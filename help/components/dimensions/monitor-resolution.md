---
title: Risoluzione monitor
description: La risoluzione del monitor del visitatore in pixel.
translation-type: tm+mt
source-git-commit: ad206649488a1a2dead717cdfe53f4c630ba3f3b
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 1%

---


# Risoluzione monitor

La dimensione &quot;Risoluzione monitor&quot; mostra l’altezza e la larghezza della visualizzazione attiva, in pixel. Questa dimensione è utile quando si desidera capire dove si trova la &quot;piega&quot; sul sito per i visitatori, o quanto i visitatori possono fare la loro finestra del browser. Comprendere dove si trova la piega può consentire di ottimizzare il contenuto per la visualizzazione.

Questa dimensione è diversa dall’altezza e dalla larghezza del browser. Altezza/larghezza del browser indica il numero di pixel all’interno dello spazio visibile del browser, mentre la risoluzione del monitor corrisponde al numero di pixel dell’intero monitor. Se desiderate visualizzare la differenza tra queste due variabili sul computer, aprite la console del browser (F12 nella maggior parte dei browser) e copiate e incollate il seguente codice nella console:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Le dimensioni del browser sono sempre più piccole rispetto alla risoluzione del monitor, poiché le dimensioni del browser non includono la navigazione o i bordi del browser.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`s` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `screen.width` e `screen.height` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite Adobe Experience Platform Launch), questa dimensione non è disponibile. Se utilizzate un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertatevi di includere il parametro della stringa di `s` query nelle richieste di immagine.

## Valori dimensione

I valori delle dimensioni includono tutte le risoluzioni del monitor raccolte. I valori di esempio includono `1920 x 1080`, `1366 x 768`e `1280 x 720`.
