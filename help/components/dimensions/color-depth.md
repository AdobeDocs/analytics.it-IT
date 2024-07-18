---
title: Profondità colore
description: Profondità colore del dispositivo.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 6%

---

# Profondità colore

La &#39;Profondità colore&#39; [dimensione](overview.md) indica quanti colori supporta il dispositivo. Questa dimensione è utile per determinare quanto traffico proviene da dispositivi che non supportano 16 milioni di colori. Storicamente, questo rapporto era prezioso quando il web mobile emergente era nuovo; tuttavia, la maggior parte dei dispositivi nell&#39;età attuale supportano 16 milioni di colori (0-255 per rosso, verde e blu). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca, traducendo il valore di bit in un formato più leggibile. Raccoglie dati dalla stringa di query [`c`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. L&#39;AppMeasurement utilizza la variabile `screen.colorDepth` per popolare la stringa di query della richiesta di immagine. Se utilizzi AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno a AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `c` in ogni hit con un valore di bit valido.

## Elementi dimensionali

Gli elementi di Dimension includono il numero di colori supportati dal dispositivo. Valori di esempio includono `"16 million (24-bit)"`, `"16 million (32-bit)"`, e `"65,536 (16-bit)"`. Se AppMeasurement non è in grado di determinare la profondità del colore, verrà visualizzato come `"None"`.

>[!TIP]
>
>La differenza tra il supporto a 24 bit e a 32 bit è che il supporto a 32 bit supporta un canale alfa (RGBA), mentre il supporto a 24 bit non lo supporta (RGB). Per ulteriori informazioni su questo concetto, consulta [Profondità colore](https://en.wikipedia.org/wiki/Color_depth) su Wikipedia.
