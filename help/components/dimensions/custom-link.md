---
title: Collegamento personalizzato
description: Nome del collegamento personalizzato.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 2%

---

# Collegamento personalizzato

La dimensione &quot;Collegamento personalizzato&quot; riporta i nomi dei collegamenti personalizzati implementati sul sito. Questa dimensione è utile quando desideri comprendere i tipi di collegamenti più selezionati dai visitatori.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie i dati dal [`pev2` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini per i risultati che hanno anche `pe` stringa di interrogazione con il valore di `lnk_o`. Se la `pe` la stringa di query ha un valore diverso nell&#39;hit, questa dimensione non raccoglie dati.

Se desideri inviare dati a questa dimensione utilizzando AppMeasurement, invia un [`tl()`](/help/implement/vars/functions/tl-method.md) richiesta immagine con un argomento del tipo di collegamento `"o"`. Compila l’argomento del nome del collegamento con il valore desiderato.

## Elementi Dimension

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina gli elementi dimensionali desiderati. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
