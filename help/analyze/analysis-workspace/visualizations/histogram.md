---
description: Scopri come utilizzare un istogramma, simile a un grafico a barre, ma che raggruppa i numeri in intervalli.
title: Istogramma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
TQID: 'https://experienceleague.adobe.com/8sr6lBHkp8zWeToEqPsd9ZFRCMGNj2A1fn57d5wgvOI'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 917804b359e040bc04282fe69e05a1a4b6e9bdc4
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 53%

---

# Istogramma {#histogram}

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Istogramma"
>abstract="Crea una visualizzazione a istogramma per rappresentare la distribuzione dei dati numerici in gruppi di intervalli."


>[!BEGINSHADEBOX]

_In questo articolo viene documentata la visualizzazione Istogramma in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Vedere [Istogramma](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/histogram) per la_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** versione di questo articolo._

>[!ENDSHADEBOX]


Una visualizzazione a **[!UICONTROL Histogram]** ![istogramma](/help/assets/icons/Histogram.svg) è simile a una visualizzazione [!UICONTROL Bar], ma con i numeri raggruppati in intervalli (bucket). Analytics automatizza la creazione di intervalli di numeri, ma puoi comunque cambiare le impostazioni in [Impostazioni avanzate](#advanced-settings).

## Utilizzo

Per creare un istogramma:

1. Aggiungi una visualizzazione a **[!UICONTROL Histogram]** ![istogramma](/help/assets/icons/Histogram.svg). Consulta [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel).
1. Trascinare una metrica dall&#39;elenco dei componenti **[!UICONTROL Metrics]** oppure selezionare una metrica dal menu a discesa [!UICONTROL *Aggiungi una metrica*].
1. (facoltativo) Seleziona **[!UICONTROL Show advanced settings]**. Consulta [Impostazioni avanzate](#advanced-settings).
1. Seleziona **[!UICONTROL Build]**.

>[!NOTE]
>
>Gli istogrammi supportano solo metriche standard; le metriche calcolate non sono supportate.

Nell’esempio seguente, viene utilizzato un istogramma per le sessioni di bucket relative al numero di persone. L’istogramma mostra che la maggior parte delle persone ha tra 16 e 21 sessioni per l’intervallo di date selezionato.

![](assets/histogram.png)

## Impostazioni avanzate

Come parte della visualizzazione, sono disponibili impostazioni specifiche dell’istogramma.

| Impostazioni istogramma | Descrizione |
|---|---|
| **[!UICONTROL Starting bucket]** | Determina con quale bucket inizia l’istogramma. &quot;1&quot; è il valore predefinito. È possibile impostare i numeri iniziali da 0 a infinito (nessun numero negativo). |
| **[!UICONTROL Metric buckets]** | Consente di aumentare/diminuire il numero di intervalli di dati (bucket). Il numero massimo consentito è 50. |
| **[!UICONTROL Metric bucket size]** | Consente di impostare la dimensione di ciascun bucket. Ad esempio, puoi modificare la dimensione del bucket dalla visualizzazione a 1 pagina a 2 visualizzazioni di pagina. |
| **[!UICONTROL Counting method]** | Seleziona tra **[!UICONTROL Person]**, **[!UICONTROL Session]**, **[!UICONTROL Event]** o **[!UICONTROL Products]** (per [analisi sub-hit](/help/components/segmentation/sub-hit.md)). Ad esempio, visualizzazioni pagina per sessione, visualizzazioni pagina per persona, visualizzazioni pagina per evento o visualizzazione pagina per prodotto. |

<!--Russ or Meike - Check Hit Type link above. -->

**Esempi**:

| Bucket iniziale | Bucket metrica | Dimensione bucket di metrica | Risultato |
|:----:|:--:|:--:|:--|
| 1 | 5 | 2 | ![Istogramma, bucket iniziale 1, bucket metrica 5, dimensione bucket metrica 2](assets/histogram-1-5-2.png) |
| 0 | 3 | 5 | ![Istogramma, bucket iniziale 0, bucket metrica 3, dimensione bucket metrica 5](assets/histogram-0-3-5.png) |

>[!MORELIKETHIS]
>
>[Aggiungi una visualizzazione a un pannelloImpostazioni di visualizzazioneMenu di scelta rapida visualizzazioneUtilizzo di istogrammi per identificare valori di dati imprevisti](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168)

