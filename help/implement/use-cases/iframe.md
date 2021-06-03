---
title: Utilizzare AppMeasurement con gli iframe
description: Accedi alle variabili di Adobe Analytics all’interno di un iframe o di una pagina padre durante un iframe.
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 2%

---

# Utilizzare AppMeasurement con gli iframe

Puoi fare riferimento a variabili AppMeasurement da iframe figlio e padre. È necessario definire tutte le variabili nella stessa posizione in cui si trova la libreria AppMeasurement. Gli esempi seguenti spiegano come impostare variabili e metodi di base di AppMeasurement all&#39;interno e all&#39;esterno di un iframe.

Se utilizzi Adobe Experience Platform Launch, assicurati che l’oggetto tracker sia accessibile a livello globale. Consulta [Panoramica dell’estensione Adobe Analytics](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html) nella guida utente di Launch.

>[!CAUTION]
>
>Evita di includere le librerie AppMeasurement sia su una pagina padre che su un iframe. In questo modo si rischia di inviare più richieste di immagini, gonfiare i rapporti e aumentare le chiamate al server fatturabili.

## Accedere ad AppMeasurement che si trova in un iframe

È possibile accedere alle variabili AppMeasurement tramite l&#39;oggetto iframe. Questi esempi impostano [pageName](../vars/page-vars/pagename.md) e richiamano il metodo [t()](../vars/functions/t-method.md) utilizzando due modi diversi per fare riferimento all&#39;oggetto iframe.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Accedere ad AppMeasurement dall&#39;interno di un iframe

Puoi accedere alle variabili AppMeasurement da una pagina padre direttamente da un iframe. Questo esempio imposta [pageName](../vars/page-vars/pagename.md) e chiama il metodo [t()](../vars/functions/t-method.md) utilizzando la proprietà [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp).

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Utilizzare `postMessage` e i listener di eventi

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

* Come con altri codici JavaScript, gli iframe possono comunicare solo quando i domini e il protocollo corrispondono. Questi esempi non funzionano se il contenuto dell’iframe si trova in un dominio diverso da quello principale.
* Se AppMeasurement risiede in un iframe, la variabile [`referrer`](../vars/page-vars/referrer.md) è impostata sull&#39;URL principale, non sull&#39;URL effettivo di riferimento. Puoi impostare manualmente la variabile `referrer` per risolvere il problema.
* Il [debugger Adobe Experience Cloud](https://docs.adobe.com/content/help/it-IT/experience-cloud/user-guides/home.translate.html) non riconosce le richieste di immagini attivate all&#39;interno di iframe.
* Activity Map non visualizza la mappa di calore sui collegamenti selezionati all’interno di iframe. Viene invece evidenziato l’intero iframe.
