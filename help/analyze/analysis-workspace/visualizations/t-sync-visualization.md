---
description: Scopri come sincronizzare una tabella a forma libera o un’origine dati con la visualizzazione corrispondente.
keywords: Analysis Workspace, sincronizzazione di una visualizzazione con un’origine dati
title: Gestire le origini dati
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 85%

---

# Gestione delle origini dati {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Blocca selezione"
>abstract="Abilita questa impostazione per bloccare la visualizzazione nelle posizioni o gli elementi selezionati nell’origine dati."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostra tabella"
>abstract="Selezionando **[!UICONTROL Show table]** verrà generata una nuova origine dati per la visualizzazione corrente, separata dall’origine dati originale."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Mostra tabella"
>abstract="Seleziona **[!UICONTROL Show table]** per generare una nuova origine dati per la visualizzazione corrente, separata dall&#39;origine dati originale."


La sincronizzazione delle visualizzazioni consente di controllare quale tabella a forma libera o origine dati corrisponde a una visualizzazione.


>[!TIP]
>
>Puoi individuare le visualizzazioni correlate dal colore del ![StatusOrange](/help/assets/icons/StatusOrange.svg) accanto al titolo delle visualizzazioni. Colori uguali indicano che le visualizzazioni si basano sulla stessa origine dati.
>

Puoi visualizzare o nascondere l’origine dati. Puoi inoltre bloccare la selezione in base alle posizioni o agli elementi selezionati. Queste impostazioni determinano in che modo la visualizzazione cambia o meno con l’arrivo di nuovi dati.

![La finestra di dialogo delle opzioni di origine dati mostra le opzioni descritte nella sezione successiva.](assets/lock-selection.png)

<!--
**Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table and a [visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data source settings](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

| Opzione | Descrizione |
|--- |--- |
| **[!UICONTROL Data source]** | Dal menu a discesa, seleziona l’origine dati su cui si basa la visualizzazione. |
| **[!UICONTROL Linked visualizations]** | Elenca tutte le visualizzazioni collegate. Si applica all’origine dati (tabella a forma libera). |
| **[!UICONTROL Show data source]** | Consente di mostrare o nascondere l’origine dati (tabella a forma libera) corrispondente alla visualizzazione. |
| **[!UICONTROL Lock Selection]** | Seleziona questa opzione per bloccare la visualizzazione ![LockClosed](/help/assets/icons/LockClosed.svg) ai dati attualmente selezionati nella tabella di dati corrispondente. Dopo aver abilitato questa opzione, scegli tra:  <ul><li>**Posizioni selezionate**: la visualizzazione è bloccata sulle **posizioni** selezionate nella tabella di dati corrispondente. Queste posizioni continuano a essere visualizzate, anche se gli elementi specifici in queste posizioni cambiano (ad esempio a causa di ordinamento o filtri). Ad esempio, seleziona questa opzione se desideri visualizzare sempre i primi cinque nomi di campagna elencati nell’origine dati di questa visualizzazione. Indipendentemente dai nomi delle campagne visualizzati.</li> <li>**Elementi selezionati**: la visualizzazione è bloccata su **elementi** specifici attualmente selezionati nella tabella di dati corrispondente. Questi elementi continuano a essere visualizzati, anche se cambiano posizione nella classificazione rispetto agli elementi della tabella. Ad esempio, seleziona questa opzione se desideri visualizzare sempre gli stessi cinque nomi di campagna specifici elencati nell’origine dati di questa visualizzazione. Indipendentemente dalla posizione nella classificazione di quei nomi di campagna.</li></ul>Se la visualizzazione è bloccata su dati che non sono più visibili nella tabella di dati connessa, puoi generare una nuova tabella. Seleziona **[!UICONTROL Show table]** per generare una nuova origine dati per la visualizzazione corrente, separata dall’origine dati originale. |
