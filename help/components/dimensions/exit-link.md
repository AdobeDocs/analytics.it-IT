---
title: Collegamento di uscita
description: Nome del collegamento di uscita.
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 2%

---


# Collegamento di uscita

La dimensione &#39;Exit link&#39; segnala i nomi dei collegamenti di uscita implementati sul sito. Questa dimensione è preziosa quando si desidera capire quali collegamenti sono più popolari che puntano a domini esterni al sito.

## Compilare questa dimensione con i dati

Questa dimensione raccoglie i dati dalla [`pev2` stringa query](/help/implement/validate/query-parameters.md) nelle richieste di immagini per gli hit che dispongono anche della stringa di query `pe` con il valore di `lnk_e`. Se la stringa di query `pe` ha un valore diverso nell&#39;hit, questa dimensione non raccoglie dati.

Se desiderate inviare dati a questa dimensione utilizzando AppMeasurement, inviate una richiesta di immagine [`tl()`](/help/implement/vars/functions/tl-method.md) con un argomento del tipo di collegamento `"e"`. Compilare l’argomento del nome del collegamento con il valore desiderato.

## Elementi Dimension

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina gli elementi dimensione.  Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
