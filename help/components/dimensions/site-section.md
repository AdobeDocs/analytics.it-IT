---
title: Sezione del sito
description: Nome della sezione del sito.
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
TQID: https://experienceleague.adobe.com/fZwN-24--98XULDEgHR-5dcIsiYXspaSOsv1t-M0iys
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
source-wordcount: '179'
ht-degree: 8%
---
# Sezione del sito

Nella &#39;Sezione del sito&#39; [dimensione](overview.md) sono elencati i nomi delle sezioni del sito. Per i siti di grandi dimensioni, è utile raggruppare le pagine in sezioni. Questa dimensione è utile per visualizzare le sezioni del sito con le prestazioni migliori o più elevate.

Questa dimensione è correlata alle dimensioni [Pagina](page.md) e [Server](server.md). La pagina è più granulare, il server meno granulare e la sezione Sito è compresa tra le due.

## Popolare questa dimensione con i dati

AppMeasurement raccoglie questi dati utilizzando la variabile [`channel`](/help/implement/vars/page-vars/channel.md).

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | [`channel`](/help/implement/vars/page-vars/channel.md) |
| **Campo Web SDK / XDM** | [`web.webPageDetails.siteSection`](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parametro query** | [`ch`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<channel>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 100 byte |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli elementi di Dimension includono i nomi delle sezioni del sito. L’organizzazione determina gli elementi dimensionali specifici che desideri utilizzare. Indipendentemente dal metodo utilizzato, assicurati che sia coerente e che venga registrato in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).
