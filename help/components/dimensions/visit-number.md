---
title: Numero di visite
description: L’ennesima visita del visitatore.
feature: Dimensions
exl-id: daef34b3-c270-476d-a45c-a20be6138c6b
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 2%

---

# Numero di visite

Il rapporto sulla dimensione &quot;Numero di visite&quot; che visita il visitatore al momento. Quando inizia una nuova visita, questo elemento della dimensione aumenta di 1. Questa dimensione è utile quando desideri comprendere il coinvolgimento dei visitatori al ritorno al sito. Si tratta di una dimensione basata su visita, il che significa che contiene lo stesso valore per l’intera visita e non può essere modificata. Si applica alla durata del visitatore, indipendentemente dall’intervallo di date del progetto.

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Gli elementi di Dimension includono la stringa `"Visit number"` seguita dalla rappresentazione numerica della visita su cui il visitatore si trova attualmente. Ad esempio, se il visitatore non è mai stato sul sito prima, la sua prima visita appartiene all’elemento dimensionale `"Visit number 1"`. Se si tratta della tredicesima visita del visitatore al sito, questo appartiene all’elemento dimensionale `"Visit number 13"`.
