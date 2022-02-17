---
title: Risoluzione monitor
description: La risoluzione in pixel del monitor del visitatore.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 1%

---

# Risoluzione monitor

La dimensione &quot;Risoluzione monitor&quot; mostra l&#39;altezza e la larghezza della visualizzazione attiva in pixel. Questa dimensione è utile quando desideri capire dove si trova la &quot;piega&quot; sul sito per i visitatori, o quanto possono essere i visitatori a fare la loro finestra del browser. Per ottimizzare il contenuto per la visualizzazione, occorre capire dove si trova la piega.

Questa dimensione è diversa dall’altezza e dalla larghezza del browser. L&#39;altezza/larghezza del browser è il numero di pixel all&#39;interno dello spazio visibile del browser, mentre la risoluzione del monitor è il numero di pixel dell&#39;intero monitor. Se desideri visualizzare la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Le dimensioni del browser sono sempre più piccole della risoluzione del monitor, poiché le dimensioni del browser non includono la navigazione o i bordi del browser.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dal [`s` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `screen.width` e `screen.height` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente. Se utilizzi un metodo di raccolta dati al di fuori di AppMeasurement (ad esempio tramite l’API), assicurati di includere il `s` parametro della stringa query nelle richieste di immagini.

## Elementi Dimension

Gli elementi di Dimension includono tutte le risoluzioni di monitoraggio raccolte. I valori di esempio includono `1920 x 1080`, `1366 x 768`e `1280 x 720`.
