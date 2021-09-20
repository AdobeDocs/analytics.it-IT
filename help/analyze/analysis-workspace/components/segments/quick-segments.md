---
description: Utilizzare segmenti rapidi in Analysis Workspace.
title: Segmenti rapidi
feature: Workspace Basics
role: User, Admin
source-git-commit: 8cd5d5ec1525e29779a13330dfeaeae120dfdd56
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---


# Segmenti rapidi

Puoi creare segmenti rapidi all&#39;interno di un progetto per bypassare la complessità del generatore di segmenti [completo](/help/components/segmentation/segmentation-workflow/seg-build.md). Per un confronto tra le attività dei segmenti veloci e quelle dei segmenti a livello di componente completi, visita [qui](/help/analyze/analysis-workspace/components/segments/t-freeform-project-segment.md).

>[!IMPORTANT]
> I segmenti rapidi sono attualmente in fase di test limitati e non sono ancora generalmente disponibili.

## Creare segmenti rapidi

1. In una tabella a forma libera, fai clic sull’icona del filtro+ nell’intestazione del pannello:

   ![](assets/quick-seg1.png)

   Tieni presente che:

   - Esiste un solo contenitore di segmenti che consente di includere una dimensione/metrica/intervallo di date nel segmento (o escluderlo da).
   - Puoi impostare il contenitore a livello di Hit, Visita o Visitatore. Il valore predefinito è Hit.

1. Aggiungi una dimensione/metrica/intervallo di date in uno dei tre modi seguenti:

   - Inizia a digitare e il generatore di segmenti rapidi trova automaticamente il componente appropriato.
   - Utilizza l’elenco a discesa per trovare il componente.
   - Trascina i componenti dalla barra a sinistra.

1. Specifica la prima regola, ad esempio `Page equals workspace`. Puoi avere fino a tre regole nelle definizioni dei segmenti. Fai clic sul segno &quot;+&quot; per aggiungere un’altra regola. Puoi aggiungere i qualificatori &quot;AND&quot; o &quot;OR&quot; alle regole, ma non puoi combinare &quot;AND&quot; e &quot;OR&quot; in una singola definizione di segmento.

   Ecco un esempio di segmento che combina dimensioni e metriche:

