---
description: Implementare il progetto accelerato Pagine mobili (AMP) in Adobe Analytics.
keywords: Implementazione di Analytics; amp; amp-analytics; modello adobeanalytics; adobeanalytics_ nativeconfig, modello; monitoraggio dei clic; gonfiatura dei visitatori; servizio id
seo-description: Implementare il progetto accelerato Pagine mobili (AMP) in Adobe Analytics.
seo-title: Accelerated Mobile Pages
solution: Analytics
title: Accelerated Mobile Pages
topic: Sviluppatore e implementazione
uuid: c 86 e 4 a 80-7191-4 ee 7-ab 20-787730026 c 4 b
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Accelerated Mobile Pages

Implementare il progetto accelerato Pagine mobili (AMP) in Adobe Analytics.

AMP is an [open source project](https://www.ampproject.org/) that lets you build web pages for static content that renders quickly. Questa funzione è ideale per coloro che desiderano creare e pubblicare contenuti ottimizzati per dispositivi mobili per poi caricarli istantaneamente ovunque. Gli argomenti includono:

* [Come funziona](../../implement/js-implementation/accelerated-mobile-pages.md#section_21C2836D63104794BCEBEECB6593AFBF)
* [Utilizzo del tag di amp-analytics con il modello "adobeanalytics"](../../implement/js-implementation/accelerated-mobile-pages.md#section_2E4EBF4EF623440D95DE98E78C47244E)
* [Utilizzo del tag di amp-analytics con il modello "adobeanalytics_ nativeconfig"](../../implement/js-implementation/accelerated-mobile-pages.md#section_3556B68304A4492991F439885727E9FF)
* [Riepilogo](../../implement/js-implementation/accelerated-mobile-pages.md#section_4D8ED26084F249738A5C2BC66B933A07)
* [Domande frequenti](../../implement/js-implementation/accelerated-mobile-pages.md#section_5F57AA2DE0C5452FB65241058A924C73)

**Documentazione ed esempi aggiuntivi**

* External, open-source AMP project [documentation](https://www.ampproject.org/docs/get_started/about-amp.html)
* [Esempi di configurazione](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml)

## Come funziona {#section_21C2836D63104794BCEBEECB6593AFBF}

Gli AMP dispongono di pagine HTML con tag speciale memorizzate nella cache sul Web su diverse reti di distribuzione dei contenuti (CDNS) di partner tecnologici e editori partecipanti. Il contenuto AMP viene distribuito dalla più vicina sorgente possibile con la latenza minima possibile. In questo modo si crea un'analisi di analisi perché non è mai possibile verificare se il contenuto di un editore sarà caricato da e i cookie di terze parti saranno problematici per l'identificazione dei visitatori.

Inoltre, per ridurre notevolmente lo spessore delle pagine e accelerare il caricamento delle pagine, gli AMP limitano l'utilizzo di javascript e cookie. Anche se questo è vantaggioso per il dispositivo mobile, perché riduce la quantità di elaborazione, introduce problematiche per misurare con precisione i visitatori unici e comprendere l'acquisizione e la conservazione degli utenti.

To solve these problems, Adobe has collaborated with AMP partners and publishers on two options that a publisher can choose from to best suit their business needs, both using the `amp-analytics` tag. The first approach uses the `"adobeanalytics"` tracking template to construct the Analytics request directly from within the AMP. The second approach uses the `"analytics_nativeConfig"` tracking template, which uses an iframe containing the AppMeasurement code you deploy on your normal site. La tabella seguente fornisce un'idea dei professionisti e delle s di ogni approccio.

|  | **modello "adobeanalytics"** | ** "adobeanalytics_ nativeconfig" template** |
|---|---|---|
| Conteggio visitatore/visita (nella suite di rapporti esistente) | Alta inflazione | Inflazione minima |
| Utilizzo di una suite di rapporti separata | Consigliato | Non necessario |
| Nuovi visitatori a confronto | Non supportato | Supportate |
| Servizio ID visitatori | Non supportato | Supportate |
| Tracciamento video e collegamento | Supporto parziale | Non ancora supportato |
| Difficoltà di implementazione | Un po' difficile | Relativamente semplice |
| [!DNL Experience Cloud] integrazioni | Non supportato | Supportato con le avvertenze |

## Using the amp-analytics tag with the "adobeanalytics" template {#section_2E4EBF4EF623440D95DE98E78C47244E}

The `"adobeanalytics"`tracking template utilizes the `amp-analytics` tag to construct a tracking request directly. Using the `"adobeanalytics"` template in the `amp-analytics` tag, you can specify hit requests that fire on specific page events, like the page becoming visible or on a click (and in the future, video views and more). Gli eventi Click possono essere personalizzati per essere applicati a determinati ID di elementi o classi specificando un selettore. Adobe has made this easy to set up using the `"adobeanalytics"` template specifically designed for [!DNL Adobe Analytics]. You can load the template by adding `type="adobeanalytics"` to the amp-analytics tag.

In the following code example, there are two triggers defined: `pageLoad` and `click`. The `pageLoad` trigger will fire when the document becomes visible and will include the `pageName` variable as defined in the `vars section`. The second trigger `click` will fire when a button is clicked. `eVar 1` verranno impostati per questo evento con il valore `button clicked`.

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

In the `click` trigger, you can specify a selector to ensure that whenever the specific DOM element is clicked (in this case, any button), the `buttonClick` request is fired and will be automatically set to denote this hit as a non-stage event (i.e. `trackLink` call).

`amp-analytics` Inoltre, supporta una serie di sostituzioni variabili in modo che AMP possa fornire valori di dati a cui è a conoscenza. You can learn all about those and more by visiting: [amp-analytics variable documentation](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md).

Se vuoi incorporare qualsiasi variabile di tecnologia o DOM (ad esempio browser, dimensioni dello schermo, dispositivo, referente ecc.) è necessario aggiungerli esplicitamente a qualsiasi richiesta, in quanto non vengono generati automaticamente. Documentation on each of our available query string parameters used for tracking can be found [here](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=query_parameters).

If you inspect the hits created by amp-analytics, you will notice that in each request, Adobe has included the `vid` query parameter. We set the `vid` based on a built-in AMP function to set a custom Analytics cookie ID named `adobe_amp_id`. This ID is independent of any other ID being set by [!DNL Adobe Analytics] elsewhere (e.g. `s_vi cookie`) and creates new visitors in any report suite the hits are sent to.

Alcuni aspetti sono noti. Quando utilizzate il tag di amp-analytics come indicato sopra, i visitatori saranno indipendenti dal normale tracciamento e, poiché il AMP può essere caricato da una rete di distribuzione dei contenuti, otterrete un visitatore univoco per ogni rete CDN su cui il visitatore vede questo AMP (quindi la gonfiatura dei visitatori indicata in precedenza). For this reason, Adobe recommends that if you use the `"adobeanalytics"` template for `amp-analytics`, you put your data into a separate report suite specific to AMP. Also, the [!DNL Experience Cloud] ID service (formerly, *`visitor ID service`*) is not supported using this method, so if your business requires additional [!DNL Experience Cloud] integrations, or will in the future, this is probably not the option for you.

Finally, and perhaps most importantly, this `amp-analytics` solution requires that the tracking server you specify in the `vars` section matches the tracking server on your main site, so that your existing privacy policy controls are respected. In caso contrario, dovete creare un'informativa sulla privacy separata solo per gli AMP.

## Using the amp-analytics tag with the "adobeanalytics_nativeConfig" template {#section_3556B68304A4492991F439885727E9FF}

`"adobeanalytics_nativeConfig"` Il tag è più semplice da implementare, in quanto utilizza la stessa metodologia utilizzata per le normali pagine Web. To accomplish this, add the following to your `amp-analytics` tag:

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

This approach sends data to a utility web page via special query string parameters added to the `iframeMessage` request parameter. In this case, notice that we have added the `ampdocUrl AMP` variable, and the `documentReferrer` to the query string parameters `pageURL`, and refer respectively to the `iframeMessage` request above. These extra query string parameters can be named whatever you like, as long as your [!DNL stats.html] page (shown below) is configured to collect the appropriate data from them.

The `"adobeanalytics_nativeConfig"` template also adds query string parameters based on the variables listed in the `extraUrlParams` section of the amp-analytics tag. In this case, you can see we have specified the `pageName` and `v1` parameters , which will be used by our [!DNL stats.html] page.

Be aware that you can only use a single `amp-analytics` template at a time and can not use the `"adobeanalytics"` template as well as the `"adobeanalytics_nativeConfig"` template on the same AMP. Se si tenta di farlo, si potrebbe verificare un errore nella console del browser e il conteggio dei visitatori verrà gonfiato erroneamente.

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

As shown above, you can use or link to your existing [!DNL VisitorAPI.js] and [!DNL AppMeasurement.js] (as in our example), or whatever your existing implementation uses, then add the correct configuration parameters. To capture the correct values into the correct variables, you can use the provided `s.Util.getQueryParam` function to grab the value(s) that you passed in from the `iframeMessage` URL and set the appropriate variables, just as you would on a typical page. If you use tag management software like Adobe's [ [!DNL Dynamic Tag Manager] ](https://www.adobe.com/solutions/digital-marketing/dynamic-tag-management.html), the query string parameters should be straightforward to capture. In this case, `s.pageName` is set to the value we passed in the query string parameter `pageName`. Here, the page name would be set to *`Adobe Analytics Example 2`*.

>[!IMPORTANT]
>
>Due to restrictions on iframes in the AMP framework, your [!DNL stats.html] page must be hosted on a separate subdomain from the domain the AMP itself is hosted on. Il framework AMP non consente iframe dello stesso sottodominio su cui esiste la pagina AMP. For example, if your AMP is hosted on [!DNL amp.example.com], be sure to host your [!DNL stats.html] page on a separate subdomain such as [!DNL ampmetrics.example.com] or something similar.

Poiché la pagina di utilità è ospitata sul sito originale, non è necessario un lavoro aggiuntivo per supportare l'informativa sulla privacy esistente in tutti gli AMP. Questo significa che se un utente finale non rileva il tracciamento sul sito principale, anche questi vengono non tracciati su tutti i tuoi AMP, senza dover effettuare ulteriori passaggi. Using this utility page also means that AMP can support Adobe's [!DNL Experience Cloud] ID service so that you can integrate the measurement captured on your AMPs with the rest of the [!DNL Experience Cloud] (for targeted advertising using [!DNL Adobe Audience Manager] for example).

To reiterate, if your organization is not yet using the [!DNL Experience Cloud] ID service (or has tag management software like Adobe's [!DNL Dynamic Tag Manager]), you can tag the [!DNL stats.html] page however you want. Utilizza la tua implementazione esistente come punto di riferimento. The only difference from your standard implementation is that you will get the applicable data points from the amp-analytics `iframeMessage` URL (or [!DNL document.URL] from within the [!DNL stats.html] page ) for each of the variables you want to set. Also, if you want to use any of the [AMP specific variables](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md) (as mentioned above) like the AMP referrer or AMP page URL, please include them in the iframeMessage object as shown in our example above.

Come questa soluzione è flessibile, ci sono delle caratteristiche. Due to inherent restrictions in the `amp-analytics` `iframeMessage`, it can only be loaded on a page load once. This means you will not be able to do link tracking or video tracking with the `"adobeanalytics_nativeConfig"` template. Moreover, some DOM values that are typically captured automatically by our [!DNL AppMeasurement] code, such as `referrer` (which impacts the Search Engine Keyword reports, Referrer, and Referrer Type reports, or may include a marketing campaign tracking code) will have to be passed manually to the `iframeMessage` using whatever AMP variables [are available](https://github.com/ampproject/amphtml/blob/master/extensions/amp-analytics/analytics-vars.md). Per questo motivo, Adobe consiglia di impostare una variabile personalizzata con il valore AMP se inserite dati AMP in una suite di rapporti esistente, in modo da segmentare il traffico AMP quando visualizzate i report indicati. Questo significa che i rapporti tecnologici standard, come browser, dispositivo, dimensione dello schermo o risoluzione, funzionano automaticamente.

Infine, poiché l'iframe viene caricato come pagina separata e esegue completamente il javascript su quella pagina, AMP non è un formato leggero quanto lo standard AMP previsto. Per essere chiara, questo non influisce sul tempo di caricamento della pagina (l'iframe viene caricato dopo che la pagina è stata caricata), ma la CPU e la rete eseguiranno il rendering in modo leggermente più di quanto dovrebbero altrimenti, che potrebbero influenzare l'uniformità di scorrimento. In pratica, non abbiamo visto un grande impatto, ma stiamo lavorando con Google per ridurre al minimo l'impatto dell'esperienza dell'utente.

## Riepilogo {#section_4D8ED26084F249738A5C2BC66B933A07}

If you need click tracking and don't mind visitors being counted as entirely new visitors separate from your site, use the `"adobeanalytics"` tracking template, with our recommendation that you put the data into a *`separate report suite`*. If you need the [!DNL Experience Cloud] ID service, do not want visitor or visit inflation, and are okay with only firing Analytics on page load, we recommend using the `"adobeanalytics_nativeConfig"` solution.

Adobe Analytics è entusiasta di collaborare con Google e i nostri editori per portare le funzionalità di analisi leader del settore agli editori sul Web mobile in un'esperienza utente veloce e veloce. Sebbene queste due soluzioni offrano al momento i propri compromessi, ci impegniamo a costruire la soluzione a termine più lunga per rispondere all'analisi in evoluzione necessaria ai nostri clienti.

The AMP Project is moving fast and changes occur frequently, so check back [here](https://github.com/Adobe-Marketing-Cloud/mobile-services/tree/master/samples/mobile-web/amphtml) frequently for updates to our examples. Ciò che vi abbiamo presentato dovrebbe essere sufficiente per iniziare, ma si aspettano modifiche man mano che miglioriamo ulteriormente le integrazioni e quando più editori adottano AMP nel tempo.

In caso di domande o problemi, rivolgetevi al consulente Adobe o all'Assistenza clienti.

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
   <td colname="col1"> <p> Is video tracking available for either the <code> "adobeanalytics" </code> or <code> "adobeanalytics_nativeConfig" </code> template? </p> </td> 
   <td colname="col2"> <p> Purtroppo non ancora. Lo standard AMP supporta solo gli attivatori per «visible», «click» e «timer», e non supporta ancora le attivazioni esplicite per il tracciamento video che possono essere intercettate dal tag di amp-analytics. Also, because the <code> "adobeanalytics_nativeConfig" </code> tag can only be loaded once, it is not compatible with video viewing which occurs after the AMP has loaded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>You mention that visitor inflation is lower for the " <code> adobeanalytics_nativeConfig </code>" template in your comparison. Cosa significa? What would cause visitor inflation in either the <code> "adobeanalytics" </code> or the <code> “adobeanalytics_nativeConfig” </code> solution? </p> </td> 
   <td colname="col2"> <p>The <code> “adobeanalytics” </code> template does not allow Adobe Analytics to set a visitor identification cookie; this means all visits and visitors to your AMP page will be treated as a new and independent visit and visitor in your report suite. </p> <p>The <code> “adobeanalytics_nativeConfig” </code> template, however, allows the Adobe Analytics visitor identification cookie to be set in nearly all cases, except for new visitors using the Safari browser. Ciò significa che tutti i visitatori di Safari che non hanno visitato in precedenza il sito di un editore verranno ingranditi nel report di Adobe Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devo usare una suite di rapporti separata per gli AMP? </p> </td> 
   <td colname="col2"> <p>Consigliamo di utilizzare una suite di rapporti separata per gli AMP se utilizzi il modello adobeanalytics a causa del problema di gonfiamento visitatore/visita. Tuttavia, imposteremo anche la versione javascript su «AMP vx. X» dal modello di tag amp-analytics in modo da segmentare il traffico da una suite di rapporti combinata, se necessario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>What is the <span class="keyword"> Experience Cloud </span> ID service? È necessario? </p> </td> 
   <td colname="col2"> <p>The <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Identity Service </a> (formerly <span class="term"> visitor ID service </span>) enables <span class="keyword"> Experience Cloud </span> core services and allows integrations between different Adobe <span class="keyword"> Experience Cloud </span> solutions. If you have integrations with <span class="keyword"> Adobe Audience Manager </span> or <span class="keyword"> Adobe Target </span>, you are likely using this service. This service is also the foundation for many upcoming <span class="keyword"> Adobe Analytics </span> features. If you need ID service support or will need it in the future, we recommend using the <code> iframeMessage </code> solution. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>For the <code> "adobeanalytics_nativeConfig" </code> template, where should I host my utility page? </p> </td> 
   <td colname="col2"> <p>Lo standard AMP non consente il caricamento degli iframe dal dominio esatto e dal sottodominio della AMP stessa. Pertanto, si consiglia di ospitare la pagina di utilità su un sottodominio separato dal sito principale, in particolare se la società ha un proprio CDN che pianifica la memorizzazione nella cache di amps. For maximum compatibility, pick a subdomain such as <span class="filepath"> ampmetrics.publisher.com </span> that is apart from where the actual AMP content will reside. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Isn't this similar to <span class="keyword"> Facebook Instant Articles </span>? How do I setup <span class="keyword"> Adobe Analytics </span> with Facebook Instant Articles? </p> </td> 
   <td colname="col2"> <p> Gli articoli Instant Instant supportano una soluzione simile alla soluzione nativeconfig descritta sopra. Infatti, la pagina stats.html creata sopra può servire simultaneamente le tue esigenze di analisi sia AMP sia FIA. For more information on implementing tracking on FIA, see <a href="../../implement/js-implementation/analytics-facebook-instant-articles.md#concept_AC9AD1431CD14F919E329A161A80AA08" format="dita" scope="local"> Facebook Instant Articles </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

