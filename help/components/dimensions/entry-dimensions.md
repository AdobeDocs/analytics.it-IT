---
title: Dimensioni di entrata
description: Elenca le dimensioni di ingresso e il loro utilizzo.
keywords: pagina di ingresso, sezione del sito di ingresso, server di ingresso, informazioni personalizzate di ingresso
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
source-git-commit: 1e8f2bdb7a20f21f6ff1a4d78d4db20963af6b45
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# Dimensioni di entrata

*Questa pagina di aiuto descrive il funzionamento delle voci come una dimensione. Per informazioni sul funzionamento delle voci come metriche, consulta la sezione [Voci](../metrics/entries.md) metrica.*

Le dimensioni di ingresso sono basate sulle visite. Registrano il primo elemento dimensione e lo persistono per l’intera durata della visita. Le dimensioni di ingresso sono disponibili per tutte le variabili con percorso abilitato in [Variabili del traffico](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti.

## Popolare le dimensioni di ingresso con i dati

Una determinata dimensione di ingresso è basata sulla variabile di traffico associata. Se la variabile non entry ha dati, anche la dimensione di ingresso associata contiene dati. Non sono necessarie modifiche di implementazione per le dimensioni di ingresso se le variabili di traffico contengono dati.

## Elementi dimensionali

Poiché le variabili di ingresso sono in genere basate su stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensionali desiderati. I valori in una data dimensione di ingresso corrispondono agli elementi dimensionali nella dimensione non di ingresso associata. Ad esempio, gli elementi dimensionali nella dimensione &quot;Pagina di ingresso&quot; contengono elementi dimensionali simili nella dimensione &quot;Pagina&quot;.

## Pagina di ingresso originale

La dimensione &quot;Originale pagina di ingresso&quot; funziona in modo diverso rispetto ad altre dimensioni di ingresso. Invece di conservare la pagina di ingresso per una data visita, conserva la prima pagina di ingresso per l’intera durata del cookie del visitatore. Ad esempio, se accedi a `https://example.com/page4` per la tua prima visita al sito, poi un anno dopo atterrare su `https://example.com/store`, gli elenchi delle dimensioni originali della pagina di ingresso `https://example.com/page4` come elemento della dimensione.
