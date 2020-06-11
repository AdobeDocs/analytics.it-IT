---
title: Profondità colore
description: Profondità colore del dispositivo.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# Profondità colore

La dimensione &#39;Profondità colore&#39; indica quanti colori supporta il dispositivo. Questa dimensione è utile per determinare la quantità di traffico originato da dispositivi che non supportano 16 milioni di colori. Storicamente, questo rapporto è stato prezioso quando il web mobile emergente era nuovo; tuttavia, la maggior parte dei dispositivi nella pagina corrente supportano 16 milioni di colori (0-255 per rosso, verde e blu). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca, traducendo il valore bit in un formato più leggibile. Raccoglie dati dalla stringa [`c` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement utilizza la `screen.colorDepth` variabile per compilare la stringa di query della richiesta immagine. Se usi AppMeasurement (ad esempio tramite Adobe Experience Platform Launch), questa dimensione non è disponibile. Se utilizzi un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertati di includere il parametro della stringa di `c` query in ogni hit con un valore di bit valido.

## Valori dimensione

I valori delle dimensioni includono il numero di colori supportati dal dispositivo. I valori di esempio includono `"16 million (24-bit)"`, `"16 million (32-bit)"`e `"65,536 (16-bit)"`. Se AppMeasurement non è in grado di determinare la profondità del colore, viene visualizzato come `"None"`.

> [!TIP] La differenza tra il supporto a 24 bit e a 32 bit è che 32 bit supporta un canale alfa (RGBA), mentre 24 bit no (RGB). Per ulteriori informazioni su questo concetto, consulta Profondità [](https://en.wikipedia.org/wiki/Color_depth) colore su Wikipedia.
