---
title: Server
description: Nome del server.
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
TQID: https://experienceleague.adobe.com/BDVwwy3jCtHrcWLy2nOHVnDRbFiAoR-EeOzp-35XjBs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 7%
---
# Server

La [dimensione](overview.md) del &#39;server&#39; elenca in genere il nome host del sito. Per le suite di rapporti che combinano più domini o sottodomini, questa dimensione è utile per vedere quali domini o sottodomini offrono le prestazioni migliori.

Questa dimensione è correlata alle dimensioni [Pagina](page.md) e [Sezione sito](site-section.md). La pagina è più granulare, il server meno granulare e la sezione Sito è compresa tra le due.

## Popolare questa dimensione con i dati

AppMeasurement raccoglie questi dati utilizzando la variabile [`server`](/help/implement/vars/page-vars/server.md), funzionalmente identica a una prop.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | [`server`](/help/implement/vars/page-vars/server.md) |
| **Campo Web SDK / XDM** | [`web.webPageDetails.server`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parametro query** | [`server`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<server>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 100 byte |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli elementi di Dimension includono i server del sito. L’organizzazione determina gli elementi dimensionali specifici che desideri utilizzare. Alcune organizzazioni utilizzano `window.location.hostname`, mentre altre formulano valori personalizzati. Indipendentemente dal metodo utilizzato, assicurati che sia coerente e che venga registrato in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).
