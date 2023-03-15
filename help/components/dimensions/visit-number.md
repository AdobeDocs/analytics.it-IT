---
title: Numero di visite
description: L’ennesima visita del visitatore.
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 3%

---

# Numero di visite

La dimensione &quot;Numero di visite&quot; segnala le visite al visitatore attualmente in corso. Quando inizia una nuova visita, questo elemento dimensionale aumenta di 1. Questa dimensione è utile quando desideri comprendere quanto sono coinvolti i visitatori quando ritornano al sito. Si tratta di una dimensione basata sulle visite, il che significa che contiene lo stesso valore per l’intera visita e non può cambiare. Si applica alla durata del visitatore, indipendentemente dall’intervallo di date del progetto.

## Popola questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi Dimension includono la stringa `"Visit number"` seguito dalla rappresentazione numerica della visita in cui si trova il visitatore. Ad esempio, se il visitatore non è mai stato prima sul tuo sito, la sua prima visita appartiene all’elemento dimensione `"Visit number 1"`. Se si tratta della 13a visita del visitatore al sito, l’elemento appartiene alla dimensione `"Visit number 13"`.
