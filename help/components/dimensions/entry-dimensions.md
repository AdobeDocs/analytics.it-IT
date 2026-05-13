---
title: Dimensioni di entrata
description: Elenca le dimensioni di entrata e il relativo utilizzo.
keywords: pagina di ingresso, sezione del sito di ingresso, server di ingresso, insight personalizzato di ingresso
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
TQID: https://experienceleague.adobe.com/6a6Xy8SEqjcnuB1Acbwkesw6OA7Nggld5ppWtjYaj5k
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 292
ht-degree: 2%

---

# Dimensioni di entrata

*Questa pagina della Guida descrive il funzionamento delle voci come [dimensione](overview.md). Per informazioni sul funzionamento delle voci come metrica, vedi la metrica [Voci](../metrics/entries.md).*

Le dimensioni di ingresso sono [basate sulle visite](../metrics/visits.md). Registrano il primo elemento dimensione e lo mantengono per l’intera durata di tale visita. Le dimensioni di ingresso sono disponibili per tutte le variabili con percorsi abilitati in [Variabili di traffico](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti.

>[!TIP]
>Se desideri visualizzare i dati in base al primo hit di una visita invece del primo valore visualizzato in una visita, puoi utilizzare un [segmento](/help/components/segmentation/seg-overview.md). Utilizza un contenitore di hit in cui [Profondità di hit](hit-depth.md) è uguale a 1, quindi utilizza quel segmento con la variabile desiderata.

## Compilare dimensioni di immissione con i dati

Una data voce [dimensione](overview.md) è basata sulla variabile di traffico associata. Se la variabile non di immissione contiene dati, anche la dimensione di immissione associata contiene dati. Se le variabili di traffico contengono dati, non sono necessarie modifiche all’implementazione per le dimensioni di immissione.

## Elementi dimensionali

Poiché le variabili di ingresso sono in genere basate su stringhe personalizzate nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. I valori in una determinata dimensione di ingresso corrispondono agli elementi dimensionali nella dimensione non di ingresso associata. Ad esempio, gli elementi dimensione nella dimensione &quot;Pagina di ingresso&quot; contengono elementi dimensione simili nella dimensione &quot;Pagina&quot;.

## Pagina di ingresso originale

La dimensione &quot;Pagina di ingresso originale&quot; funziona in modo diverso rispetto alle altre dimensioni di ingresso. Invece di conservare la pagina di ingresso per una determinata visita, conserva la prima pagina di ingresso per l’intera durata del cookie del visitatore. Ad esempio, se arrivi a `https://example.com/page4` per la tua prima visita al sito e un anno dopo arrivi a `https://example.com/store`, la dimensione &quot;Pagina di ingresso originale&quot; elenca `https://example.com/page4` come elemento della dimensione.
