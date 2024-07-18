---
title: Usa AppMeasurement con iframe
description: Accedi alle variabili di Adobe Analytics all’interno di un iframe o di una pagina padre mentre si trova all’interno di un iframe.
feature: Implementation Basics
exl-id: 59b9cd4f-8599-41ee-8b54-a6a556198ecd
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 1%

---

# Usa AppMeasurement con iframe

È possibile fare riferimento a variabili di AppMeasurement da iframe figlio e padre. È necessario definire tutte le variabili nella stessa posizione in cui esiste la libreria AppMeasurement. Negli esempi seguenti viene illustrato come impostare variabili e metodi di AppMeasurement di base all&#39;interno e all&#39;esterno di un iframe.

Se utilizzi i tag in Adobe Experience Platform, accertati che l’oggetto tracker sia accessibile a livello globale. Consulta [Panoramica dell&#39;estensione Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=it).

>[!CAUTION]
>
>Evita di includere librerie AppMeasurement sia su una pagina padre che su un iframe. In questo modo si comportano rischi per l’invio di più richieste di immagini, si gonfiano i rapporti e si aumentano le chiamate al server fatturabili.

## AppMeasurement di accesso che risiede in un iframe

È possibile accedere alle variabili AppMeasurement tramite l’oggetto iframe. In questi esempi viene impostato [pageName](../vars/page-vars/pagename.md) e viene chiamato il metodo [t()](../vars/functions/t-method.md) utilizzando due modi diversi per fare riferimento all&#39;oggetto iframe.

```js
// Reference AppMeasurement code that resides within an iframe and send an image request
document.getElementById('targetFrame').contentWindow.s.pageName="Page name within iframe";
document.getElementById('targetFrame').contentWindow.s.t();

// An alternate method to the above if there's only one iframe on the page
window.frames[0].contentWindow.s.pageName = "Page name within iframe";
window.frames[0].contentWindow.s.t();
```

## Accedere all’AppMeasurement dall’interno di un iframe

Puoi accedere alle variabili AppMeasurement su una pagina padre da un iframe. Questo esempio imposta [pageName](../vars/page-vars/pagename.md) e chiama il metodo [t()](../vars/functions/t-method.md) utilizzando la proprietà [`parent`](https://www.w3schools.com/jsref/prop_win_parent.asp).

```js
// Reference AppMeasurement code on a parent page from within an iframe and send an image request
parent.s.pageName = "Page Name on Hosted Window";
parent.s.t();
```

## Usa `postMessage` e listener di eventi

In alternativa, è possibile utilizzare `postMessage` e i listener di eventi per impostare le variabili. Questo metodo non richiede un riferimento diretto a un iframe.

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

* Come con altri codici JavaScript, gli iframe possono comunicare solo quando i domini e il protocollo corrispondono. Questi esempi non funzionano se il contenuto dell’iframe risiede in un dominio diverso da quello dell’elemento principale.
* Se AppMeasurement risiede in un iframe, la variabile [`referrer`](../vars/page-vars/referrer.md) viene impostata sull&#39;URL padre, non sull&#39;URL di riferimento effettivo. È possibile impostare manualmente la variabile `referrer` per risolvere il problema.
* Il [debugger di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it) non riconosce le richieste di immagini attivate negli iframe.
* Activity Map non visualizza la mappa di calore sui collegamenti su cui è stato fatto clic all’interno degli iframe. Viene invece evidenziato l’intero iframe.
