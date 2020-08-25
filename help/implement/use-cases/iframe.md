---
title: Usa AppMeasurement con iframe
description: Accedete  variabili Adobe Analytics all'interno di un iframe o di una pagina padre mentre vi trovate in un iframe.
translation-type: tm+mt
source-git-commit: 355985a6baa1a1112e75446012be72f5c0a1d0c2
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 6%

---


# Usa AppMeasurement con iframe

Potete fare riferimento alle variabili AppMeasurement sia dagli iframe figlio che da quelli padre. È necessario definire tutte le variabili nella stessa posizione in cui esiste la libreria AppMeasurement. Gli esempi seguenti spiegano come impostare le variabili e i metodi di base di AppMeasurement all&#39;interno e all&#39;esterno di un iframe.

Se utilizzate  Adobe Experience Platform Launch, accertatevi che l&#39;oggetto di tracciamento sia accessibile a livello globale. Consultate [panoramica](https://docs.adobe.com/content/help/it-IT/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) dell’estensione Adobe Analytics nella guida utente di Launch.

>!![CAUTION]
Evitate di includere le librerie AppMeasurement in una pagina padre e in un iframe. In questo modo si rischia di inviare più richieste di immagini, di gonfiare i report e di aumentare le chiamate ai server fatturabili.

## Accesso ad AppMeasurement che si trova in un iframe

Potete accedere alle variabili AppMeasurement tramite l&#39;oggetto iframe. Questi esempi impostano [pageName](../vars/page-vars/pagename.md) e richiamano il metodo [](../vars/functions/t-method.md) t() utilizzando due modi diversi per fare riferimento all&#39;oggetto iframe.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Accesso ad AppMeasurement dall&#39;interno di un iframe

Puoi accedere alle variabili AppMeasurement su una pagina padre da un iframe. Questo esempio imposta [pageName](../vars/page-vars/pagename.md) e chiama il metodo [](../vars/functions/t-method.md) t() utilizzando la [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp) proprietà.

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Utilizzo `postMessage` e listener di eventi

In alternativa, è possibile utilizzare i listener di eventi `postMessage` e per impostare le variabili. Questo metodo non richiede un riferimento diretto a un iframe.

```js
// Place this code in your parent window
function listenMessage(e) {
    if(e.data == "Example page view call") {
        s.pageName = "Page name using postMessage";
        s.t();
    }
}
window.addEventListener("message", listenMessage, false);

// Place this code in the iframe
window.top.postMessage("Example page view call","https://example.com");
```

## Limitazioni

* Come con altri codici JavaScript, gli iframe possono comunicare solo se i domini e il protocollo corrispondono. Questi esempi non funzionano se il contenuto iframe risiede in un dominio diverso da quello del padre.
* Se AppMeasurement risiede in un iframe, la [`referrer`](../vars/page-vars/referrer.md) variabile viene impostata sull’URL principale, non sull’URL di provenienza effettivo. Potete impostare manualmente la `referrer` variabile per risolvere il problema.
* Il debugger [](https://docs.adobe.com/content/help/it-IT/debugger/using/experience-cloud-debugger.html) Adobe Experience Cloud non riconosce le richieste di immagini attivate all&#39;interno di iframe.
*  Activity Map non visualizza la mappa di calore sui collegamenti selezionati all&#39;interno di iframe. Viene invece evidenziato l’intero iframe.
