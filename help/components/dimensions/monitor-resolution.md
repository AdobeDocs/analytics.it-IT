---
title: Risoluzione monitor
description: Risoluzione in pixel del monitor del visitatore.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: e3a1c1fde3809cb73b1bda091b8be43778515d1a
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 5%

---

# Risoluzione monitor

La &#39;risoluzione monitor&#39; [dimensione](overview.md) mostra l&#39;altezza e la larghezza dello schermo attivo in pixel. Questa dimensione è utile quando desideri comprendere dove si trova la &quot;piega&quot; sul sito per i visitatori o quanto i visitatori possono fare la loro finestra del browser. Sapere dove si trova la piega può consentirti di ottimizzare il contenuto da visualizzare.

Questa dimensione è diversa da quella del browser [height](browser-height.md) e [width](browser-width.md). Altezza/larghezza browser è il numero di pixel all’interno dello spazio visualizzabile del browser, mentre risoluzione monitor è il numero di pixel dell’intero monitor. Se desideri vedere la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Le dimensioni del browser sono sempre inferiori alla risoluzione del monitor, poiché non includono la navigazione o i bordi del browser.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa di query [`s`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando le variabili JavaScript `screen.width` e `screen.height` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito.

Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `s` nelle richieste di immagini. Se la stringa di query `s` è mancante o una libreria di raccolta dati non è in grado di raccogliere la risoluzione del monitoraggio, tali dati sono elencati in [!UICONTROL `Not Specified`].

## Elementi dimensionali

Gli elementi Dimension includono tutte le risoluzioni del monitor raccolte. I valori di esempio includono `1920 x 1080`, `1366 x 768` e `1280 x 720`.
