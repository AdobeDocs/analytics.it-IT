---
description: Metriche che fanno riferimento alla distanza orizzontale/verticale dei dati solo nella finestra del browser. Più specificamente, il browser
seo-description: Metriche che fanno riferimento alla distanza orizzontale/verticale dei dati solo nella finestra del browser. Più specificamente, il browser
seo-title: Larghezza/Altezza browser
solution: Analytics
title: Larghezza/Altezza browser
topic: Metrics (Metriche)
uuid: 1 c 0 d 3 ea 9-e 001-4152-9 bfc -8 fe 6406 bc 755
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Larghezza/Altezza browser

Metriche che fanno riferimento alla distanza orizzontale/verticale dei dati solo nella finestra del browser. Più specificamente, il browser

Adobe Analytics usa l'altezza e la larghezza del browser solo a partire dalla prima occorrenza di una visita. Gli altri hit non ricevono l'attribuzione per la stessa visita.
The browser width/height dimensions capture similar but distinct values when compared with [mobile screen size](../../../components/c-variables/dimensionslist/reports-mobile.md#topic_D306EA4558194488AC47A45B9C570150).

Ad esempio, quando interrompete la larghezza o l'altezza del browser per risoluzione mobile, dovete essere consapevoli di queste distinzioni:

* Le risoluzioni dei dispositivi mobili sono i valori fisici associati al dispositivo. Ad esempio, in Risoluzioni dispositivo mobili il valore Galaxy S 8 verrebbe visualizzato come 2,960 x 1,440. La risoluzione del dispositivo mobile viene recuperata da un servizio 3 rd-party dopo che il dispositivo è stato identificato.
* Per contro, sotto i valori Altezza e Larghezza browser vengono visualizzati i valori CSS (logici) di 740 x 360. I valori del browser usano i dati Javascript/CSS.
* For a brief discussion, see [this thread](https://stackoverflow.com/questions/8785643/what-exactly-is-device-pixel-ratio).

