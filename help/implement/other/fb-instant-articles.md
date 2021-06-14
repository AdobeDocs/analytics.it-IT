---
title: Implementazione con gli articoli istantanei di Facebook
description: Implementa Adobe Analytics sulle pagine degli articoli istantanei di Facebook.
exl-id: 2189f70d-32f0-4137-9d53-7acab0f15e6c
source-git-commit: de0424db27f9d1a3ce07632df8fd5e76b4d7bb4c
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Implementazione con gli articoli istantanei di Facebook

Gli articoli istantanei di facebook consentono agli editori di creare articoli interattivi veloci su Facebook. Gli articoli istantanei possono caricare i contenuti fino a 10 volte più rapidamente del web mobile.

Puoi incorporare Adobe Analytics sugli articoli istantanei di Facebook per monitorare il comportamento dei visitatori. Poiché il contenuto dell’editore si trova all’interno dell’app Facebook e non sui siti web dell’editore, l’approccio relativo ai tag è leggermente diverso dall’implementazione standard di Analytics.

## Flusso di lavoro

Il flusso di lavoro complessivo per l’implementazione di Adobe Analytics è il seguente:

1. Crea una pagina `stats.html`. Codifica questa pagina per estrarre i parametri della stringa di query dall’URL e assegna ogni parametro a una variabile di Analytics
1. Hosting della pagina `stats.html` sul server web
1. Implementa Analytics sull’articolo istantaneo di Facebook facendo riferimento al file `stats.html` in un iframe
1. Includi parametri di stringa di query nell&#39;attributo iframe `src`

### Passaggio 1: Creare una pagina `stats.html`

Il codice HTML di esempio riportato di seguito può essere utilizzato per acquisire statistiche dagli articoli istantanei. Questo file è in genere ospitato su uno dei server web della tua azienda. Ogni volta che viene caricato un articolo istantaneo, questo carica il file in un iframe, il che attiva l’invio di dati ad Adobe.

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

### Passaggio 2: Hosting della pagina `stats.html` sul server web

Adobe consiglia di ospitare la pagina `stats.html` accanto all’ultima versione di `AppMeasurement.js` e `VisitorAPI.js`. Collabora con i team tecnici appropriati della tua organizzazione per ospitare il file nella posizione corretta.

### Passaggio 3: Riferimento `stats.html` su ogni pagina Facebook Instant Article

Durante la creazione del contenuto Facebook Instant Article, incorpora il contenuto HTML di analytics all’interno di un iframe. Ad esempio:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Passaggio 4: Imposta il tracciamento personalizzato delle variabili e degli eventi

Le variabili e gli eventi personalizzati possono essere tracciati all’interno dell’HTML di analytics attraverso due approcci diversi:

* Includi valori ed eventi variabili direttamente nella pagina `stats.html`. Le variabili qui definite sono consigliate per i valori che in genere sono gli stessi per tutti gli articoli istantanei di Facebook.
* Includi i valori delle variabili come parte di una stringa di query che fa riferimento all&#39;iframe. Questo metodo ti consente di inviare i valori delle variabili dall’articolo istantaneo di Facebook all’iframe che ospita il codice Analytics.

L’esempio seguente mostra diverse variabili personalizzate incluse in una stringa di query. Il JavaScript all’interno di `stats.html` controllerebbe quindi la stringa di query utilizzando `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>La dimensione referente non viene tracciata automaticamente a causa della natura degli iframe. Assicurati di includere questa dimensione come parte della stringa di query se desideri tenerla traccia.

## Articoli istantanei e privacy di facebook

Se la pagina HTML di Analytics è ospitata sul server web, Adobe supporta la tua politica sulla privacy esistente in tutti gli articoli istantanei di Facebook. Se un utente rinuncia al tracciamento sul sito principale, rifiuta anche il tracciamento su tutti gli articoli istantanei di Facebook. La pagina dell’utility supporta anche il servizio Adobe Experience Cloud Identity, in modo da poter integrare i dati di Facebook Instant Article con il resto dell’Experience Cloud.
