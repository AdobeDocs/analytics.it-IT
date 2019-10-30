---
description: Metriche che fanno riferimento alla distanza orizzontale/verticale dei dati solo nella finestra del browser. Più precisamente, il browser
seo-description: Metriche che fanno riferimento alla distanza orizzontale/verticale dei dati solo nella finestra del browser. Più precisamente, il browser
seo-title: Larghezza/Altezza browser
solution: Analytics
title: Larghezza/Altezza browser
topic: Metriche
uuid: 1c0d3ea9-e001-4152-9bfc-8fe6406bc755
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Larghezza/Altezza browser

Metriche che fanno riferimento alla distanza orizzontale/verticale dei dati solo nella finestra del browser. Più precisamente, il browser

Adobe Analytics utilizza l’altezza e la larghezza del browser solo dal primo hit di una visita. Gli altri hit non ricevono l’attribuzione per la stessa visita.
Le dimensioni larghezza/altezza del browser acquisiscono valori simili ma distinti rispetto alle dimensioni [dello schermo](../../../components/c-variables/dimensionslist/reports-mobile.md#topic_D306EA4558194488AC47A45B9C570150)mobile.

Ad esempio, quando si suddivide larghezza o altezza del browser per risoluzione mobile, è necessario essere consapevoli delle seguenti differenze:

* Le risoluzioni dispositivo mobile sono i valori fisici associati al dispositivo. Ad esempio, in Risoluzioni dispositivo mobile la Galaxy S8 viene visualizzata come 2.960 x 1.440. La risoluzione del dispositivo mobile viene recuperata da un servizio di terze parti dopo che il dispositivo è stato identificato.
* Per contro, sotto i valori Altezza e Larghezza del browser, vengono visualizzati i valori CSS (logici) di 740 x 360. I valori del browser si basano sui dati Javascript/CSS.
* Per una breve discussione, consultate [questo thread](https://stackoverflow.com/questions/8785643/what-exactly-is-device-pixel-ratio).

