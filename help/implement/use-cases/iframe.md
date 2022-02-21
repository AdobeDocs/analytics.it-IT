---
title: Utilizzare AppMeasurement con gli iframe
description: Accedi alle variabili di Adobe Analytics all’interno di un iframe o di una pagina padre durante un iframe.
feature: Implementation Basics
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 2%

---

# Utilizzare AppMeasurement con gli iframe

Puoi fare riferimento a variabili AppMeasurement da iframe figlio e padre. È necessario definire tutte le variabili nella stessa posizione in cui si trova la libreria AppMeasurement. Gli esempi seguenti spiegano come impostare variabili e metodi di base di AppMeasurement all&#39;interno e all&#39;esterno di un iframe.

Se utilizzi i tag in Adobe Experience Platform, accertati che l’oggetto tracker sia accessibile a livello globale. Vedi [Panoramica dell&#39;estensione Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html).

>[!CAUTION]
>
>Evita di includere le librerie AppMeasurement sia su una pagina padre che su un iframe. In questo modo si rischia di inviare più richieste di immagini, gonfiare i rapporti e aumentare le chiamate al server fatturabili.

## Accedere ad AppMeasurement che si trova in un iframe

È possibile accedere alle variabili AppMeasurement tramite l&#39;oggetto iframe. Questi esempi sono impostati [pageName](../vars/page-vars/pagename.md) e chiama [t(), metodo](../vars/functions/t-method.md) utilizzando due modi diversi per fare riferimento all&#39;oggetto iframe.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Accedere ad AppMeasurement dall&#39;interno di un iframe

Puoi accedere alle variabili AppMeasurement da una pagina padre direttamente da un iframe. Questo esempio imposta [pageName](../vars/page-vars/pagename.md) e chiama [t(), metodo](../vars/functions/t-method.md) utilizzando [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp) proprietà.

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Utilizzo `postMessage` e ascoltatori di eventi

In alternativa, puoi utilizzare `postMessage` e ascoltatori di eventi per impostare le variabili. Questo metodo non richiede un riferimento diretto a un iframe.

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
* Se AppMeasurement risiede in un iframe, la [`referrer`](../vars/page-vars/referrer.md) è impostata sull&#39;URL principale, non sull&#39;URL effettivo di riferimento. Puoi impostare manualmente la variabile `referrer` per risolvere il problema.
* La [Debugger Adobe Experience Cloud](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it) non riconosce le richieste di immagini attivate all’interno di iframe.
* Activity Map non visualizza la mappa di calore sui collegamenti selezionati all’interno di iframe. Viene invece evidenziato l’intero iframe.
