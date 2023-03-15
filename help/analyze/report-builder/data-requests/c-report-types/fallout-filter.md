---
description: Descrive i passaggi necessari per applicare filtri a un rapporto di fallout.
title: Filtrare un rapporto di fallout mediante la Creazione guidata richieste
feature: Report Builder
role: User, Admin
exl-id: 6134d7d4-7287-4a83-92b6-d250ca15cf69
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 11%

---

# Filtrare un rapporto di fallout mediante la Creazione guidata richieste

Descrive i passaggi necessari per applicare filtri a un rapporto di fallout.

Questo esempio mostra il rapporto Fallout pagina.

1. In Adobe Report Builder, fai clic su **[!UICONTROL Create]** per aprire la Creazione guidata richieste.
1. Seleziona la suite di rapporti corretta.
1. Nella struttura a sinistra, seleziona **[!UICONTROL Paths]** > **[!UICONTROL Page]** > **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. Configura l’appropriato [intervalli di date](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).
1. Fai clic su **[!UICONTROL Next]** (Usa modello di attribuzione non predefinito).
1. Nel passaggio 2 della procedura guidata, sotto **[!UICONTROL Row Labels]**, fare clic su **[!UICONTROL Define Checkpoints]** collegamento. In un rapporto di fallout, è sempre necessario definire gli elementi del percorso, a differenza di un rapporto di percorso, in cui un pattern è preapplicato.

   ![](assets/define_checkpoints.png)

1. Seleziona l&#39;opzione **[!UICONTROL Filter]**.

1. In **[!UICONTROL Define Site Section Fallout Checkpoints]** definire punti di controllo da un intervallo di celle o da un elenco. Quindi fai clic su **[!UICONTROL OK]**.
1. Decidi se effettuare una selezione da un intervallo di celle o da un elenco.
1. Se si seleziona da un elenco, fare clic su **[!UICONTROL Add]** per selezionare i punti di controllo da aggiungere al percorso di abbandono. Puoi definire tra 3 e 8 punti di controllo. (Cerca gli elementi disponibili facendo clic su **[!UICONTROL More]**.)

   Per ulteriori informazioni sul perfezionamento del filtro, consulta [Filtra Dimension](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md). 1. Spostare **[!UICONTROL Available Elements]** dalla colonna sinistra a destra selezionandoli e facendo clic sulla freccia arancione.
1. Clic **[!UICONTROL OK]** tre volte, quindi fai clic su **[!UICONTROL Finish]**.

   Il rapporto dovrebbe essere aggiornato ora.
