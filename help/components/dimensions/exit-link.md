---
title: Collegamento di uscita
description: Nome del collegamento di uscita.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 3%

---

# Collegamento di uscita

La dimensione &quot;Collegamento di uscita&quot; riporta i nomi dei collegamenti di uscita implementati sul sito. Questa dimensione è utile quando desideri comprendere quali collegamenti sono più popolari e che puntano a domini esterni al sito.

## Popola questa dimensione con i dati

Questa dimensione raccoglie dati da [`pev2` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini per hit che hanno anche il `pe` stringa di query con il valore di `lnk_e`. Se il `pe` la stringa di query ha un valore diverso nell’hit, questa dimensione non raccoglie dati.

Se desideri inviare dati a questa dimensione utilizzando AppMeasurement, invia un [`tl()`](/help/implement/vars/functions/tl-method.md) richiesta immagine con argomento tipo collegamento `"e"`. Popolare l&#39;argomento del nome del collegamento con il valore desiderato.

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. L’Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
