---
title: Profondità colore
description: Profondità colore del dispositivo.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# Profondità colore

La &#39;Profondità colore&#39; [dimensione](overview.md) riporta il numero di colori supportati dal dispositivo. Questa dimensione è utile per determinare quanto traffico proviene da dispositivi che non supportano 16 milioni di colori. Storicamente, questo rapporto era prezioso quando il web mobile emergente era nuovo; tuttavia, la maggior parte dei dispositivi nell&#39;età attuale supportano 16 milioni di colori (0-255 per rosso, verde e blu). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Popola questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca, traducendo il valore di bit in un formato più leggibile. Raccoglie dati dal [`c` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement utilizza `screen.colorDepth` variabile per popolare la stringa di query della richiesta di immagine. Se utilizzi AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati che non rientra in AppMeasurement (ad esempio tramite l’API), accertati di includere i `c` parametro della stringa di query su ogni hit con un valore di bit valido.

## Elementi dimensionali

Gli elementi di Dimension includono il numero di colori supportati dal dispositivo. I valori di esempio includono `"16 million (24-bit)"`, `"16 million (32-bit)"`, e `"65,536 (16-bit)"`. Se l&#39;AppMeasurement non è in grado di determinare la profondità del colore, viene visualizzato come `"None"`.

>[!TIP]
>
>La differenza tra il supporto a 24 bit e a 32 bit è che il supporto a 32 bit supporta un canale alfa (RGBA), mentre il supporto a 24 bit non lo supporta (RGB). Consulta [Profondità colore](https://en.wikipedia.org/wiki/Color_depth) su Wikipedia per ulteriori informazioni su questo concetto.
