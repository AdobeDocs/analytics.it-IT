---
title: Collegamento di download
description: Nome del collegamento di download.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 2%

---

# Collegamento di download

La dimensione &quot;Download link&quot; (Collegamento download) riporta i nomi dei collegamenti di download implementati sul sito. Questa dimensione è utile quando desideri ulteriori informazioni sul comportamento dei visitatori in relazione ai collegamenti per il download, ad esempio:

* Determina i file scaricati più frequentemente dal sito.
* Comprendere se alcuni file vengono scaricati più spesso durante specifici periodi di tempo.
* Convalida che i visitatori scaricino tipi di file diversi, se offerti.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie i dati dal [`pev2` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini per i risultati che hanno anche `pe` stringa di interrogazione con il valore di `lnk_d`. Se la `pe` la stringa di query ha un valore diverso nell&#39;hit, questa dimensione non raccoglie dati.

Se desideri inviare dati a questa dimensione utilizzando AppMeasurement, invia un [`tl()`](/help/implement/vars/functions/tl-method.md) richiesta immagine con un argomento del tipo di collegamento `"d"`. Compila l’argomento del nome del collegamento con il valore desiderato.

## Elementi Dimension

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina gli elementi dimensionali desiderati. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting.
