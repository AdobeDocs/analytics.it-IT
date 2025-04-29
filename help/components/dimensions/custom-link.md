---
title: Collegamento personalizzato
description: Nome del collegamento personalizzato.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 6%

---

# Collegamento personalizzato

La [dimensione](overview.md) del &#39;collegamento personalizzato&#39; riporta i nomi dei collegamenti personalizzati implementati nel sito. Questa dimensione è utile quando desideri comprendere i tipi di collegamenti che i visitatori fanno più clic.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalla stringa di query [`pev2`](/help/implement/validate/query-parameters.md) nelle richieste di immagini per hit che hanno anche la stringa di query `pe` con il valore di `lnk_o`. Se la stringa di query `pe` ha un valore diverso nell&#39;hit, questa dimensione non raccoglie dati. La lunghezza massima di questa dimensione è di 100 byte.

Se desideri inviare dati a questa dimensione utilizzando AppMeasurement, invia una richiesta di immagine [`tl()`](/help/implement/vars/functions/tl-method.md) con un argomento tipo collegamento di `"o"`. Popolare l&#39;argomento del nome del collegamento con il valore desiderato.

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
