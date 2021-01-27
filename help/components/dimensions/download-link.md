---
title: Collegamento di download
description: Nome del collegamento di download.
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 2%

---


# Collegamento di download

La dimensione &quot;Collegamento per il download&quot; riporta i nomi dei collegamenti di download implementati sul sito. Questa dimensione è preziosa se vuoi saperne di più sul comportamento dei visitatori in relazione ai collegamenti per il download, ad esempio:

* Determinare i file scaricati più frequentemente dal sito.
* Comprendere se alcuni file vengono scaricati più spesso durante periodi di tempo specifici.
* Convalidare che i visitatori scaricino tipi di file diversi se offerti.

## Compilare questa dimensione con i dati

Questa dimensione raccoglie i dati dalla [`pev2` stringa query](/help/implement/validate/query-parameters.md) nelle richieste di immagini per gli hit che dispongono anche della stringa di query `pe` con il valore di `lnk_d`. Se la stringa di query `pe` ha un valore diverso nell&#39;hit, questa dimensione non raccoglie dati.

Se desiderate inviare dati a questa dimensione utilizzando AppMeasurement, inviate una richiesta di immagine [`tl()`](/help/implement/vars/functions/tl-method.md) con un argomento del tipo di collegamento `"d"`. Compilare l’argomento del nome del collegamento con il valore desiderato.

## Elementi Dimension

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina gli elementi dimensione.  Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
