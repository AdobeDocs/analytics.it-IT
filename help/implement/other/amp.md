---
title: Implementazione con AMP
description: Implementa Adobe Analytics sulle pagine AMP.
feature: Implementation Basics
exl-id: 51a2662e-2a24-48f1-b17a-d1e1a57a394b
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 1%

---

# Implementazione con AMP

[AMP](https://amp.dev) è un framework HTML open-source che fornisce un modo semplice per creare pagine web veloci e con caricamento uniforme.

Poiché Adobe Analytics utilizza una libreria JavaScript per compilare e inviare una richiesta di immagine, nell’implementazione sono necessarie modifiche per inviare dati ad Adobe sulle pagine che utilizzano AMP.

## Determinare quale metodo implementare Adobe Analytics nelle pagine utilizzando AMP

Adobe ha creato due metodi per implementare Adobe Analytics nelle pagine utilizzando AMP. Entrambe utilizzano il `<amp-analytics>` Tag HTML. Vedi [Tag amp-analytics](https://amp.dev/documentation/components/amp-analytics) nella documentazione di AMP per ulteriori informazioni.

* **Utilizza la `"adobeanalytics"` modello di tracciamento**: Crea la richiesta di Analytics direttamente sulla pagina
* **Utilizza la `"analytics_nativeConfig"` modello di tracciamento**: Utilizza un iframe contenente lo stesso codice AppMeasurement distribuito sul sito normale

Nella tabella seguente vengono messi a confronto questi due metodi:

|  | **Modello &quot;adobeanalytics&quot;** | **Modello &quot;adobeanalytics_nativeConfig&quot;** |
|---|---|---|
| Conteggi di visitatori/visite nella suite di rapporti esistente | Inflazione elevata | Inflazione minima |
| Utilizzare una suite di rapporti separata | Consigliato | Non necessario |
| Visitatori nuovi e di ritorno | Non supportati | Supportati |
| Servizio ID visitatori | Non supportati | Supportati |
| Tracciamento video e collegamenti | Supporto parziale | Non ancora supportato |
| Difficoltà di implementazione | Un po&#39; difficile | Relativamente facile |
| Integrazioni Adobe Experience Cloud | Non supportati | Supporto parziale |

Valuta i pro e i contro all’interno della tua organizzazione per determinare quale metodo desideri utilizzare. Vedi [Esempi AMP](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web) nell’archivio GitHub di Adobe per codice di esempio.

>[!WARNING]
>
>Non utilizzare entrambi i `"adobeanalytics"` e `"adobeanalytics_nativeConfig"` modelli sulla stessa pagina utilizzando AMP. Se tenti di farlo, puoi generare errori nella console del browser e due numeri di visitatori.

## Metodo 1: Utilizza il tag amp-analytics con il modello &quot;adobeanalytics&quot;

La `"adobeanalytics"` il modello di tracciamento utilizza `<amp-analytics>` Tag HTML per creare direttamente una richiesta di tracciamento. Puoi specificare le richieste di hit che si attivano su eventi di pagina specifici, ad esempio quando la pagina diventa visibile o su un clic. Gli eventi di clic possono essere personalizzati per essere applicati a determinati ID di elementi o classi specificando un selettore. Puoi caricare il modello aggiungendo `type="adobeanalytics"` al tag amp-analytics.

Nell&#39;esempio di codice seguente sono definiti due trigger: `pageLoad` e `click`. La `pageLoad` l&#39;attivazione viene attivata quando il documento diventa visibile e include `pageName` come definito nella `vars` sezione . Il secondo trigger `click` viene attivato quando si fa clic su un pulsante. `eVar1` è impostato per questo evento con il valore `button clicked`.

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.data.adobedc.net",
        "reportSuites": "reportSuiteID1,reportSuiteID2",
        "pageName": "Adobe Analytics Using amp-analytics tag"
      },
      "triggers": {
        "pageLoad": {
          "on": "visible",
          "request": "pageview"
        },
        "click": {
          "on": "click",
          "selector": "button",
          "request": "myClick",
          "vars": {
            "eVar1": "button clicked"
          }
        }
      }
    }
  </script>
</amp-analytics>
```

In `click` , puoi specificare un selettore in modo che ogni volta che fai clic sull’elemento DOM specifico (in questo caso, un pulsante qualsiasi), la variabile `buttonClick` La richiesta viene attivata e viene automaticamente impostata per indicare questo hit come chiamata di tracciamento dei collegamenti.

Inoltre, `amp-analytics` supporta una serie di sostituzioni di variabili in modo che AMP possa fornire valori di dati di cui è a conoscenza. Vedi [variabili supportate in amp-analytics](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) su GitHub per ulteriori informazioni.

>[!NOTE]
>
>Le richieste di immagini inviate ad Adobe utilizzando questo metodo non includono dati per molti rapporti predefiniti (ad esempio, browser, dimensioni dello schermo o referrer). Se desideri includere queste informazioni negli hit, accertati che siano incluse come parte della stringa di query della richiesta di immagine. Vedi [Parametri query di raccolta dati](../validate/query-parameters.md) per ulteriori informazioni.

Adobe identifica i visitatori utilizzando una funzione AMP integrata e imposta il cookie `adobe_amp_id`. Questo ID visitatore è univoco per qualsiasi altro ID impostato da Adobe Analytics (ad esempio, `s_vi` cookie). Il servizio Adobe Experience Cloud ID non è supportato utilizzando questo metodo di implementazione.

>[!NOTE]
>
>AMP utilizza CDN per distribuire contenuti. È strutturato per contare un visitatore univoco diverso per ogni CDN da cui un visitatore recupera il contenuto, il che può gonfiare il conteggio dei visitatori univoci.

Si consiglia di utilizzare una suite di rapporti separata per le pagine AMP a causa del modo in cui AMP identifica i visitatori univoci.

Questa soluzione richiede che il server di tracciamento specificato nel `host` corrisponde al server di tracciamento sul sito principale, in modo che i controlli dell&#39;informativa sulla privacy esistenti vengano rispettati. In caso contrario, crea un&#39;informativa sulla privacy separata per le pagine che utilizzano AMP.

## Metodo 2: Utilizza il tag amp-analytics con il modello &quot;adobeanalytics_nativeConfig&quot;

La `"adobeanalytics_nativeConfig"` è più semplice da implementare, in quanto utilizza la stessa metodologia di assegnazione tag utilizzata nelle normali pagine web. Aggiungi quanto segue al tuo `amp-analytics` tag:

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.data.adobedc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

È inoltre necessaria una pagina HTML ospitata sui server web:

```html
<html>
  <head>
    <title>Stats Example</title>
    <script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script>
    <script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script>
  </head>
  <body>
    <script>
      var v_orgId = "INSERT-ORG-ID-HERE";
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
      var visitor = Visitor.getInstance(v_orgId);
      visitor.trackingServer = s_trackingServer;
      var s = s_gi(s_account);
      s.account = s_account;
      s.trackingServer = s_trackingServer;
      s.visitorNamespace = s_visitorNamespace;
      s.visitor = visitor;
      s.pageName = s.Util.getQueryParam("pageName");
      s.eVar1 = s.Util.getQueryParam("v1");
      s.campaign = s.Util.getQueryParam("campaign");
      s.pageURL = s.Util.getQueryParam("pageURL");
      s.referrer = s.Util.getQueryParam("ref");
      s.t();
    </script>
  </body>
</html>
```

Questo approccio invia i dati a una pagina Web di un&#39;utilità tramite i parametri della stringa di query aggiunti al `iframeMessage` parametro di richiesta. Questi parametri della stringa di query possono essere denominati come preferisci, purché il tuo `stats.html` La pagina è configurata per raccogliere i dati da esse.

La `"adobeanalytics_nativeConfig"` modello aggiunge anche parametri della stringa di query basati sulle variabili elencate nella `extraUrlParams` della sezione del tag amp-analytics. Nell’esempio precedente, la `pageName` e `v1` sono inclusi.

>[!IMPORTANT]
>
>Le `stats.html` la pagina deve essere ospitata in un sottodominio separato dal dominio in cui è ospitato l’AMP stesso. Il framework AMP non consente l’utilizzo di iframe dello stesso sottodominio su cui si trova la pagina AMP. Ad esempio, se AMP è ospitato su `amp.example.com`, ospita `stats.html` in un sottodominio separato, ad esempio `ampmetrics.example.com`.

Utilizzando questo metodo, se un utente rinuncia al tracciamento sul sito principale, viene anche escluso dal tracciamento su tutti gli AMP. L&#39;utilizzo di questa pagina di utilità consente inoltre ad AMP di supportare il servizio Adobe Experience Cloud ID. Non è necessaria una suite di rapporti separata.

Impossibile utilizzare il tracciamento dei collegamenti e il tracciamento video con questo metodo. La `iframeMessage` In AMP è possibile caricare solo una volta per pagina, pertanto non è possibile inviare altre richieste di immagini dopo il caricamento del frame. Questo metodo richiede inoltre l’esecuzione di più risorse di elaborazione, che possono influire sulle prestazioni di scorrimento. Questo metodo non influisce sul tempo di caricamento della pagina, in quanto tutte le risorse vengono caricate in modo asincrono.

## Domande frequenti

**Il tracciamento video è disponibile per entrambi i metodi?**

No. Lo standard AMP supporta solo i trigger per &quot;visible&quot;, &quot;click&quot; e &quot;timer&quot;. Non supporta ancora attivatori espliciti per il tracciamento video che `amp-analytics` può ascoltare. Inoltre, il `"adobeanalytics_nativeConfig"` il modello può essere caricato solo una volta, pertanto non è possibile effettuare richieste di immagini successive dopo il caricamento di una pagina.

**Come posso distinguere i visitatori AMP dagli altri nei miei dati?**

Per tutte le pagine AMP, il [!UICONTROL JavaScript Version] raccoglie un valore simile a `AMP vX.X`. Puoi anche impostare una dimensione personalizzata su &quot;AMP&quot; in modo da segmentare i visitatori.

**Come si confronta questo metodo di implementazione con gli articoli istantanei di Facebook?**

Gli articoli istantanei di facebook supportano una soluzione simile a `"adobeanalytics_nativeConfig"` metodo . La `stats.html` pagina per questo metodo può soddisfare le tue esigenze di analisi sia per AMP che per FIA simultaneamente. Per ulteriori informazioni sull&#39;implementazione del tracciamento su FIA, vedi [Articoli istantanei facebook](fb-instant-articles.md).
