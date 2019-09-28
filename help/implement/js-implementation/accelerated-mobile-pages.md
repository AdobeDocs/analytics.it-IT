---
description: Implementa il progetto Accelerated Mobile Pages (AMP) in Adobe Analytics.
keywords: Analytics Implementation;amp;amp-analytics;adobeanalytics template;adobeanalytics_nativeConfig template;click tracking;visitor inflation;id service
seo-description: Implementa il progetto Accelerated Mobile Pages (AMP) in Adobe Analytics.
seo-title: Accelerated Mobile Pages
solution: Analytics
title: Accelerated Mobile Pages
topic: Sviluppatore e implementazione
uuid: c86e4a80-7191-4ee7-ab20-78730026c4b
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Accelerated Mobile Pages

Implementa il progetto Accelerated Mobile Pages (AMP) in Adobe Analytics.

AMP is an [open source project](https://www.ampproject.org/) that lets you build web pages for static content that renders quickly. Questa funzione è ideale per coloro che desiderano creare e pubblicare contenuti ottimizzati per dispositivi mobili per poi caricarli istantaneamente ovunque. Gli argomenti includono:

* [Come funziona](../../implement/js-implementation/accelerated-mobile-pages.md#section_21C2836D63104794BCEBEECB6593AFBF)
* [Utilizzo del tag amp-analytics con il modello "adobeanalytics"](../../implement/js-implementation/accelerated-mobile-pages.md#section_2E4EBF4EF623440D95DE98E78C47244E)
* [Utilizzo del tag amp-analytics con il modello "adobeanalytics_nativeConfig"](../../implement/js-implementation/accelerated-mobile-pages.md#section_3556B68304A4492991F439885727E9FF)
* [Riepilogo](../../implement/js-implementation/accelerated-mobile-pages.md#section_4D8ED26084F249738A5C2BC66B933A07)
* [Domande frequenti](../../implement/js-implementation/accelerated-mobile-pages.md#section_5F57AA2DE0C5452FB65241058A924C73)

**Documentazione ed esempi aggiuntivi**

* Documentazione di progetto AMP esterna e open-source [](https://www.ampproject.org/docs/get_started/about-amp.html)
* Esempi [di configurazione](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml)

## Come funziona {#section_21C2836D63104794BCEBEECB6593AFBF}

Gli AMP dispongono di pagine HTML con tag specifici memorizzate nella cache sul Web su reti CDN (content delivery network, reti di distribuzione di contenuti) diverse tra partner tecnologici e editori partecipanti. In questo modo, il contenuto AMP viene distribuito dalla sorgente più vicina possibile con la latenza più bassa possibile. Questo crea una sfida di analisi perché non puoi mai essere sicuro al 100% di dove verrà caricato il contenuto di un editore e i cookie di terze parti sono fastidiosi per l'identificazione del visitatore.

Inoltre, per ridurre notevolmente il peso della pagina e il tempo di caricamento della pagina, gli AMP limitano l'uso di JavaScript e cookie. Anche se questo è vantaggioso per il dispositivo mobile perché riduce la quantità di elaborazione, introduce delle sfide per misurare con precisione i visitatori unici e comprendere l'acquisizione e la conservazione degli utenti.

Per risolvere questi problemi, Adobe ha collaborato con partner ed editori AMP su due opzioni tra cui un editore può scegliere per soddisfare al meglio le proprie esigenze aziendali, utilizzando entrambi il `amp-analytics` tag . Il primo approccio utilizza il modello di `"adobeanalytics"` tracciamento per costruire la richiesta di Analytics direttamente dall’interno dell’AMP. Il secondo approccio utilizza il modello di `"analytics_nativeConfig"` tracciamento, che utilizza un iframe contenente il codice AppMeasurement distribuito sul sito normale. Nella tabella seguente sono illustrati i pro e i contro di ciascun approccio.

|  | **Modello "adobeanalytics"** | ** Modello "adobeanalytics_nativeConfig"** |
|---|---|---|
| Conteggio visitatori/visite (nella suite di rapporti esistente) | Alta inflazione | Inflazione minima |
| Utilizzo di una suite di rapporti separata | Consigliato | Non necessario |
| Visitatori nuovi e di ritorno | Non supportato | Supportate |
| Servizio ID visitatori | Non supportato | Supportate |
| Tracciamento video e collegamenti | Supporto parziale | Non ancora supportato |
| Difficoltà di implementazione | Un po' difficile | Relativamente facile |
| [!DNL Experience Cloud] integrazioni | Non supportato | Supportato da cavezze |

## Utilizzo del tag amp-analytics con il modello "adobeanalytics" {#section_2E4EBF4EF623440D95DE98E78C47244E}

Il modello di `"adobeanalytics"`tracciamento utilizza il `amp-analytics` tag per creare direttamente una richiesta di tracciamento. Utilizzando il `"adobeanalytics"` modello nel `amp-analytics` tag , potete specificare le richieste di hit da attivare in corrispondenza di eventi di pagina specifici, come la pagina che diventa visibile o su un clic (e in futuro, visualizzazioni video e altro ancora). Gli eventi di clic possono essere personalizzati per essere applicati ad alcuni ID di elementi o classi specificando un selettore. Adobe ha semplificato la configurazione utilizzando il `"adobeanalytics"` modello appositamente progettato per [!DNL Adobe Analytics]. Potete caricare il modello aggiungendo `type="adobeanalytics"` al tag amp-analytics.

Nell'esempio di codice seguente sono definiti due attivatori: `pageLoad` e `click`. L' `pageLoad` attivatore viene attivato quando il documento diventa visibile e includerà la `pageName` variabile come definito nel `vars section`. Il secondo attivatore `click` viene attivato quando si fa clic su un pulsante. `eVar 1` verrà impostato per questo evento con il valore `button clicked`.

```
  <amp-analytics type="adobeanalytics"> 
  <script type="application/json"> 
  { 
        "requests": { 
      "myClick": "${click}&v1=${eVar1}", 
  }, 
  "vars": { 
      "host": "metrics.example.com", 
      "reportSuites": "reportSuiteID", 
      "pageName": "Adobe Analytics Using amp-analytics tag" 
  }, 
    "triggers": { 
      "pageLoad": { 
        "on": "visible", 
        "request": "pageView" 
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

Nell' `click` attivatore, potete specificare un selettore in modo che ogni volta che si fa clic sullo specifico elemento DOM (in questo caso, un pulsante), la `buttonClick` richiesta venga attivata e venga automaticamente impostata per denotare l'hit come evento non-stage ( `trackLink` chiamata).

Inoltre, `amp-analytics` supporta una serie di sostituzioni variabili in modo che AMP possa fornire valori di dati di cui è a conoscenza. Per saperne di più visita: Documentazione [della variabile](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md)di analisi dei dati.

Tenete presente che se desiderate incorporare una qualsiasi tecnologia o variabili DOM (come browser, dimensioni dello schermo, dispositivo, referente, ecc.) dovrete aggiungerli esplicitamente a qualsiasi richiesta, in quanto non vengono generati automaticamente. La documentazione relativa a ciascuno dei parametri di stringa di query disponibili utilizzati per il tracciamento è disponibile [qui](https://marketing.adobe.com/resources/help/en_US/sc/implement/query_parameters.html).

Se ispezionate gli hit creati da amp analytics, noterete che in ogni richiesta Adobe ha incluso il parametro di `vid` query. L'impostazione è `vid` basata su una funzione AMP integrata per impostare un ID cookie Analytics personalizzato denominato `adobe_amp_id`. Questo ID è indipendente da qualsiasi altro ID impostato da [!DNL Adobe Analytics] un altro utente (ad es. `s_vi cookie`) e crea nuovi visitatori in qualsiasi suite di rapporti a cui vengono inviati gli hit.

Ci sono alcuni avvertimenti di cui essere a conoscenza. Quando si utilizza il tag di analisi per ampli come indicato sopra, i visitatori saranno indipendenti dal normale tracciamento, e poiché l'AMP può essere caricato da qualsiasi rete di distribuzione dei contenuti, si avrà un visitatore unico per ogni CDN su cui un visitatore vede questo AMP (da qui l'inflazione dei visitatori menzionata in precedenza). Per questo motivo, Adobe consiglia di inserire i dati in una suite di rapporti separata specifica di AMP se si utilizza il `"adobeanalytics"` modello per `amp-analytics`. Inoltre, il servizio [!DNL Experience Cloud] ID (già, *`visitor ID service`*) non è supportato utilizzando questo metodo, quindi se la tua azienda richiede [!DNL Experience Cloud] integrazioni aggiuntive, o lo sarà in futuro, questa probabilmente non sarà l’opzione giusta.

Infine, e forse ancora più importante, questa `amp-analytics` soluzione richiede che il server di tracciamento specificato nella `vars` sezione corrisponda al server di tracciamento sul sito principale, in modo da rispettare i controlli dell'informativa sulla privacy esistenti. In caso contrario, devi creare un'informativa sulla privacy separata solo per gli AMP.

## Utilizzo del tag amp-analytics con il modello "adobeanalytics_nativeConfig" {#section_3556B68304A4492991F439885727E9FF}

Il `"adobeanalytics_nativeConfig"` tag è più semplice da implementare, in quanto utilizza la stessa metodologia di tag utilizzata sulle pagine Web normali. A questo scopo, aggiungete quanto segue al `amp-analytics` tag:

```
<amp-analytics type="adobeanalytics_nativeConfig"> 
 <script type="application/json"> 
 { 
  "requests": { 
   "base": "https://${host}", 
   "iframeMessage": "${base}/stats.html?campaign=${queryParam(campaign)}&pageURL=${ampdocUrl}&ref=${documentReferrer}" 
  }, 
  "vars": { 
   "host": "statshost.publishersite.com" 
  }, 
  "extraUrlParams": { 
   "pageName": "Adobe Analytics Using amp-analytics tag", 
   "v1": "eVar1 test value" 
  } 
 } 
 </script> 
</amp-analytics>  
```

Questo approccio invia i dati a una pagina Web dell'utility tramite i parametri stringa di query speciali aggiunti al parametro `iframeMessage` request. In questo caso, si noti che abbiamo aggiunto la `ampdocUrl AMP` variabile, e `documentReferrer` i parametri della stringa di query `pageURL`, e si fa riferimento rispettivamente alla `iframeMessage` richiesta precedente. Questi parametri di stringa di query aggiuntivi possono essere denominati come preferite, purché la [!DNL stats.html] pagina (come illustrato di seguito) sia configurata per raccogliere i dati appropriati.

Il `"adobeanalytics_nativeConfig"` modello aggiunge anche parametri di stringa di query basati sulle variabili elencate nella `extraUrlParams` sezione del tag amp-analytics. In questo caso, potete vedere che abbiamo specificato i `pageName` parametri e `v1` , che verranno utilizzati dalla nostra [!DNL stats.html] pagina.

Tenete presente che potete utilizzare un solo `amp-analytics` modello alla volta e non potete usare sia il `"adobeanalytics"` modello che il `"adobeanalytics_nativeConfig"` modello sullo stesso AMP. Se tentate di farlo, potreste visualizzare un errore nella console del browser e gonfierete erroneamente il numero dei visitatori.

```
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
<html> 
<head> 
<title>Stats Test</title> 
<script language="JavaScript" type="text/javascript" src="VisitorAPI.js"></script> 
<script language="JavaScript" type="text/javascript" src="AppMeasurement.js"></script> 
</head> 
<body> 
<script> 
var v_orgId = "1234567@PublisherOrg"; 
var s_account = "reportSuite"; 
var s_trackingServer = "metrics.publisher.com"; 
var s_visitorNamespace = "publisherNamespace"; 
var visitor = Visitor.getInstance(v_orgId); 
visitor.trackingServer = s_trackingServer; 
var s = s_gi(s_account); 
s.account = s_account; 
s.trackingServer = s_trackingServer; 
s.visitorNamespace = s_visitorNamespace; 
s.visitor = visitor; 
s.pagename = s.Util.getQueryParam("pageName"); 
s.eVar1=s.Util.getQueryParam("v1"); 
s.campaign=s.Util.getQueryParam("campaign"); 
s.pageURL=s.Util.getQueryParam("pageURL"); 
s.referrer=s.Util.getQueryParam(“ref”); 
s.t(); 
</script> 
</body> 
</html> 
```

Come mostrato sopra, puoi usare o collegare al tuo esistente [!DNL VisitorAPI.js] e [!DNL AppMeasurement.js] (come nel nostro esempio), o qualsiasi cosa utilizzi l'implementazione esistente, quindi aggiungere i parametri di configurazione corretti. Per acquisire i valori corretti nelle variabili corrette, è possibile utilizzare la `s.Util.getQueryParam` funzione fornita per acquisire i valori passati dall' `iframeMessage` URL e impostare le variabili appropriate, come si fa in una pagina tipica. Se utilizzate un software di gestione tag come Adobe [ [!DNL Dynamic Tag Manager] ](https://www.adobe.com/solutions/digital-marketing/dynamic-tag-management.html), i parametri della stringa di query devono essere semplici da acquisire. In questo caso, `s.pageName` è impostato sul valore passato nel parametro della stringa di query `pageName`. Qui il nome della pagina viene impostato su *`Adobe Analytics Example 2`*.

>[!IMPORTANT]
>
>A causa di restrizioni sugli iframe nel framework AMP, la [!DNL stats.html] pagina deve essere ospitata in un sottodominio separato dal dominio in cui è ospitato l'AMP stesso. Il framework AMP non consente iframe dello stesso sottodominio in cui esiste la pagina AMP stessa. Ad esempio, se il vostro AMP è ospitato su [!DNL amp.example.com], assicuratevi di ospitare la [!DNL stats.html] pagina in un sottodominio separato, ad esempio [!DNL ampmetrics.example.com] o qualcosa di simile.

Poiché la pagina dell'utility è ospitata sul sito originale, non è necessario alcun lavoro aggiuntivo per supportare l'informativa sulla privacy esistente in tutti gli AMP. Ciò significa che, se un utente finale rinuncia al tracciamento sul sito principale, non potrà più effettuare il tracciamento su tutti gli AMP, senza dover effettuare ulteriori passaggi. Utilizzando questa pagina di utilità, AMP può anche supportare il servizio Adobe [!DNL Experience Cloud] ID in modo da poter integrare la misurazione acquisita sull’AMP con il resto dell’ [!DNL Experience Cloud] (per la pubblicità mirata utilizzando [!DNL Adobe Audience Manager] ad esempio).

Per ribadire, se l’organizzazione non utilizza ancora il servizio [!DNL Experience Cloud] ID (o ha un software di gestione tag come quello di Adobe [!DNL Dynamic Tag Manager]), puoi assegnare alla [!DNL stats.html] pagina i tag desiderati. Utilizza l’implementazione esistente come punto di riferimento. L’unica differenza rispetto all’implementazione standard è che si ottengono i punti dati applicabili dall’ `iframeMessage` URL di analisi amp (o [!DNL document.URL] dall’interno della [!DNL stats.html] pagina) per ciascuna delle variabili da impostare. Inoltre, se desiderate utilizzare una qualsiasi delle variabili [specifiche](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) AMP (come indicato sopra) come il referente AMP o l'URL della pagina AMP, includetele nell'oggetto iframeMessage come illustrato nel nostro esempio precedente.

Per quanto flessibile sia questa soluzione, ci sono delle avvertenze. A causa di restrizioni intrinseche nella `amp-analytics` pagina, è possibile caricarla solo una volta su una pagina caricata `iframeMessage`. Ciò significa che non sarà possibile effettuare il tracciamento dei collegamenti o del video con il `"adobeanalytics_nativeConfig"` modello. Inoltre, alcuni valori DOM solitamente catturati automaticamente dal nostro [!DNL AppMeasurement] codice, come `referrer` (che interessa i rapporti sulle parole chiave del motore di ricerca, i rapporti sul referente e sul tipo di referente, o che possono includere un codice di tracciamento della campagna di marketing) dovranno essere passati manualmente al `iframeMessage` sistema utilizzando tutte le variabili AMP [disponibili](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md). Per questo motivo, Adobe consiglia di impostare una variabile personalizzata con il valore AMP se inserisci dati AMP in una suite di rapporti esistente, in modo da segmentare il traffico AMP quando visualizzi i rapporti sopra indicati. Tuttavia, i report sulla tecnologia standard, come browser, dispositivo, dimensioni dello schermo o risoluzione, dovrebbero funzionare automaticamente.

Infine, poiché l'iframe viene caricato come una pagina separata ed esegue completamente il codice JavaScript su tale pagina, l'AMP non è leggero come previsto dallo standard AMP. Per essere chiari, questo non influisce sul tempo di caricamento della pagina (l'iframe viene caricato dopo il caricamento della pagina), ma la CPU e la rete stanno facendo poco più di quanto non farebbero altrimenti, il che potrebbe avere un impatto sull'uniformità dello scorrimento. In pratica, non abbiamo visto un grande impatto, ma stiamo lavorando con Google per ridurre al minimo l'impatto dell'esperienza utente di questo approccio.

## Riepilogo {#section_4D8ED26084F249738A5C2BC66B933A07}

Se hai bisogno del monitoraggio dei clic e non ti dispiace che i visitatori vengano conteggiati come visitatori completamente nuovi separati dal tuo sito, usa il modello di `"adobeanalytics"` tracciamento, con la nostra raccomandazione di inserire i dati in un *`separate report suite`*. Se hai bisogno del servizio [!DNL Experience Cloud] ID, non vuoi che il visitatore o l’inflazione venga visitata e puoi attivare solo Analytics al caricamento della pagina, ti consigliamo di utilizzare la `"adobeanalytics_nativeConfig"` soluzione.

Adobe Analytics è entusiasta di collaborare con Google e i nostri editori per offrire agli editori sul Web dei dispositivi mobili funzionalità di analisi leader del settore con un'esperienza utente estremamente semplice. Anche se queste due soluzioni offrono attualmente i loro compromessi, ci impegniamo a creare la migliore soluzione a lungo termine per rispondere alle esigenze di analisi in evoluzione dei nostri clienti.

Il progetto AMP si sta muovendo velocemente e si verificano spesso cambiamenti, quindi [qui](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml) di frequente per gli aggiornamenti ai nostri esempi. Quello che abbiamo mostrato qui dovrebbe essere abbastanza per iniziare, ma ci aspettiamo dei cambiamenti man mano che miglioriamo ulteriormente le integrazioni e che più editori adotteranno AMP nel tempo.

In caso di domande o problemi, rivolgiti al tuo consulente Adobe o all'Assistenza clienti.

## Domande frequenti {#section_5F57AA2DE0C5452FB65241058A924C73}

<table id="table_9A2ED5E482E8423CB54F99613C04BEA0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Il tracciamento video è disponibile per il modello <code> "adobeanalytics" </code> o <code> "adobeanalytics_nativeConfig" </code> ? </p> </td> 
   <td colname="col2"> <p> Sfortunatamente, non ancora. Lo standard AMP supporta solo attivatori per "visible", "click" e "timer", e non supporta ancora attivatori espliciti per il tracciamento video che possono essere ascoltati dal tag di analisi amp. Inoltre, poiché <code> "adobeanalytics_nativeConfig" </code> tag può essere caricato solo una volta, non è compatibile con la visualizzazione video che si verifica dopo il caricamento dell’AMP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>L'inflazione del visitatore è inferiore per il modello " <code> adobeanalytics_nativeConfig </code>" nel confronto. Cosa significa? Cosa causerebbe l'inflazione dei visitatori nella soluzione <code> "adobeanalytics" </code> o <code> "adobeanalytics_nativeConfig" </code> ? </p> </td> 
   <td colname="col2"> <p>Il modello <code> "adobeanalytics" </code> non consente ad Adobe Analytics di impostare un cookie di identificazione del visitatore; ciò significa che tutte le visite e i visitatori della pagina AMP saranno trattati come una visita e un visitatore nuovi e indipendenti nella suite di rapporti. </p> <p>Il modello <code> "adobeanalytics_nativeConfig" </code> , tuttavia, consente di impostare il cookie di identificazione del visitatore di Adobe Analytics in quasi tutti i casi, ad eccezione dei nuovi visitatori che utilizzano il browser Safari. Ciò significa che tutti i visitatori da Safari che non hanno visitato in precedenza il sito di un editore verranno ingranditi nei rapporti di Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devo utilizzare una suite di rapporti separata per gli AMP? </p> </td> 
   <td colname="col2"> <p>È consigliabile utilizzare una suite di rapporti separata per gli AMP se si utilizza il modello adobeanalytics, a causa del problema di inflazione visitatore/visita. Tuttavia, imposteremo anche la versione JavaScript su "AMP vX.X" dal modello di tag di analisi di ampli in modo che possiate segmentare il traffico fuori da una suite di rapporti combinata, se necessario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cos'è il servizio <span class="keyword"> Experience Cloud </span> ID? Ne ho bisogno? </p> </td> 
   <td colname="col2"> <p>Il <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> servizio ID </a> (già servizio ID <span class="term"> visitatore </span>) abilita i servizi di base <span class="keyword"> Experience Cloud </span> e consente l’integrazione tra diverse soluzioni Adobe <span class="keyword"> Experience Cloud </span> . Se disponete di integrazioni con <span class="keyword"> Adobe Audience Manager </span> o <span class="keyword"> </span>Adobe Target, probabilmente state utilizzando questo servizio. Questo servizio è inoltre alla base di molte delle prossime funzionalità di <span class="keyword"> Adobe Analytics </span> . Se hai bisogno del supporto del servizio ID o ne avrai bisogno in futuro, ti consigliamo di utilizzare la soluzione <code> iframeMessage </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per il modello <code> "adobeanalytics_nativeConfig" </code> , dove devo ospitare la pagina dell'utility? </p> </td> 
   <td colname="col2"> <p>Lo standard AMP non consente il caricamento di iframe dal dominio esatto e sottodominio dell'AMP stesso. Di conseguenza, si consiglia di ospitare la pagina dell'utility su un sottodominio separato dal sito principale, soprattutto se la società dispone di un CDN specifico che pianifica il caching degli AMP. Per la massima compatibilità, scegliete un sottodominio come <span class="filepath"> ampmetriche.publisher.com </span> che sia diverso da dove risiederà il contenuto AMP effettivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Questo non è simile agli articoli istantanei di <span class="keyword"> Facebook </span>? Come si configura <span class="keyword"> Adobe Analytics </span> con gli articoli istantanei di Facebook? </p> </td> 
   <td colname="col2"> <p> Gli articoli istantanei di Facebook supportano una soluzione simile alla soluzione nativeConfig descritta sopra. Infatti, la pagina stats.html creata sopra può soddisfare le esigenze di analisi sia per AMP che per FIA simultaneamente. Per ulteriori informazioni sull'implementazione del tracciamento su FIA, vedi <a href="../../implement/js-implementation/analytics-facebook-instant-articles.md#concept_AC9AD1431CD14F919E329A161A80AA08" format="dita" scope="local"> Facebook Instant Articles </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

