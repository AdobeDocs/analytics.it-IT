---
title: Panoramica sulle dimensioni
description: Scopri che cosa sono le dimensioni e come vengono utilizzate in Adobe Analytics.
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
TQID: https://experienceleague.adobe.com/WypIneraYlrSyIpXv3UQWIFn42A-Dxi0SxeJ2VbeubQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 434
ht-degree: 29%

---

# Panoramica delle dimensioni

Le dimensioni sono delle variabili in Adobe Analytics che in genere contengono valori stringa. Le dimensioni comuni includono [Pagina](page.md), [Dominio di riferimento](referring-domain.md) o una [eVar](evar.md). Al contrario, le [metriche](../metrics/overview.md) contengono valori numerici che si legano a una dimensione. Un rapporto di base mostra righe di valori stringa (dimensioni) rispetto a una colonna di valori numerici (metriche).

Ad esempio, se hai combinato la dimensione **[!UICONTROL Page]** con la metrica **[!UICONTROL Visits]**, otterrai un rapporto con classifica che mostra le pagine più visitate:

| Pagina | Visite |
| --- | ---: |
| Pagina Home | 800 |
| Pagina di prodotto | 500 |
| Pagina di acquisto | 100 |

{style="table-layout:fixed"}

Ogni dimensione rappresenta una parte o un facet diversi del sito. Puoi combinare una o più di queste dimensioni con una o più metriche per creare un rapporto desiderato.

## Aggiungere descrizioni delle dimensioni

Gli amministratori di Analytics possono aggiungere descrizioni per le dimensioni e altri componenti direttamente nella suite di rapporti o in Analysis Workspace. Per informazioni su come aggiungere descrizioni alle dimensioni, consulta [Aggiungere descrizioni dei componenti](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Dimensioni ritirate

Le seguenti dimensioni vengono ritirate. La maggior parte erano rapporti Reports &amp; Analytics non disponibili in Analysis Workspace. Sono documentati qui come riferimento se li si trova in rapporti o dati storici precedenti.

* **Gerarchia**: dimensione personalizzata (`hier1`-`hier5`) utilizzata per acquisire la struttura gerarchica di un sito per i report. È ritirato e non disponibile in Analysis Workspace. Utilizza invece [eVar](evar.md) e classificazioni.
* **Home page**: flag che indica se la pagina corrente è la home page del browser del visitatore. Si tratta di una dimensione legacy senza equivalenti moderni a causa delle pratiche moderne in materia di privacy del browser.
* **Supporto JavaScript**: indica se il browser del visitatore supporta JavaScript. Una dimensione legacy che non è più significativa per le misurazioni moderne.
* **Versione JavaScript**: segnalata la versione JavaScript supportata dal browser del visitatore. Una dimensione legacy che non viene più raccolta.
* **Pagina successiva**: dimensione di percorso che mostra la pagina successiva visualizzata da un visitatore. Utilizza la [Visualizzazione flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) in Analysis Workspace per le dimensioni del percorso corrente.
* **Pagina precedente**: dimensione di percorso che mostra la pagina precedente visualizzata da un visitatore. Utilizza la [Visualizzazione flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) in Analysis Workspace per le dimensioni del percorso corrente.
* **Fuso orario**: il fuso orario del visitatore, derivato dallo scostamento della marca temporale nelle richieste di immagini AppMeasurement. Web SDK raccoglie il fuso orario utilizzando [`placeContext`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/context).
* **Dominio di primo livello**: dominio di primo livello del punto di accesso del visitatore. Un report legacy di Reports &amp; Analytics; utilizza invece la dimensione [Dominio](domain.md).
* **Numero pagina visita**: numero di pagina all&#39;interno di una visita. Un report legacy di Reports &amp; Analytics; utilizza invece la dimensione [Profondità di hit](hit-depth.md).
* **Stato visitatore**: segnalato lo stato USA dalla variabile `s.state`. È stato ritirato a favore della dimensione [Stati USA](us-states.md), che utilizza la geosegmentazione.
