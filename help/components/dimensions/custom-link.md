---
title: Collegamento personalizzato
description: Nome del collegamento personalizzato.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 7%

---

# Collegamento personalizzato

La [dimensione](overview.md) del &#39;collegamento personalizzato&#39; riporta i nomi dei collegamenti personalizzati implementati nel sito. Questa dimensione è utile quando desideri comprendere i tipi di collegamenti che i visitatori fanno più clic.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalla stringa di query [`pev2`](/help/implement/validate/query-parameters.md) nelle richieste di immagini per hit che hanno anche la stringa di query `pe` con il valore di `lnk_o`. Se la stringa di query `pe` ha un valore diverso nell&#39;hit, questa dimensione non raccoglie dati.

Se si desidera inviare dati a questa dimensione utilizzando AppMeasurement, inviare una richiesta di immagine [`tl()`](/help/implement/vars/functions/tl-method.md) con un argomento tipo collegamento di `"o"`. Popolare l&#39;argomento del nome del collegamento con il valore desiderato.

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. L’Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
