---
title: Altezza browser - con bucket
description: Altezza della finestra del browser in pixel.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
source-git-commit: 2601b0e5c3fa78237ce693801b8dd8c95b853b81
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 3%

---

# Altezza browser

In &#39;Altezza browser - bucket&#39; [dimensione](overview.md) è visualizzata l&#39;altezza della finestra del browser, classificata in gruppi predefiniti. Questa dimensione è utile quando desideri capire dove si trova la &quot;piega&quot; sul sito per i visitatori. Sapere dove si trova la piega può consentirti di ottimizzare il contenuto da visualizzare.

Questa dimensione è diversa dall’altezza dello schermo. L&#39;altezza del browser è il numero di pixel all&#39;interno dello spazio visualizzabile del browser, mentre l&#39;altezza dello schermo è l&#39;altezza dell&#39;intero monitor in pixel. Se desideri vedere la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

L&#39;altezza del browser è sempre inferiore o uguale all&#39;altezza dello schermo, poiché non include la navigazione o i bordi del browser.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa di query [`bh`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `window.innerHeight` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `bh` nel primo hit di ogni visita.

Adobe mantiene l’altezza del browser per una visita. Se l’altezza del browser è regolata a metà visita, la regolazione non viene registrata.

## Elementi dimensionali

Gli elementi Dimension includono tutte le altezze del browser raccolte, classificate in gruppi predefiniti. Ad esempio, se l&#39;altezza del browser di un hit è `720`, viene raggruppato nell&#39;elemento dimensione `700 to 799`.
