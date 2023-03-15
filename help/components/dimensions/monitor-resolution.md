---
title: Risoluzione monitor
description: Risoluzione in pixel del monitor del visitatore.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 2%

---

# Risoluzione monitor

La dimensione &quot;Risoluzione monitor&quot; mostra l&#39;altezza e la larghezza dello schermo attivo in pixel. Questa dimensione è utile quando desideri comprendere dove si trova la &quot;piega&quot; sul sito per i visitatori o quanto i visitatori possono fare la loro finestra del browser. Sapere dove si trova la piega può consentirti di ottimizzare il contenuto da visualizzare.

Questa dimensione è diversa dall’altezza e dalla larghezza del browser. Altezza/larghezza browser è il numero di pixel all’interno dello spazio visualizzabile del browser, mentre risoluzione monitor è il numero di pixel dell’intero monitor. Se desideri vedere la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Le dimensioni del browser sono sempre inferiori alla risoluzione del monitor, poiché non includono la navigazione o i bordi del browser.

## Popola questa dimensione con i dati

Questa dimensione recupera i dati da [`s` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `screen.width` e `screen.height` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), assicurati di includere i `s` parametro della stringa di query nelle richieste di immagini.

## Elementi dimensionali

Gli elementi di Dimension includono tutte le risoluzioni del monitor raccolte. I valori di esempio includono `1920 x 1080`, `1366 x 768`, e `1280 x 720`.
