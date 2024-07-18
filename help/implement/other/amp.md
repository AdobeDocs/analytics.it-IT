---
title: Implementazione con AMP
description: Implementa Adobe Analytics sulle pagine AMP.
feature: Implementation Basics
exl-id: 51a2662e-2a24-48f1-b17a-d1e1a57a394b
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 1%

---

# Implementazione con AMP

[AMP](https://amp.dev) è un framework HTML open-source che fornisce un modo semplice per creare pagine Web a caricamento rapido e senza problemi.

Poiché Adobe Analytics utilizza una libreria JavaScript per compilare e inviare una richiesta di immagine, sono necessarie delle regolazioni nell’implementazione per inviare i dati agli Adobi sulle pagine utilizzando AMP.

## Determinare quale metodo implementare Adobe Analytics sulle pagine utilizzando AMP

Adobe ha creato due metodi per implementare Adobe Analytics sulle pagine utilizzando AMP. Entrambi utilizzano il tag HTML `<amp-analytics>`. Per ulteriori informazioni, consulta [amp-analytics](https://amp.dev/documentation/components/amp-analytics) nella documentazione di AMP.

* **Usa il modello `"adobeanalytics"`**: crea la richiesta Analytics direttamente sulla pagina
* **Utilizza il modello `"analytics_nativeConfig"`**: utilizza un iframe contenente lo stesso codice di AppMeasurement distribuito nel sito normale

Nella tabella seguente vengono confrontati i due metodi seguenti:

|   | **`"adobeanalytics"`modello** | **`"adobeanalytics_nativeConfig"`modello** |
|---|---|---|
| Conteggi di visitatori e visite nella suite di rapporti esistente | Elevata inflazione | Inflazione minima |
| Utilizzare una suite di rapporti separata | Consigliato | Non necessario |
| Visitatori nuovi e di ritorno | Non supportati | Supportati |
| Servizio ID visitatori | Non supportati | Supportati |
| Tracciamento di video e collegamenti | Supporto parziale | Non ancora supportato |
| Difficoltà di implementazione | Difficile | Relativamente facile |
| Integrazioni Adobe Experience Cloud | Non supportati | Supporto parziale |

Valuta i pro e i contro in modo da poter scegliere il metodo di implementazione migliore per la tua organizzazione.

>[!WARNING]
>
>Non utilizzare entrambi i modelli `"adobeanalytics"` e `"adobeanalytics_nativeConfig"` sulla stessa pagina utilizzando AMP. Se tenti di farlo, puoi generare errori nella console del browser e contare due volte i visitatori.

## Metodo 1: utilizzare il tag `<amp-analytics>` con il modello `"adobeanalytics"`

Il modello di tracciamento `"adobeanalytics"` utilizza il tag HTML `<amp-analytics>` per creare direttamente una richiesta di tracciamento. Puoi specificare richieste di hit che si attivano su eventi di pagina specifici, come quando la pagina diventa visibile o si fa clic su di essa. È possibile personalizzare gli eventi di clic per applicarli a determinati ID o classi di elementi specificando un selettore. Puoi caricare il modello aggiungendo `type="adobeanalytics"` al tag amp-analytics.

Nell&#39;esempio di codice seguente sono definiti due trigger: `pageLoad` e `click`. Il trigger `pageLoad` viene attivato quando il documento diventa visibile e include la variabile `pageName` definita nella sezione `vars`. Il secondo trigger `click` viene attivato quando si fa clic su un pulsante. La variabile `eVar1` è impostata per questo evento con il valore `button clicked`.

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

Il tag `<amp-analytics>` supporta le sostituzioni di variabili in modo che AMP possa fornire i valori dei dati di cui è a conoscenza. Per ulteriori informazioni, vedi [variabili supportate in `amp-analytics`](https://github.com/ampproject/amphtml/blob/main/extensions/amp-analytics/analytics-vars.md) su GitHub.

>[!NOTE]
>
>Le richieste di immagini inviate ad Adobe utilizzando questo metodo non includono i dati per molti rapporti predefiniti (ad esempio, browser, dimensioni dello schermo o referrer). Se desideri includere queste informazioni negli hit, accertati che siano inclusi nella stringa di query della richiesta di immagine. Per un elenco completo dei parametri di query delle richieste di immagini e delle relative variabili associate, vedere [Parametri query raccolta dati](../validate/query-parameters.md).

Adobe identifica i visitatori utilizzando una funzione AMP incorporata e imposta il cookie `adobe_amp_id`. Questo ID visitatore è univoco rispetto a qualsiasi altro ID impostato da Adobe Analytics. Un visitatore univoco diverso viene conteggiato per ogni CDN da cui un visitatore recupera il contenuto, il che può gonfiare il conteggio dei visitatori univoci. L’utilizzo di una suite di rapporti separata per le pagine AMP è vivamente consigliato a causa del modo in cui AMP identifica i visitatori univoci. Servizio Adobe Experience Cloud ID non supportato.

Questa soluzione richiede che il server di tracciamento specificato nella proprietà `host` corrisponda al server di tracciamento sul sito principale, in modo che i controlli esistenti dell&#39;informativa sulla privacy vengano rispettati. In caso contrario, crea un’informativa sulla privacy separata per le pagine che utilizzano AMP.

## Metodo 2: utilizzare il tag `<amp-analytics>` con il modello `"adobeanalytics_nativeConfig"`

Il tag `"adobeanalytics_nativeConfig"` è più semplice da implementare, in quanto utilizza la stessa metodologia di assegnazione tag utilizzata nelle normali pagine Web. Aggiungi quanto segue al tuo tag `amp-analytics`:

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

Questo approccio invia i dati a una pagina Web di utilità tramite i parametri della stringa di query aggiunti al parametro di richiesta `iframeMessage`. Questi parametri della stringa di query possono essere denominati come desideri, purché la pagina `stats.html` sia configurata per raccogliere dati da essi.

Il modello `"adobeanalytics_nativeConfig"` aggiunge inoltre parametri della stringa di query basati sulle variabili elencate nella sezione `extraUrlParams` del tag `<amp-analytics>`. Nell&#39;esempio precedente sono inclusi i parametri `pageName` e `v1`.

>[!IMPORTANT]
>
>La pagina `stats.html` deve essere ospitata in un sottodominio separato dal dominio in cui è ospitato l&#39;AMP stesso. Il framework AMP non consente l’utilizzo di iframe dallo stesso sottodominio in cui esiste la pagina AMP stessa. Ad esempio, se il tuo AMP è ospitato su `amp.example.com`, ospita la pagina `stats.html` in un sottodominio separato come `ampmetrics.example.com`.

Utilizzando questo metodo, se un utente rinuncia al tracciamento sul sito principale, viene escluso anche dal tracciamento su tutti gli AMP. L&#39;utilizzo di questa pagina dell&#39;utilità consente inoltre ad AMP di supportare il servizio Adobe Experience Cloud ID. Non è necessaria una suite di rapporti separata.

Non è possibile utilizzare il tracciamento dei collegamenti e il tracciamento dei video con questo metodo. Il tag `iframeMessage` in AMP può essere caricato una sola volta per pagina, pertanto non puoi inviare altre richieste di immagini dopo il caricamento del frame. Questo metodo richiede inoltre più risorse di elaborazione da eseguire, il che può influire sulle prestazioni di scorrimento. Questo metodo non influisce sul tempo di caricamento della pagina, poiché tutte le risorse vengono caricate in modo asincrono.

## Domande frequenti

**Come posso distinguere i visitatori AMP dagli altri nei miei dati?**

Per tutte le pagine AMP, la dimensione [!UICONTROL JavaScript Version] raccoglie un valore simile a `AMP vX.X`. Puoi anche impostare una dimensione personalizzata su &quot;AMP&quot; in modo da poter segmentare questi visitatori.

**Come si confronta questo metodo di implementazione con gli articoli istantanei di Facebook?**

Gli articoli istantanei di facebook supportano una soluzione simile al metodo `"adobeanalytics_nativeConfig"`. La pagina `stats.html` per questo metodo può soddisfare le tue esigenze di analisi sia per AMP che per FIA contemporaneamente. Per ulteriori informazioni sull&#39;implementazione del tracciamento in FIA, vedere [Facebook Instant Article](fb-instant-articles.md).
