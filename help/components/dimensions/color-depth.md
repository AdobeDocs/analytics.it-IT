---
title: Profondità colore
description: Profondità colore del dispositivo.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 6%

---

# Profondità colore

La &#39;Profondità colore&#39; [dimensione](overview.md) indica quanti colori supporta il dispositivo. Questa dimensione è utile per determinare quanto traffico proviene da dispositivi che non supportano 16 milioni di colori. Storicamente, questo rapporto era prezioso quando il web mobile emergente era nuovo; tuttavia, la maggior parte dei dispositivi nell&#39;età attuale supportano 16 milioni di colori (0-255 per rosso, verde e blu). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca, traducendo il valore di bit in un formato più leggibile. Raccoglie dati dalla stringa di query [`c`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement utilizza la variabile `screen.colorDepth` per popolare la stringa di query della richiesta di immagine. Se utilizzi AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `c` in ogni hit con un valore di bit valido.

## Elementi dimensionali

Gli elementi Dimension includono il numero di colori supportati dal dispositivo. Valori di esempio includono `"16 million (24-bit)"`, `"16 million (32-bit)"`, e `"65,536 (16-bit)"`. Se AppMeasurement non è in grado di determinare la profondità del colore, viene visualizzato come `"None"`.

>[!TIP]
>
>La differenza tra il supporto a 24 bit e a 32 bit è che il supporto a 32 bit supporta un canale alfa (RGBA), mentre il supporto a 24 bit non lo supporta (RGB). Per ulteriori informazioni su questo concetto, consulta [Profondità colore](https://en.wikipedia.org/wiki/Color_depth) su Wikipedia.
