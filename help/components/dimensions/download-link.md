---
title: Collegamento di download
description: Nome del collegamento per il download.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: 33d837cfa7909bd93d5a4f675aa0d8894a403266
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 3%

---

# Collegamento di download

Il &quot;collegamento di download&quot; [dimensione](overview.md) segnala i nomi dei collegamenti di download implementati sul sito. Questa dimensione è utile quando desideri ulteriori informazioni sul comportamento dei visitatori in merito ai collegamenti di download, ad esempio:

* Determina i file scaricati più frequentemente dal tuo sito.
* Scopri se alcuni file vengono scaricati più spesso in determinati periodi di tempo.
* Convalida che i visitatori scarichino diversi tipi di file, se offerti.

## Popola questa dimensione con i dati

Questa dimensione raccoglie dati da [`pev2` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini per hit che hanno anche il `pe` stringa di query con il valore di `lnk_d`. Se il `pe` la stringa di query ha un valore diverso nell’hit, questa dimensione non raccoglie dati.

Se desideri inviare dati a questa dimensione utilizzando AppMeasurement, invia un [`tl()`](/help/implement/vars/functions/tl-method.md) richiesta immagine con argomento tipo collegamento `"d"`. Popolare l’argomento del nome del collegamento con il valore desiderato:

```js
s.tl(true,"d","Example download link");
```

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. L’Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
