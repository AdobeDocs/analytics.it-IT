---
title: Implementazione con Facebook Instant Articles
description: Implementate Adobe  Analytics nelle pagine Facebook Instant Article.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---


# Implementazione con Facebook Instant Articles

Gli articoli istantanei di Facebook consentono agli editori di creare articoli interattivi veloci su Facebook. Gli articoli istantanei possono caricare il contenuto fino a 10 volte più rapidamente del Web per dispositivi mobili.

Potete incorporare Adobe  Analytics in Facebook Instant Articles per monitorare il comportamento dei visitatori. Poiché il contenuto dell&#39;editore si trova all&#39;interno dell&#39;app Facebook e non nei siti Web dell&#39;editore, l&#39;approccio basato sui tag è leggermente diverso dall&#39;implementazione standard  Analytics.

## Flusso di lavoro

Il flusso di lavoro globale per implementare Adobe  Analytics è il seguente:

1. Creare una `stats.html` pagina. Codifica questa pagina per estrarre i parametri della stringa di query dall’URL e assegnare ogni parametro a una variabile Analytics 
1. Ospitare la `stats.html` pagina sul server Web
1. Implementare  Analytics nell&#39;articolo Facebook Instant Article facendo riferimento al `stats.html` file in un iframe
1. Includi parametri di stringa query nell&#39; `src` attributo iframe

### Passaggio 1: Creare una `stats.html` pagina

Il codice HTML di esempio riportato di seguito può essere utilizzato per acquisire le statistiche dagli articoli istantanei. Questo file è in genere ospitato su uno dei server Web della tua azienda. Ogni volta che viene caricato un articolo istantaneo, il file viene caricato in un iframe, il che attiva l&#39;invio di dati ad Adobe.

```html
<html>
  <head>
    <title>Facebook Stats</title>
      <script language="javaScript" type="text/javascript" src="VisitorAPI.js"></script>
      <script language="javaScript" type="text/javascript" src="AppMeasurement.js"></script>
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
      s.visitor = visitor;

      s.pageName = s.Util.getQueryParam("pageName");
      s.pageURL = document.referrer; // The referrer to the utility page is the parent frame
      s.campaign = s.Util.getQueryParam("cmpId");
      s.eVar1 = "Facebook Instant Article";
      s.eVar2 = s.Util.getQueryParam("eVar2");

      s.t();
    </script>
  </body>
</html>
```

### Passaggio 2: Ospitare la `stats.html` pagina sul server Web

Adobe consiglia di ospitare la `stats.html` pagina insieme all’ultima versione di `AppMeasurement.js` e `VisitorAPI.js`. Collabora con i team tecnici appropriati della tua organizzazione per ospitare il file nella posizione corretta.

### Passaggio 3: Riferimento `stats.html` su ogni pagina Facebook Instant Article

Quando create contenuto Facebook Instant Article, incorporate il contenuto HTML di analisi in un iframe. Ad esempio:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Passaggio 4: Impostazione del tracciamento personalizzato delle variabili e degli eventi

Le variabili e gli eventi personalizzati possono essere tracciati all&#39;interno dell&#39;HTML di analisi attraverso due approcci diversi:

* Includi valori variabili ed eventi direttamente nella `stats.html` pagina. Le variabili definite qui sono la scelta migliore per i valori generalmente identici per tutti gli articoli istantanei di Facebook.
* Includete i valori delle variabili come parte di una stringa di query che fa riferimento all&#39;iframe. Questo metodo consente di inviare valori variabili dall’articolo istantaneo di Facebook all’iframe  codice Analytics.

L&#39;esempio seguente mostra diverse variabili personalizzate incluse in una stringa di query. Il codice JavaScript all&#39;interno `stats.html` controllerebbe quindi la stringa di query utilizzando `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>La dimensione Referente non viene tracciata automaticamente a causa della natura di iframe. Accertatevi di includere questa dimensione come parte della stringa di query per tenerla traccia.

## Articoli istantanei di Facebook e privacy

Fintanto che la pagina HTML  Analytics è ospitata sul server Web, Adobe supporta l&#39;informativa sulla privacy esistente in tutti gli articoli istantanei di Facebook. Se un utente rinuncia al tracciamento sul sito principale, rinuncia anche al tracciamento su tutti gli articoli istantanei di Facebook. La pagina dell&#39;utility supporta anche il servizio Adobe Experience Cloud Identity Service, in modo da poter integrare i dati Facebook Instant Article con il resto dell&#39;Experience Cloud .
