---
title: Altezza browser - a blocchi
description: Altezza della finestra del browser in pixel.
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Altezza browser

La dimensione &#39;Altezza browser - fibket&#39; mostra l&#39;altezza della finestra del browser, classificata in gruppi di 100 pixel. Questa dimensione è utile quando desideri capire dove si trova la &quot;piega&quot; sul sito per i visitatori. Per ottimizzare il contenuto per la visualizzazione, occorre capire dove si trova la piega.

Questa dimensione è diversa dall’altezza dello schermo. L&#39;altezza del browser è il numero di pixel all&#39;interno dello spazio visibile del browser, mentre l&#39;altezza dello schermo è l&#39;altezza dell&#39;intero monitor in pixel. Se desideri visualizzare la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

L’altezza del browser è sempre inferiore o uguale all’altezza dello schermo, poiché l’altezza del browser non include la navigazione o i bordi del browser.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla [`bh` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `window.innerHeight` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente. Se utilizzi un metodo di raccolta dati al di fuori di AppMeasurement (ad esempio tramite l’API), assicurati di includere il parametro della stringa di query `bh` sul primo hit di ogni visita.

L’altezza del browser dell’Adobe persiste per una visita. Se l’altezza del browser viene regolata a metà visita, la regolazione non viene registrata.

## Elementi Dimension

Gli elementi di Dimension includono tutte le altezze raccolte del browser, classificate in gruppi di 100 pixel. Ad esempio, se l’altezza del browser di un hit è `720`, viene raggruppata nell’elemento dimensionale `700 to 799`.
