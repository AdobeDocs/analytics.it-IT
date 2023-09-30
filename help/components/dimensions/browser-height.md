---
title: Altezza browser - con bucket
description: Altezza della finestra del browser in pixel.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 1%

---

# Altezza browser

&quot;Altezza browser - bucket&quot; [dimensione](overview.md) mostra l&#39;altezza della finestra del browser, classificata in gruppi predefiniti. Questa dimensione è utile quando desideri capire dove si trova la &quot;piega&quot; sul sito per i visitatori. Sapere dove si trova la piega può consentirti di ottimizzare il contenuto da visualizzare.

Questa dimensione è diversa dall’altezza dello schermo. L&#39;altezza del browser è il numero di pixel all&#39;interno dello spazio visualizzabile del browser, mentre l&#39;altezza dello schermo è l&#39;altezza dell&#39;intero monitor in pixel. Se desideri vedere la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

L&#39;altezza del browser è sempre inferiore o uguale all&#39;altezza dello schermo, poiché non include la navigazione o i bordi del browser.

## Popola questa dimensione con i dati

Questa dimensione recupera i dati da [`bh` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `window.innerHeight` nel browser. Se utilizzi una libreria di AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati che non rientra in AppMeasurement (ad esempio tramite l’API), accertati di includere i `bh` parametro della stringa di query sul primo hit di ogni visita.

L’Adobe persiste nell’altezza del browser per una visita. Se l’altezza del browser è regolata a metà visita, la regolazione non viene registrata.

## Elementi dimensionali

Gli elementi di Dimension includono tutte le altezze del browser raccolte, classificate in gruppi predefiniti. Ad esempio, se l’altezza del browser di un hit è `720`, quindi viene raggruppato nell’elemento dimensione `700 to 799`.
