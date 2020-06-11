---
title: Link di download
description: Nome del collegamento di download.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 2%

---


# Link di download

La dimensione &quot;Collegamento per il download&quot; riporta i nomi dei collegamenti di download implementati sul sito. Questa dimensione è preziosa se vuoi saperne di più sul comportamento dei visitatori in relazione ai collegamenti per il download, ad esempio:

* Determinare i file scaricati più frequentemente dal sito.
* Comprendere se alcuni file vengono scaricati più spesso durante periodi di tempo specifici.
* Convalidare che i visitatori scaricino tipi di file diversi se offerti.

## Compilare questa dimensione con i dati

Questa dimensione raccoglie i dati dalla stringa [`pev2` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini per gli hit che dispongono anche della stringa di `pe` query con il valore di `lnk_d`. Se la stringa di `pe` query ha un valore diverso nell’hit, questa dimensione non raccoglie dati.

Se vuoi inviare dati a questa dimensione utilizzando AppMeasurement:

* Compilare la [`linkName`](/help/implement/vars/config-vars/linkname.md) variabile con il valore desiderato.
* Set the [`linkType`](/help/implement/vars/config-vars/linktype.md) variable to `"d"`.
* Invia una richiesta di [`tl()`](/help/implement/vars/functions/tl-method.md) immagine.

## Valori dimensione

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina i valori della dimensione. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
