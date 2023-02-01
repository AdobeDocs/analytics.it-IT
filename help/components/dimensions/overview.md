---
title: Panoramica delle dimensioni
description: Variabili che contengono valori stringa.
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
source-git-commit: 3ed4c075578ef31cec4b1c825039eae989c813dc
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 2%

---

# Panoramica delle dimensioni

I Dimension sono variabili in Adobe Analytics che in genere contengono valori stringa. Le dimensioni comuni includono [Pagina](page.md), [Dominio di riferimento](referring-domain.md)o [eVar](evar.md). Al contrario, [metriche](../metrics/overview.md) contengono valori numerici che si legano a una dimensione. Un rapporto di base mostra righe di valori stringa (dimensione) rispetto a una colonna di valori numerici (metrica).

Ad esempio, se hai combinato la dimensione &quot;Pagina&quot; con la metrica &quot;Visite&quot;, riceverai un rapporto di classifica che mostra le pagine più visitate:

| `Page` | `Visits` |
| --- | --- |
| `Home page` | `800` |
| `Product page` | `500` |
| `Purchase page` | `100` |

Ogni dimensione rappresenta una parte o un volto diverso del sito. Puoi combinare una o più di queste dimensioni con una o più metriche per creare un rapporto desiderato.

## Aggiungi descrizioni delle dimensioni

Gli amministratori di Analytics possono aggiungere descrizioni per dimensioni e altri componenti sia all’interno della suite di rapporti che direttamente in Analysis Workspace. Per informazioni su come aggiungere descrizioni alle dimensioni, consulta [Aggiungi descrizioni dei componenti](/help/analyze/analysis-workspace/components/add-component-descriptions.md).
