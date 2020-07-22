---
title: Altezza del browser - rilegatura
description: L’altezza della finestra del browser in pixel.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Altezza browser

La dimensione &#39;Altezza browser - rilegatura&#39; mostra l&#39;altezza della finestra del browser, classificata in gruppi di 100 pixel. Questa dimensione è utile per capire dove si trova la &quot;piega&quot; sul sito per i visitatori. Comprendere dove si trova la piega può consentire di ottimizzare il contenuto per la visualizzazione.

Questa dimensione è diversa dall’altezza dello schermo. L’altezza del browser è il numero di pixel all’interno dello spazio visibile del browser, mentre l’altezza dello schermo è l’altezza dell’intero monitor, in pixel. Se desiderate visualizzare la differenza tra queste due variabili sul computer, aprite la console del browser (F12 nella maggior parte dei browser) e copiate e incollate il seguente codice nella console:

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

L&#39;altezza del browser è sempre inferiore o uguale all&#39;altezza dello schermo, poiché l&#39;altezza del browser non include la navigazione del browser o i bordi.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`bh` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `window.innerHeight` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite  lancio del Adobe Experience Platform), questa dimensione non è disponibile. Se utilizzi un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertati di includere il parametro della stringa di `bh` query nel primo hit di ogni visita.

Adobe persiste nell’altezza del browser per una visita. Se l’altezza del browser viene regolata a metà visita, la regolazione non viene registrata.

## Elementi dimensione

Gli elementi dimensione includono tutte le altezze del browser raccolte, classificati in gruppi di 100 pixel. Ad esempio, se l’altezza del browser di un hit è `720`, viene raggruppata nell’elemento dimensione `700 to 799`.
