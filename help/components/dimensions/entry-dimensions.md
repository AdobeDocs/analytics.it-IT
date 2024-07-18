---
title: Dimensioni di entrata
description: Elenca le dimensioni di entrata e il relativo utilizzo.
keywords: pagina di ingresso, sezione del sito di ingresso, server di ingresso, approfondimenti personalizzati della voce
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 2%

---

# Dimensioni di entrata

*Questa pagina della Guida descrive il funzionamento delle voci come [dimensione](overview.md). Per informazioni sul funzionamento delle voci come metrica, vedi la metrica [Voci](../metrics/entries.md).*

Le dimensioni di ingresso sono [basate sulle visite](../metrics/visits.md). Registrano il primo elemento dimensione e lo mantengono per l’intera durata di tale visita. Le dimensioni di ingresso sono disponibili per tutte le variabili con percorsi abilitati in [Variabili di traffico](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti.

>[!TIP]
>Se desideri visualizzare i dati in base al primo hit di una visita invece del primo valore visualizzato in una visita, puoi utilizzare un [segmento](/help/components/segmentation/seg-overview.md). Utilizza un contenitore di hit in cui [Profondità di hit](hit-depth.md) è uguale a 1, quindi utilizza quel segmento con la variabile desiderata.

## Compilare dimensioni di immissione con i dati

Una data voce [dimensione](overview.md) è basata sulla variabile di traffico associata. Se la variabile non di immissione contiene dati, anche la dimensione di immissione associata contiene dati. Se le variabili di traffico contengono dati, non sono necessarie modifiche all’implementazione per le dimensioni di immissione.

## Elementi dimensionali

Poiché le variabili di ingresso sono in genere basate su stringhe personalizzate nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. I valori in una determinata dimensione di ingresso corrispondono agli elementi dimensionali nella dimensione non di ingresso associata. Ad esempio, gli elementi dimensione nella dimensione &quot;Pagina di ingresso&quot; contengono elementi dimensione simili nella dimensione &quot;Pagina&quot;.

## Pagina di ingresso originale

La dimensione &quot;Pagina di ingresso originale&quot; funziona in modo diverso rispetto alle altre dimensioni di ingresso. Invece di conservare la pagina di ingresso per una determinata visita, conserva la prima pagina di ingresso per l’intera durata del cookie del visitatore. Ad esempio, se arrivi a `https://example.com/page4` per la tua prima visita al sito e un anno dopo arrivi a `https://example.com/store`, la dimensione &quot;Pagina di ingresso originale&quot; elenca `https://example.com/page4` come elemento della dimensione.
