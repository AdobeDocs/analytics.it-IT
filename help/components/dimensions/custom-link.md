---
title: Collegamento personalizzato
description: Nome del collegamento personalizzato.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 3%

---

# Collegamento personalizzato

Il &quot;collegamento personalizzato&quot; [dimensione](overview.md) segnala i nomi dei collegamenti personalizzati implementati sul sito. Questa dimensione è utile quando desideri comprendere i tipi di collegamenti che i visitatori fanno più clic.

## Popola questa dimensione con i dati

Questa dimensione raccoglie dati da [`pev2` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini per hit che hanno anche il `pe` stringa di query con il valore di `lnk_o`. Se il `pe` la stringa di query ha un valore diverso nell’hit, questa dimensione non raccoglie dati.

Se desideri inviare dati a questa dimensione utilizzando AppMeasurement, invia un [`tl()`](/help/implement/vars/functions/tl-method.md) richiesta immagine con argomento tipo collegamento `"o"`. Popolare l&#39;argomento del nome del collegamento con il valore desiderato.

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. L’Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
