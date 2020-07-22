---
title: Numero visita
description: Ennesima visita del visitatore.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 0%

---


# Numero visita

I rapporti sulla dimensione &quot;Visita numero&quot; in cui il visitatore è attualmente attivo. Quando inizia una nuova visita, questo elemento dimensione aumenta di 1. Questa dimensione è utile per comprendere il livello di coinvolgimento dei visitatori che tornano al sito. Si tratta di una dimensione basata sulle visite, il che significa che contiene lo stesso valore per l’intera visita e non può essere modificata. Si applica al ciclo di vita del visitatore, indipendentemente dall’intervallo di date del progetto.

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensione

Gli elementi dimensione includono la stringa `"Visit number"` seguita dalla rappresentazione numerica della visita attualmente in corso. Ad esempio, se il visitatore non è mai stato sul sito prima, la sua prima visita appartiene all’elemento dimensione `"Visit number 1"`. Se si tratta della tredicesima visita del visitatore al sito, questi appartiene all’elemento dimensione `"Visit number 13"`.
