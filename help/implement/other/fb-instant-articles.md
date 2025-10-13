---
title: Implementazione con gli articoli istantanei di Facebook
description: Implementare Adobe Analytics sulle pagine di articolo istantaneo di Facebook.
feature: Implementation Basics
exl-id: 2189f70d-32f0-4137-9d53-7acab0f15e6c
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Implementazione con gli articoli istantanei di Facebook

Gli articoli istantanei di Facebook consentono agli editori di creare articoli interattivi e veloci su Facebook. Gli articoli istantanei possono caricare i contenuti fino a 10 volte più rapidamente rispetto al web mobile.

Puoi incorporare Adobe Analytics sugli articoli istantanei di Facebook per monitorare il comportamento dei visitatori. Poiché il contenuto dell’editore si trova all’interno dell’app Facebook e non sui siti web dell’editore, l’approccio basato sui tag è leggermente diverso rispetto a un’implementazione standard di Analytics.

## Flusso di lavoro

Il flusso di lavoro generale per l’implementazione di Adobe Analytics è il seguente:

1. Crea una pagina `stats.html`. Crea un codice per questa pagina per richiamare i parametri della stringa di query dall’URL e assegnare ciascun parametro a una variabile di Analytics
1. Ospita la pagina `stats.html` nel server Web
1. Implementare Analytics sull&#39;articolo istantaneo di Facebook facendo riferimento al file `stats.html` in un iframe
1. Includi parametri di stringa di query nell’attributo iframe `src`

### Passaggio 1: creare una pagina `stats.html`

Il HTML di esempio riportato di seguito può essere utilizzato per acquisire statistiche dagli articoli istantanei. In genere questo file è ospitato su uno dei server web della tua azienda. Ogni volta che viene caricato un Instant Article, il file viene caricato in un iframe, il che attiva l’invio di dati ad Adobe.

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

### Passaggio 2: ospita la pagina `stats.html` sul server Web

Adobe consiglia di ospitare la pagina `stats.html` insieme all&#39;ultima versione di `AppMeasurement.js` e `VisitorAPI.js`. Collabora con i team tecnici appropriati della tua organizzazione per ospitare il file nella posizione corretta.

### Passaggio 3: fai riferimento a `stats.html` in ogni pagina di articolo istantaneo di Facebook

Durante la creazione di contenuti di Facebook Instant Article, incorpora il contenuto di Analytics HTML all’interno di un iframe. Ad esempio:

```html
<iframe class="no-margin" src="https://example.com/stats.html" height="0"></iframe>
```

### Passaggio 4: impostare la variabile personalizzata e il tracciamento degli eventi

Le variabili e gli eventi personalizzati possono essere tracciati all’interno del HTML di analisi attraverso due approcci diversi:

* Includere valori ed eventi variabili direttamente nella pagina `stats.html`. Le variabili qui definite sono ideali per i valori che sono in genere gli stessi per tutti gli articoli istantanei di Facebook.
* Includi i valori delle variabili come parte di una stringa di query che fa riferimento all’iframe. Questo metodo ti consente di inviare valori di variabili dall’articolo istantaneo di Facebook al codice di Analytics che ospita l’iframe.

L’esempio seguente mostra diverse variabili personalizzate incluse in una stringa di query. Il JavaScript all&#39;interno di `stats.html` verificherà quindi la stringa di query utilizzando `s.Util.getQueryParam()`.

```html
<iframe class="no-margin" src="https://example.com/stats.html?eVar2=Dynamic%20article%20title&pageName=Example%20article%20name&cmpId=exampleID123" height="0"></iframe>
```

>[!NOTE]
>
>La dimensione Referrer non viene tracciata automaticamente a causa della natura degli iframe. Se desideri tenere traccia di questa dimensione, assicurati di includerla nella stringa di query.

## Articoli istantanei e privacy di Facebook

Se la pagina HTML di Analytics è ospitata sul server web, Adobe supporta l’informativa sulla privacy esistente in tutti gli articoli istantanei di Facebook. Se un utente rinuncia al tracciamento sul sito principale, rinuncia anche al tracciamento su tutti gli articoli istantanei di Facebook. La pagina dell’utility supporta anche il servizio Adobe Experience Cloud Identity, in modo da poter integrare i dati degli articoli istantanei di Facebook con il resto di Experience Cloud.
