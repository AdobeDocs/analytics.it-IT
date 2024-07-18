---
description: È possibile suddividere dimensioni ed elementi dimensionali in Analysis Workspace.
keywords: Analysis Workspace
title: Suddividere dimensioni
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 80%

---

# Suddividere dimensioni

È possibile suddividere dimensioni ed elementi dimensionali in Analysis Workspace.

Analizza i dati in tantissimi modi per ogni necessità; realizza query con metriche, dimensioni, segmenti, linee temporali e altri valori rilevanti.

1. [Crea un progetto](/help/analyze/analysis-workspace/home.md) con una tabella di dati.
1. Nella tabella di dati, fai clic con il pulsante destro del mouse su un elemento e seleziona **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Risultato del passaggio](assets/fa_data_table_actions.png)

   Puoi analizzare metriche per elementi dimensionali o segmenti di pubblico in diversi periodi di tempo selezionati. Puoi anche effettuare analisi molto più dettagliate.

   >[!NOTE]
   >
   >È possibile mostrare nella tabella un massimo di 200 analisi. Questo limite aumenterà per le esportazioni.

## Applicare modelli di attribuzione ai raggruppamenti

A qualsiasi raggruppamento all’interno di una tabella può essere applicato anche qualsiasi modello di attribuzione. Tale modello di attribuzione può essere lo stesso o diverso dalla colonna principale. Ad esempio, puoi analizzare gli ordini lineari sulla dimensione canali di marketing, ma applicare ordini a forma di U agli specifici codici di tracciamento all’interno di un canale. Per modificare il modello di attribuzione applicato a un raggruppamento, passa il cursore sul modello di raggruppamento e fai clic su **[!UICONTROL Edit]**:

![Impostazioni di raggruppamento](assets/breakdown_settings.png)

Questo è il comportamento previsto quando si applicano modelli di attribuzione ai raggruppamenti o quando questi vengono modificati:

* Se applichi un’attribuzione quando non esistono altre attribuzioni, questa si applica all’intera struttura ad albero della colonna.

* Se aggiungi un raggruppamento dopo l’applicazione di un’attribuzione, per il raggruppamento aggiunto verrà utilizzato il valore predefinito, se tale dimensione ha un valore predefinito. In caso contrario, utilizzerà il raggruppamento dalla colonna padre. Alcune dimensioni hanno un’allocazione predefinita.  Ad esempio, [!UICONTROL Time] dimensioni e [!UICONTROL Referrer] utilizzano [!UICONTROL Same Touch]. La dimensione [!UICONTROL Product] utilizza [!UICONTROL Last Touch]. Altre dimensioni non hanno un valore predefinito e utilizzeranno l’allocazione della colonna padre.

* Se la struttura ad albero della colonna contiene già delle attribuzioni, la modifica dell’attribuzione ha effetto solo su quella che si sta modificando.

## Video

Aggiungere dimensioni e metriche al progetto in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606/?quality=12)

Utilizzo delle dimensioni nelle tabelle a forma libera:

>[!VIDEO](https://video.tv.adobe.com/v/40179/?quality=12)

Ecco un video sulle suddivisioni delle dimensioni per posizione:

>[!VIDEO](https://video.tv.adobe.com/v/24033/?quality=12)
