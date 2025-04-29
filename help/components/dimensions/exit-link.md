---
title: Collegamento di uscita
description: Nome del collegamento di uscita.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%

---

# Collegamento di uscita

La [dimensione](overview.md) del &#39;collegamento di uscita&#39; riporta i nomi dei collegamenti di uscita implementati nel sito. Questa dimensione è utile quando desideri comprendere quali collegamenti sono più popolari e che puntano a domini esterni al sito.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalla stringa di query [`pev2`](/help/implement/validate/query-parameters.md) nelle richieste di immagini per hit che hanno anche la stringa di query `pe` con il valore di `lnk_e`. Se la stringa di query `pe` ha un valore diverso nell&#39;hit, questa dimensione non raccoglie dati. La lunghezza massima di questa dimensione è di 100 byte.

Se desideri inviare dati a questa dimensione utilizzando AppMeasurement, invia una richiesta di immagine [`tl()`](/help/implement/vars/functions/tl-method.md) con un argomento tipo collegamento di `"e"`. Popolare l&#39;argomento del nome del collegamento con il valore desiderato.

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
