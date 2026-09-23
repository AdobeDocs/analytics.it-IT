---
title: Pagine non trovate (dimensioni)
description: URL che hanno restituito un errore sul sito.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc
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
source-wordcount: '273'
ht-degree: 5%
---
# Pagine non trovate

>[!BEGINSHADEBOX]

*Questa pagina della Guida descrive il funzionamento di &quot;Pagine non trovate&quot; come [dimensione](overview.md). Consulta la pagina delle metriche [Pagine non trovate](../metrics/pages-not-found.md) per informazioni sul funzionamento come metrica.*

>[!ENDSHADEBOX]

La dimensione &quot;Pagine non trovate&quot; mostra gli URL che contenevano un errore. Questa dimensione è utile quando desideri ridurre il numero di errori che i visitatori ricevono sul sito.

* Puoi utilizzare questa dimensione in una [Visualizzazione del flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) per vedere quali pagine i visitatori fanno clic per raggiungere l&#39;errore. Puoi quindi lavorare con i team di sviluppo della tua organizzazione per correggere il collegamento su ogni pagina.
* Puoi utilizzare questa dimensione con la dimensione [&#39;Referrer&#39;](referrer.md) per vedere dove i visitatori arrivano al tuo sito da collegamenti esterni. Puoi quindi implementare i reindirizzamenti alla posizione desiderata o collaborare con terze parti per correggere il collegamento.

>[!NOTE]
>
>In Data Warehouse questa dimensione è denominata &#39;[!UICONTROL Page Type Error]&#39;.

## Popolare questa dimensione con i dati

AppMeasurement raccoglie questi dati utilizzando la variabile [`pageType`](/help/implement/vars/page-vars/pagetype.md). Quando `pageType` è impostato su `errorPage`, l&#39;URL della pagina dell&#39;hit viene registrato come elemento dimensione. Se la variabile `pageType` non è definita o è impostata su un altro valore, non vengono raccolti dati per questa dimensione.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | [`pageType`](/help/implement/vars/page-vars/pagetype.md) |
| **Campo Web SDK / XDM** | [`web.webPageDetails.isErrorPage`](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parametro query** | [`pageType`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<pageType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | N/D |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli elementi di Dimension includono gli URL delle pagine del sito in cui si è verificato un errore.
