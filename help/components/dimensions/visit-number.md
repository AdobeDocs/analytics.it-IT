---
title: Numero di visite
description: L’ennesima visita del visitatore.
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 100%

---

# Numero di visite

La [dimensione](overview.md) “Numero di visite” segnala a quale visita si trova attualmente il visitatore. Quando inizia una nuova visita, questo elemento dimensione aumenta di 1. Questa dimensione è utile quando desideri comprendere quanto sono coinvolti i visitatori quando ritornano sul sito. Si tratta di una dimensione basata sulle visite, il che significa che contiene lo stesso valore per l’intera visita e non può cambiare. Si applica al ciclo di vita del visitatore, indipendentemente dall’intervallo di date del progetto.

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi dimensionali includono la stringa `"Visit number"` seguita dalla rappresentazione numerica della visita in cui il visitatore si trova attualmente. Ad esempio, se il visitatore non è mai stato prima sul sito, la sua prima visita appartiene all’elemento dimensione `"Visit number 1"`. Se si tratta della tredicesima visita del visitatore nel sito, l’elemento appartiene alla dimensione `"Visit number 13"`.
