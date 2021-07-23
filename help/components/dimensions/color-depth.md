---
title: Profondità colore
description: Profondità colore del dispositivo.
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 1%

---

# Profondità colore

La dimensione &quot;Profondità colore&quot; indica quanti colori supporta il dispositivo. Questa dimensione è utile per determinare la quantità di traffico originato dai dispositivi che non supportano 16 milioni di colori. Storicamente, questo rapporto è stato prezioso quando il web mobile emergente era nuovo; tuttavia, la maggior parte dei dispositivi nell&#39;età corrente supportano 16 milioni di colori (0-255 per rosso, verde e blu). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca, traducendo il valore del bit in un formato più leggibile. Raccoglie dati dalla [`c` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement utilizza la variabile `screen.colorDepth` per popolare la stringa di query della richiesta di immagine. Se utilizzi AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona come se fosse preconfigurata. Se utilizzi un metodo di raccolta dati al di fuori di AppMeasurement (ad esempio tramite l’API), assicurati di includere il parametro della stringa di query `c` su ogni hit con un valore di bit valido.

## Elementi Dimension

Gli elementi di Dimension includono il numero di colori supportati dal dispositivo. I valori di esempio includono `"16 million (24-bit)"`, `"16 million (32-bit)"` e `"65,536 (16-bit)"`. Se AppMeasurement non è in grado di determinare la profondità del colore, verrà visualizzato come `"None"`.

>[!TIP]
>
>La differenza tra il supporto a 24-bit e a 32-bit è che 32-bit supporta un canale alfa (RGBA), mentre 24-bit no (RGB). Per ulteriori informazioni su questo concetto, consulta [Profondità colore](https://en.wikipedia.org/wiki/Color_depth) su Wikipedia .
