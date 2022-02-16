---
description: Descrive i passaggi necessari per applicare filtri a un rapporto di abbandono.
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

Descrive i passaggi necessari per applicare filtri a un rapporto di abbandono.

Questo esempio mostra il rapporto Abbandono pagina .

1. In Adobe Report Builder, fai clic su **[!UICONTROL Create]** per aprire la Creazione guidata richieste.
1. Seleziona la suite di rapporti giusta.
1. Nella vista ad albero a sinistra, seleziona **[!UICONTROL Paths]** > **[!UICONTROL Page]** > **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. Configurare le [intervalli di date](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).
1. Fai clic su **[!UICONTROL Next]**.
1. Nel passaggio 2 della procedura guidata, in **[!UICONTROL Row Labels]**, fai clic su **[!UICONTROL Define Checkpoints]** link. In un rapporto di abbandono, è sempre necessario definire elementi di percorso, a differenza di un rapporto di percorso, in cui un pattern viene preapplicato.

   ![](assets/define_checkpoints.png)

1. Seleziona l&#39;opzione **[!UICONTROL Filter]**.

1. In **[!UICONTROL Define Site Section Fallout Checkpoints]** definire punti di controllo da un intervallo di celle o da un elenco. Quindi fai clic su **[!UICONTROL OK]**.
1. Decidi se scegliere da un intervallo di celle o da un elenco.
1. Se selezioni da un elenco, fai clic su **[!UICONTROL Add]** per selezionare i punti di controllo da aggiungere al percorso di abbandono. Puoi definire tra 3 e 8 punti di controllo. (Cerca gli elementi disponibili facendo clic su **[!UICONTROL More]**.)

   Per ulteriori informazioni sulla raffinazione del filtro, consulta [Dimension filtro](/help/analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md). 1. Spostamento **[!UICONTROL Available Elements]** dalla colonna di sinistra a destra selezionandole e facendo clic sulla freccia arancione.
1. Fai clic su **[!UICONTROL OK]** tre volte, quindi fai clic su **[!UICONTROL Finish]**.

   Il rapporto dovrebbe essere aggiornato ora.
