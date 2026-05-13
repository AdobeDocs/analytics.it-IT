---
description: (Facoltativo) Prima di importare le classificazioni nei rapporti di marketing, puoi scaricare un modello per la creazione di un file di dati delle classificazioni. Il file di dati utilizza le classificazioni desiderate come intestazioni di colonna, quindi organizza il set di dati di reporting sotto le intestazioni di classificazione appropriate.
title: Modello di classificazione
feature: Classifications
exl-id: e299509a-0c4f-4ba8-9e91-96356c386054
TQID: https://experienceleague.adobe.com/OR9THCLd93iUl58npPiinO4yAsK8KG3FU8qmBILHioY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 346
ht-degree: 5%

---

# Modello di classificazione (legacy)

{{classification-importer-deprecation}}

(Facoltativo) Prima di importare le classificazioni in rapporti e progetti, puoi scaricare un modello che ti aiuti a creare un file di dati delle classificazioni. Il file di dati utilizza le classificazioni desiderate come intestazioni di colonna, quindi organizza il set di dati di reporting sotto le intestazioni di classificazione appropriate.

## Modello di classificazione {#concept_0F06847AD8D042F5BA818AE3C37E2417}

(Facoltativo) Prima di importare le classificazioni nei rapporti di marketing, puoi scaricare un modello per la creazione di un file di dati delle classificazioni. Il file di dati utilizza le classificazioni desiderate come intestazioni di colonna, quindi organizza il set di dati di reporting sotto le intestazioni di classificazione appropriate.

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

| Elemento | Descrizione |
| --- | ---|
| Seleziona suite di rapporti | Seleziona la suite di rapporti da utilizzare nel modello. La suite di rapporti e il set di dati devono corrispondere. |
| Set di dati da classificare | Selezionare il tipo di dati per il file di dati. Il menu include tutti i rapporti nelle suite di rapporti configurati per le classificazioni. |
| Esporta numerico 2 | **Importante**: questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione. |
| Codifica | Selezionare la codifica dei caratteri per il file di dati. Il formato di codifica predefinito è UTF-8.<br>**Importante**: questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione. |
| Scaricare | Scarica il file modello. |

Il modello include le classificazioni attualmente definite (intestazioni di colonna) di un set di dati specifico senza includere i dati associati a ciascuna classificazione.

>[!NOTE]
>
>Il metodo Template limita il download dei dati di classificazione a una singola suite di rapporti.

Per ulteriori informazioni sulla struttura del file di dati, vedere [Informazioni sui file di dati di classificazione](/help/components/classifications/importer/c-saint-data-files.md).

## Scaricare un modello di dati delle classificazioni (facoltativo) {#task_8DFCF309B6FD43ABB1D6FEE9AFAEC596}

Il modello fornisce il formato di file da seguire per le classificazioni.

>[!NOTE]
>
>Il metodo Template limita il download dei dati a una singola suite di rapporti.

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Nella scheda **[!UICONTROL Download Template]**, specifica la [configurazione del modello dati](/help/components/classifications/importer/c-download-saint-data.md).
1. Fai clic su **[!UICONTROL Download]**.
1. Salvare il file modello nel sistema locale.

   Il file modello è un file di dati delimitato da tabulazioni (estensione del nome file [!DNL .tab]) supportato dalla maggior parte delle applicazioni per fogli di calcolo.
