---
title: Dimensioni di ingresso
description: Elenca le dimensioni delle voci e il loro utilizzo.
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---


# Dimensioni di ingresso

*Questa pagina della guida descrive il funzionamento delle voci come una dimensione. Per informazioni sul funzionamento delle voci come metriche, vedi la metrica[Voci](../metrics/entries.md).*

Le dimensioni di ingresso sono basate sulle visite. Registrano il primo elemento di dimensione e lo mantengono per tutta la durata della visita. Le dimensioni delle voci sono disponibili per tutte le variabili con percorso abilitato nelle variabili [](/help/admin/admin/c-traffic-variables/traffic-var.md) Traffico nelle impostazioni della suite di rapporti.

## Compilare le dimensioni delle voci con i dati

Una determinata dimensione di voce è basata sulla variabile di traffico associata. Se la variabile non entry ha dei dati, la dimensione di immissione associata contiene anche dei dati. Non sono necessarie modifiche di implementazione per le dimensioni di immissione se le variabili di traffico contengono dati.

## Elementi dimensione

Poiché le variabili di voce sono in genere basate su stringhe personalizzate nell’implementazione, l’organizzazione determina quali elementi dimensione sono. I valori in una data dimensione di immissione corrispondono agli elementi dimensione nella dimensione associata non di immissione. Ad esempio, gli elementi dimensionali nella dimensione &quot;Pagina entrata&quot; contengono elementi dimensionali simili nella dimensione &quot;Pagina&quot;.

## Pagina iniziale originale

La dimensione &quot;Originale pagina iniziale&quot; funziona in modo diverso rispetto alle altre dimensioni di immissione. Anziché conservare la pagina di immissione per una determinata visita, viene mantenuta la prima pagina di immissione per l’intera durata del cookie del visitatore. Ad esempio, se accedete `https://example.com/page4` per la prima visita al sito, un anno dopo accedete al sito `https://example.com/store`, la dimensione originale della pagina di immissione viene elencata `https://example.com/page4` come elemento dimensione.
