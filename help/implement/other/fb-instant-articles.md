---
title: Implementazione con gli articoli istantanei Facebook
description: Implementare Adobe Analytics sulle pagine di Facebook Instant Article.
feature: Implementation Basics
exl-id: 2189f70d-32f0-4137-9d53-7acab0f15e6c
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Implementazione con gli articoli istantanei Facebook

Gli articoli istantanei di facebook consentono agli editori di creare articoli interattivi e veloci su Facebook. Gli articoli istantanei possono caricare i contenuti fino a 10 volte più rapidamente rispetto al web mobile.

Puoi incorporare Adobe Analytics sugli articoli istantanei di Facebook per monitorare il comportamento dei visitatori. Poiché il contenuto dell’editore si trova all’interno dell’app Facebook e non sui siti web dell’editore, l’approccio basato sui tag è leggermente diverso rispetto a un’implementazione standard di Analytics.

## Flusso di lavoro

Il flusso di lavoro generale per l’implementazione di Adobe Analytics è il seguente:

1. Creare un `stats.html` pagina. Crea un codice per questa pagina per richiamare i parametri della stringa di query dall’URL e assegnare ciascun parametro a una variabile di Analytics
1. Ospita il `stats.html` pagina sul server web
1. Implementare Analytics sull’articolo istantaneo di Facebook facendo riferimento al `stats.html` file in un iframe
1. Includere i parametri di stringa di query nell’iframe `src` attributo

### Passaggio 1: creare un `stats.html` pagina

Il HTML di esempio seguente può essere utilizzato per acquisire statistiche dagli articoli istantanei. In genere questo file è ospitato su uno dei server web della tua azienda. Ogni volta che viene caricato un Instant Article, il file viene caricato in un iframe, il che attiva l’invio di dati all’Adobe.

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
      var s_account = "examplersid1,examplersid2";
      var s_trackingServer = "example.data.adobedc.net";
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

### Passaggio 2: ospitare il `stats.html` pagina sul server web

L’Adobe consiglia di ospitare il tuo `stats.html` pagina insieme all’ultima versione di `AppMeasurement.js` e `VisitorAPI.js`. Collabora con i team tecnici appropriati della tua organizzazione per ospitare il file nella posizione corretta.

### Passaggio 3: riferimento `stats.html` su ogni pagina di Facebook Instant Article

Durante la creazione di contenuti Facebook Instant Article, incorpora il contenuto Analytics HTML all’interno di un iframe. Ad esempio:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Passaggio 4: impostare la variabile personalizzata e il tracciamento degli eventi

Le variabili e gli eventi personalizzati possono essere tracciati all’interno dei HTML di Analytics tramite due approcci diversi:

* Includere i valori delle variabili e gli eventi direttamente nel `stats.html` pagina. Le variabili qui definite sono indicate per valori che in genere sono uguali per tutti gli articoli istantanei di Facebook.
* Includi i valori delle variabili come parte di una stringa di query che fa riferimento all’iframe. Questo metodo consente di inviare valori di variabili dall’articolo istantaneo di Facebook all’iframe che ospita il codice di Analytics.

L’esempio seguente mostra diverse variabili personalizzate incluse in una stringa di query. JavaScript all’interno di `stats.html` controlla quindi la stringa di query utilizzando `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>La dimensione Referrer non viene tracciata automaticamente a causa della natura degli iframe. Se desideri tenere traccia di questa dimensione, assicurati di includerla nella stringa di query.

## Articoli istantanei e privacy di facebook

Se la pagina di Analytics HTML è ospitata sul server web, Adobe supporta l’informativa sulla privacy esistente in tutti gli articoli istantanei di Facebook. Se un utente rinuncia al tracciamento sul sito principale, rinuncia anche al tracciamento su tutti gli articoli istantanei di Facebook. La pagina dell’utility supporta anche il servizio Adobe Experience Cloud Identity, in modo da poter integrare i dati di Facebook Instant Article con il resto dell’Experience Cloud.
