---
title: Larghezza browser - a blocchi
description: La larghezza della finestra del browser, in pixel.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Larghezza browser

La dimensione &#39;Larghezza browser - rilegatura&#39; mostra la larghezza della finestra del browser, classificata in gruppi di 100 pixel. Questa dimensione è utile per comprendere l’ampiezza con cui i visitatori visualizzano il contenuto. Comprendere l’ampiezza del contenuto generalmente visualizzato può consentire di ottimizzare il contenuto per la visualizzazione.

Questa dimensione è diversa dalla larghezza dello schermo. La larghezza del browser è il numero di pixel all’interno dello spazio visibile del browser, mentre la larghezza dello schermo è la larghezza dell’intero monitor, in pixel. Se desiderate visualizzare la differenza tra queste due variabili sul computer, aprite la console del browser (F12 nella maggior parte dei browser) e copiate e incollate il seguente codice nella console:

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

La larghezza del browser è sempre inferiore o uguale alla larghezza dello schermo, poiché la larghezza del browser non include barre di scorrimento o bordi.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`bw` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `window.innerWidth` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite  lancio del Adobe Experience Platform), questa dimensione non è disponibile. Se utilizzi un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertati di includere il parametro della stringa di `bw` query nel primo hit di ogni visita.

Adobe persiste nella larghezza del browser per una visita. Se la larghezza del browser viene regolata a metà visita, la regolazione non viene registrata.

## Elementi dimensione

Gli elementi dimensione includono tutte le larghezze di browser raccolte, classificate in gruppi di 100 pixel. Ad esempio, se la larghezza del browser di un hit è `1280`, viene raggruppata nell’elemento dimensione `1200 to 1299`.
