---
title: Collegamento personalizzato
description: Nome del collegamento personalizzato.
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 2%

---


# Collegamento personalizzato

La dimensione &quot;Collegamento personalizzato&quot; indica i nomi dei collegamenti personalizzati implementati sul sito. Questa dimensione è preziosa per comprendere i tipi di collegamenti di cui i visitatori fanno clic di più.

## Compilare questa dimensione con i dati

Questa dimensione raccoglie i dati dalla [`pev2` stringa query](/help/implement/validate/query-parameters.md) nelle richieste di immagini per gli hit che dispongono anche della stringa di query `pe` con il valore di `lnk_o`. Se la stringa di query `pe` ha un valore diverso nell&#39;hit, questa dimensione non raccoglie dati.

Se desiderate inviare dati a questa dimensione utilizzando AppMeasurement, inviate una richiesta di immagine [`tl()`](/help/implement/vars/functions/tl-method.md) con un argomento del tipo di collegamento `"o"`. Compilare l’argomento del nome del collegamento con il valore desiderato.

## Elementi Dimension

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina gli elementi dimensione.  Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
