---
title: Larghezza browser - a blocchi
description: Larghezza della finestra del browser in pixel.
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Larghezza browser

La dimensione &#39;Larghezza browser - fibket&#39; mostra la larghezza della finestra del browser, classificata in gruppi di 100 pixel. Questa dimensione è utile quando desideri comprendere l’ampiezza con cui i visitatori visualizzano il contenuto. L’ampiezza di visualizzazione dei contenuti può consentire di ottimizzare i contenuti per la visualizzazione.

Questa dimensione è diversa dalla larghezza dello schermo. La larghezza del browser è il numero di pixel all&#39;interno dello spazio visibile del browser, mentre la larghezza dello schermo è la larghezza dell&#39;intero monitor in pixel. Se desideri visualizzare la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

La larghezza del browser è sempre inferiore o uguale alla larghezza dello schermo, in quanto la larghezza del browser non include barre di scorrimento o bordi.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla [`bw` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `window.innerWidth` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente. Se utilizzi un metodo di raccolta dati al di fuori di AppMeasurement (ad esempio tramite l’API), assicurati di includere il parametro della stringa di query `bw` sul primo hit di ogni visita.

L’Adobe persiste nella larghezza del browser per una visita. Se la larghezza del browser viene regolata a metà visita, la regolazione non viene registrata.

## Elementi Dimension

Gli elementi di Dimension includono tutte le larghezze del browser raccolte, classificate in gruppi di 100 pixel. Ad esempio, se la larghezza del browser di un hit è `1280`, viene raggruppata nell’elemento dimensionale `1200 to 1299`.
