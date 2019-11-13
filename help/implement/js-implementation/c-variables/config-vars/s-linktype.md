---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.linkType

Contiene l’eventuale tipo di collegamento determinato automaticamente. È possibile impostare uno dei seguenti parametri:

    * `d` (download)
    * `e` (uscita)
    * `o` (personalizzato/altro)

Questo è il `pe` parametro nella richiesta di immagine. Se impostata con `linkURL` o `linkName`, una chiamata server viene inviata come collegamento di download, personalizzato o uscita.

*Nota: La variabile[`pageName`](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/optimize-implementation/page-naming-strategies.html)non può essere impostata per il download di un file, per il collegamento di uscita o per il collegamento personalizzato, perché ogni tipo di collegamento non è una visualizzazione di pagina e non dispone di un nome di pagina associato.*


**Esempio**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```
