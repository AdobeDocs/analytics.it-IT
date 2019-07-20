---
description: Descrive i passaggi necessari per applicare i filtri a un report di abbandono.
seo-description: Descrive i passaggi necessari per applicare i filtri a un report di abbandono.
seo-title: Filtrare un rapporto di abbandono utilizzando la richiesta guidata
solution: Analytics
title: Filtrare un rapporto di abbandono utilizzando la richiesta guidata
topic: Generatore di report
uuid: 269 e 900 e -23 bd -48 d 8-9 bac -69 e 3167 a 9 c 18
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Filtrare un rapporto di abbandono utilizzando la richiesta guidata

Descrive i passaggi necessari per applicare i filtri a un report di abbandono.

Questo esempio mostra il rapporto Abbandono pagina.

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. Seleziona la suite di rapporti giusta.
1. In the tree view on the left, select **[!UICONTROL Paths]** &gt; **[!UICONTROL Page]** &gt; **[!UICONTROL Page Fallout]**.

   ![](assets/page_fallout.png)

1. Configure the appropriate [date ranges](../../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).
1. Fai clic su **[!UICONTROL Next]**.
1. In Step 2 of the Wizard, under **[!UICONTROL Row Labels]**, click the **[!UICONTROL Define Checkpoints]** link. (In un rapporto di abbandono, è sempre necessario definire gli elementi del percorso, a differenza di un rapporto sul percorso, in cui un pattern viene preapplicato).

   ![](assets/define_checkpoints.png)

1. Select the **[!UICONTROL Filter]** option.

1. In the **[!UICONTROL Define Site Section Fallout Checkpoints]** dialog, define checkpoints from a range of cells or from a list. Then click **[!UICONTROL OK]**.
1. Decidere se selezionare o meno da un intervallo di celle o da un elenco.
1. If you select from a list, click **[!UICONTROL Add]** to select checkpoints to add to the fallout path. Potete definire tra i punti di controllo 3 e 8. (Search for available elements by clicking **[!UICONTROL More]**.)

   For more information on refining the filter, see [Filter Dimensions](../../../../analyze/report-builder/layout/c-filter-dimensions/filter-dimensions.md#concept_9C0518E2CF604AADA97DDBB1B4ECAAF8). 1. Move **[!UICONTROL Available Elements]** from the left column to the right by selecting them and clicking the orange arrow.
1. Click **[!UICONTROL OK]** three times, then click **[!UICONTROL Finish]**.

   Il rapporto deve essere aggiornato ora.