---
title: Larghezza browser - con bucket
description: Larghezza in pixel della finestra del browser.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 1%

---

# Larghezza browser

La &quot;Larghezza del browser - bucket&quot; [dimensione](overview.md) mostra la larghezza della finestra del browser, classificata in gruppi predefiniti. Questa dimensione è utile quando desideri comprendere il modo in cui i visitatori visualizzano il contenuto. Comprendere la larghezza in cui vengono generalmente visualizzati i contenuti può consentirti di ottimizzarli.

Questa dimensione è diversa dalla larghezza dello schermo. Larghezza browser è il numero di pixel all’interno dello spazio visualizzabile del browser, mentre la larghezza dello schermo è la larghezza dell’intero monitor in pixel. Se desideri vedere la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

La larghezza del browser è sempre inferiore o uguale alla larghezza dello schermo, in quanto non include barre di scorrimento o bordi.

## Popola questa dimensione con i dati

Questa dimensione recupera i dati da [`bw` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `window.innerWidth` nel browser. Se utilizzi una libreria di AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati che non rientra in AppMeasurement (ad esempio tramite l’API), accertati di includere i `bw` parametro della stringa di query sul primo hit di ogni visita.

L’Adobe mantiene la larghezza del browser per una visita. Se la larghezza del browser viene regolata a metà visita, la regolazione non viene registrata.

## Elementi dimensionali

Gli elementi di Dimension includono tutte le larghezze del browser raccolte, classificate in gruppi predefiniti. Ad esempio, se la larghezza del browser di un hit è `1280`, quindi viene raggruppato nell’elemento dimensione `1200 to 1299`.
