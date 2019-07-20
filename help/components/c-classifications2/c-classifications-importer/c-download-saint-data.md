---
description: (Facoltativo) Prima di importare le classificazioni nei rapporti di marketing, puoi scaricare un modello che aiuta a creare un file di dati di classificazione. Il file di dati utilizza le classificazioni desiderate come intestazioni di colonna, quindi organizza il set di dati di reporting nelle intestazioni di classificazione appropriate.
seo-description: (Facoltativo) Prima di importare le classificazioni nei rapporti di marketing, puoi scaricare un modello che aiuta a creare un file di dati di classificazione. Il file di dati utilizza le classificazioni desiderate come intestazioni di colonna, quindi organizza il set di dati di reporting nelle intestazioni di classificazione appropriate.
seo-title: Modello di classificazione
solution: Analytics
subtopic: Classificazioni
title: Modello di classificazione
topic: Strumenti di amministrazione
uuid: 4 edd 411 b -164 c -4 b 4 d-a 872-b 57 a 3163 ca 72
translation-type: tm+mt
source-git-commit: 1986561a83f22619b627d754376f7e936902a737

---


# Modello di classificazione

(Facoltativo) Prima di importare le classificazioni nei rapporti di marketing, puoi scaricare un modello che aiuta a creare un file di dati di classificazione. Il file di dati utilizza le classificazioni desiderate come intestazioni di colonna, quindi organizza il set di dati di reporting nelle intestazioni di classificazione appropriate.

## Classification template {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Facoltativo) Prima di importare le classificazioni nei rapporti di marketing, puoi scaricare un modello che aiuta a creare un file di dati di classificazione. Il file di dati utilizza le classificazioni desiderate come intestazioni di colonna, quindi organizza il set di dati di reporting nelle intestazioni di classificazione appropriate.

**[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.

| Elemento | Descrizione |
|---|---|
| Seleziona suite di rapporti | Seleziona la suite di rapporti da usare nel modello. La suite di rapporti e il set di dati devono corrispondere. |
| Set di dati da classificare | Selezionare il tipo di dati per il file di dati. Il menu include tutti i rapporti nelle suite di rapporti configurati per le classificazioni. |
| Esporta numerico 2 | Potete importare classificazioni numeriche 2 nel sistema tramite l'importazione. Numeric 2 classifications are useful for variables that change over time for different items, such as cost and budget values for the [!UICONTROL Marketing Channel] report. See [Numeric 2 Classifications](../../../components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md#concept_71024B7B91DF4E909076062AB1380D8B) for information about uploading data using numeric 2 classifications. |
| Codifica | Selezionare la codifica caratteri per il file di dati. Il formato di codifica predefinito è UTF -8. |
| Scarica | Scarica il file modello. |

Il modello include le classificazioni (intestazioni di colonna) attualmente definite di un set di dati specifico, senza includere i dati associati a ciascuna classificazione.

>[!NOTE]
>
>Il metodo Template (Modello) limita il download di dati di classificazione a una singola suite di rapporti.

For more information about the data file structure, see [About Classification Data Files](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_EBA7669C546040BE8162ADACA3548735).

## Download a classifications data template (optional) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

Il modello fornisce il formato di file da seguire per le classificazioni.

>[!NOTE]
>
>Il metodo Template (Modello) limita il download dei dati a una singola suite di rapporti.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. On the **[!UICONTROL Download Template]** tab, specify the [data template configuration](../../../components/c-classifications2/c-classifications-importer/c-download-saint-data.md#concept_0F06847AD8D042F5BA818AE3C37E2417).
1. Fai clic su **[!UICONTROL Download]**.
1. Salvare il file modello nel sistema locale.

   The template file is a tab-delimited data file ( [!DNL .tab] filename extension) that most spreadsheet applications support.

