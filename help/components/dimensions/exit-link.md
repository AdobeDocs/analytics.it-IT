---
title: Collegamento di uscita
description: Nome del collegamento di uscita.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 2%

---

# Collegamento di uscita

La dimensione &quot;Collegamento di uscita&quot; riporta i nomi dei collegamenti di uscita implementati sul sito. Questa dimensione è utile quando desideri capire quali collegamenti sono più comuni e puntare a domini esterni al tuo sito.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie i dati dal [`pev2` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini per i risultati che hanno anche `pe` stringa di interrogazione con il valore di `lnk_e`. Se la `pe` la stringa di query ha un valore diverso nell&#39;hit, questa dimensione non raccoglie dati.

Se desideri inviare dati a questa dimensione utilizzando AppMeasurement, invia un [`tl()`](/help/implement/vars/functions/tl-method.md) richiesta immagine con un argomento del tipo di collegamento `"e"`. Compila l’argomento del nome del collegamento con il valore desiderato.

## Elementi Dimension

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina gli elementi dimensionali desiderati. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
