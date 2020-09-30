---
title: Implementazione con AMP
description: Implementa  Adobe Analytics sulle pagine AMP.
translation-type: tm+mt
source-git-commit: 684e67203b2e3d5f0cb82cdbdda1f24d37a677f0
workflow-type: tm+mt
source-wordcount: '1059'
ht-degree: 1%

---


# Implementazione con AMP

[AMP](https://amp.dev) è un framework HTML open-source che fornisce un modo semplice per creare pagine Web con un caricamento rapido e uniforme.

Poiché  Adobe Analytics utilizza una libreria JavaScript per compilare e inviare una richiesta di immagine, nell’implementazione sono necessarie delle regolazioni per inviare i dati  Adobe sulle pagine tramite AMP.

## Determinare quale metodo implementare  Adobe Analytics sulle pagine utilizzando AMP

 Adobe ha creato due metodi per implementare  Adobe Analytics sulle pagine utilizzando AMP. Entrambi utilizzano il tag `<amp-analytics>` HTML. Per ulteriori informazioni, consulta Tag [di analisi](https://github.com/ampproject/amphtml/tree/master/extensions/amp-analytics) amp su ampproject GitHub.

* **Utilizzate il modello`"adobeanalytics"`di** tracciamento: Crea la richiesta di Analytics direttamente sulla pagina
* **Utilizzate il modello`"analytics_nativeConfig"`di** tracciamento: Utilizza un iframe contenente lo stesso codice AppMeasurement distribuito nel sito normale

Nella tabella seguente vengono confrontati i due metodi seguenti:

|  | **Modello &quot;adobeanalytics&quot;** | **Modello &quot;adobeanalytics_nativeConfig&quot;** |
|---|---|---|
| Conteggio visitatori/visite nella suite di rapporti esistente | Alta inflazione | Inflazione minima |
| Utilizzare una suite di rapporti separata | Consigliato | Non necessario |
| Visitatori nuovi e di ritorno | Non supportati | Supportati |
| Servizio ID visitatori | Non supportati | Supportati |
| Tracciamento di video e collegamenti | Supporto parziale | Non ancora supportato |
| Difficoltà di implementazione | Un po&#39; difficile | Relativamente facile |
| Integrazioni Adobe Experience Cloud | Non supportati | Supporto parziale |

Valutare i pro e i contro all&#39;interno dell&#39;organizzazione per determinare quale metodo utilizzare. Per un esempio di codice, consultate esempi [](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web) AMP  archivio GitHub  Adobe.

>[!WARNING]
>
>Non utilizzate sia i modelli `"adobeanalytics"` che `"adobeanalytics_nativeConfig"` i modelli sulla stessa pagina utilizzando AMP. Se tentate di farlo, potete generare errori nella console del browser e il doppio conteggio dei visitatori.

## Metodo 1: Utilizzare il tag amp-analytics con il modello &quot;adobeanalytics&quot;

Il modello di `"adobeanalytics"` tracciamento utilizza il tag `<amp-analytics>` HTML per creare direttamente una richiesta di tracciamento. Potete specificare le richieste di hit da attivare su eventi di pagina specifici, ad esempio quando la pagina diventa visibile o su un clic. Gli eventi di clic possono essere personalizzati per essere applicati ad alcuni ID di elementi o classi specificando un selettore. Potete caricare il modello aggiungendo `type="adobeanalytics"` al tag amp-analytics.

Nell&#39;esempio di codice seguente sono definiti due attivatori: `pageLoad` e `click`. L&#39; `pageLoad` attivatore viene attivato quando il documento diventa visibile e include la `pageName` variabile come definita nella `vars` sezione. Il secondo attivatore `click` viene attivato quando si fa clic su un pulsante. `eVar1` è impostato per questo evento con il valore `button clicked`.

```html
<amp-analytics type="adobeanalytics">
  <script type="application/json">
    {
      "requests": {
        "myClick": "${click}&v1=${eVar1}",
      },
      "vars": {
        "host": "example.sc.omtrdc.net",
        "reportSuites": "reportSuiteID",
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

Nell&#39; `click` attivatore, potete specificare un selettore in modo che ogni volta che si fa clic sullo specifico elemento DOM (in questo caso, su un pulsante), la `buttonClick` richiesta venga attivata e impostata automaticamente per indicare l&#39;hit come una chiamata di tracciamento del collegamento.

Inoltre, `amp-analytics` supporta una serie di sostituzioni variabili in modo che AMP possa fornire valori di dati di cui è a conoscenza. Per ulteriori informazioni, vedi [le variabili supportate nelle analisi](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) di ampli su GitHub.

>[!NOTE]
>
>Le richieste di immagini inviate al Adobe  con questo metodo non includono i dati per molti rapporti predefiniti (ad esempio, browser, dimensioni dello schermo o referente). Se desiderate includere queste informazioni negli hit, accertatevi che siano incluse come parte della stringa di query della richiesta di immagine. Per ulteriori informazioni, vedi Parametri [query di raccolta](../validate/query-parameters.md) dati.

 Adobe identifica i visitatori che utilizzano una funzione AMP integrata e imposta il cookie `adobe_amp_id`. Questo ID visitatore è univoco per qualsiasi altro ID impostato da  Adobe Analytics (ad esempio, il `s_vi` cookie). Il servizio Adobe Experience Cloud ID non è supportato utilizzando questo metodo di implementazione.

>[!NOTE]
>
>AMP utilizza CDN per distribuire contenuti. È strutturata per contare un visitatore univoco diverso per ogni CDN da cui un visitatore recupera il contenuto, il che può aumentare il numero di visitatori univoci.

È consigliabile utilizzare una suite di rapporti distinta per le pagine AMP, in quanto AMP identifica i visitatori univoci.

Questa soluzione richiede che il server di tracciamento specificato nella `host` proprietà corrisponda al server di tracciamento sul sito principale, in modo da rispettare i controlli dell&#39;informativa sulla privacy esistenti. In caso contrario, create un&#39;informativa sulla privacy separata per le pagine utilizzando AMP.

## Metodo 2: Utilizzare il tag amp-analytics con il modello &quot;adobeanalytics_nativeConfig&quot;

Il `"adobeanalytics_nativeConfig"` tag è più semplice da implementare, in quanto utilizza la stessa metodologia di tag utilizzata sulle pagine Web normali. Aggiungi quanto segue al `amp-analytics` tag:

```html
<amp-analytics type="adobeanalytics_nativeConfig">
  <script type="application/json">
    {
      "requests": {
        "base": "https://${host}",
        "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}"
      },
      "vars": {
        "host": "example.sc.omtrdc.net"
      },
      "extraUrlParams": {
      "pageName": "Example AMP page",
      "v1": "eVar1 example value"
      }
    }
 </script>
</amp-analytics>
```

È inoltre necessaria una pagina HTML ospitata sui server Web:

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
      var s_account = "examplersid";
      var s_trackingServer = "example.sc.omtrdc.net";
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

Questo approccio invia i dati a una pagina Web di utilità tramite i parametri della stringa di query aggiunti al parametro `iframeMessage` request. Questi parametri di stringa di query possono essere denominati come preferite, purché la `stats.html` pagina sia configurata per la raccolta dei dati da tali parametri.

Il `"adobeanalytics_nativeConfig"` modello aggiunge anche parametri di stringa di query basati sulle variabili elencate nella `extraUrlParams` sezione del tag amp-analytics. Nell&#39;esempio precedente, i `pageName` parametri e `v1` .

>[!IMPORTANT]
>
>La `stats.html` pagina deve essere ospitata in un sottodominio separato dal dominio in cui è ospitato l’AMP stesso. Il framework AMP non consente iframe dello stesso sottodominio in cui esiste la pagina AMP stessa. Ad esempio, se l’AMP è ospitato in `amp.example.com`, ospita la `stats.html` pagina in un sottodominio separato, ad esempio `ampmetrics.example.com`.

Utilizzando questo metodo, se un utente rinuncia al tracciamento sul sito principale, viene escluso anche il tracciamento su tutti gli AMP. Utilizzando questa pagina di utilità, AMP può anche supportare il servizio Adobe Experience Cloud ID. Non è richiesta una suite di rapporti separata.

Con questo metodo non è possibile utilizzare il tracciamento dei collegamenti e il tracciamento video. Il `iframeMessage` tag in AMP può essere caricato solo una volta per pagina, pertanto non potete inviare altre richieste di immagini dopo il caricamento del frame. Questo metodo richiede inoltre ulteriori risorse di elaborazione da eseguire, che possono avere un impatto sulle prestazioni di scorrimento. Questo metodo non influisce sul tempo di caricamento della pagina, in quanto tutte le risorse vengono caricate in modo asincrono.

## Domande frequenti

**Il tracciamento video è disponibile per entrambi i metodi?**

No. Lo standard AMP supporta solo attivatori per &quot;visible&quot;, &quot;click&quot; e &quot;timer&quot;. Non supporta ancora attivazioni esplicite per il tracciamento video che il `amp-analytics` tag può ascoltare. Inoltre, il `"adobeanalytics_nativeConfig"` modello può essere caricato solo una volta, pertanto non è possibile effettuare richieste di immagini successive al caricamento di una pagina.

**Come posso distinguere i visitatori AMP da altri nei miei dati?**

Per tutte le pagine AMP, la [!UICONTROL JavaScript Version] dimensione raccoglie un valore simile a `AMP vX.X`. Potete anche impostare una dimensione personalizzata su &#39;AMP&#39; in modo da segmentare i visitatori.

**In che modo questo metodo di implementazione è paragonabile agli articoli istantanei di Facebook?**

Gli articoli istantanei di Facebook supportano una soluzione simile al `"adobeanalytics_nativeConfig"` metodo. La `stats.html` pagina per questo metodo può soddisfare le esigenze di analisi sia per AMP che per FIA simultaneamente. Per ulteriori informazioni sull&#39;implementazione del tracciamento su FIA, consulta Articoli [istantanei di](fb-instant-articles.md)Facebook.
