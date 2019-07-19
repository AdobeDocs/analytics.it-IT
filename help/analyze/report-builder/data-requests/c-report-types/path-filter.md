---
description: Descrive i passaggi necessari per applicare i filtri a un rapporto di percorsi.
seo-description: Descrive i passaggi necessari per applicare i filtri a un rapporto di percorsi.
seo-title: Filtrare un rapporto sul percorso mediante la richiesta guidata
solution: Analytics
title: Filtrare un rapporto sul percorso mediante la richiesta guidata
topic: Generatore di report
uuid: 9 b 22 d 5 b 5-7 ae 8-49 a 2-90 ae -0 c 1075562 bbe
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Filtrare un rapporto sul percorso mediante la richiesta guidata

Descrive i passaggi necessari per applicare i filtri a un rapporto di percorsi.

In questo esempio vengono utilizzati i percorsi sezione del sito.

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. Seleziona la suite di rapporti giusta.
1. In the tree view on the left, select **[!UICONTROL Paths]** &gt; **[!UICONTROL Site Sections]** &gt; **[!UICONTROL Site Section Paths]**.

   ![](assets/site_section_path_1.png)

1. Specificate le date appropriate.
1. Fai clic su **[!UICONTROL Next]**.
1. In Step 2 of the Wizard, under **[!UICONTROL Row Labels]**, click the **[!UICONTROL Top 1-10 (pattern applied)]** link. In un rapporto percorso, per impostazione predefinita viene applicato un pattern.

   ![](assets/site_section_path_2.png)

1. Select the **[!UICONTROL Filter]** option.

   ![](assets/filter_option.png)

1. In the **[!UICONTROL Define 'Site Section Paths' Path Pattern]** dialog, you can specify
   1. il punteggio iniziale del primo report.
   1. il numero di voci da visualizzare in questo rapporto.
1. Click **[!UICONTROL Edit]** to define a path pattern.
1. If you want a custom pattern, drag and drop any **[!UICONTROL Pattern Objects]** from the list on the left into the **[!UICONTROL Pattern Build Canvas]** on the right.

   ![](assets/custom_pattern.png)

1. You can also select a predefined pattern from the **[!UICONTROL Select a Pattern]** drop-down list and modify it. I pattern disponibili sono:

   ![](assets/select_a_pattern.png)

   Alcuni di questi pattern sono specifici per il generatore di report: Pattern elemento successivo di immissione, Pattern elemento precedente percorso, Pattern elemento successivo.
1. Per modificare un pattern predefinito,
   1. Selezionatelo. For example, select the **[!UICONTROL Exited Site Pattern]**: ![](assets/exited_site_pattern.png)

   1. A questo punto, è necessario definire il percorso della sezione del sito che l'utente segue prima dell'uscita. Fai clic su **[!UICONTROL Specific Item(s): 0 selected]**. È possibile definire questo percorso selezionandolo da una serie di celle (se si sta modificando una richiesta esistente) o selezionando un elenco di sezioni.
   1. To select from a range of cells from a previous request, select **[!UICONTROL From range of cells]** and click the cell selector icon. Then pick the cells from the report. ![](assets/choose_site_section_paths.png)

   1. To select from a list of site sections, select **[!UICONTROL From list]** and click **[!UICONTROL Add]**.
   1. Move elements from the **[!UICONTROL Available Elements]** column to the **[!UICONTROL Selected Elements]** column by selecting them and clicking the orange arrow. The click **[!UICONTROL OK]**. ![](assets/move_site_section_elements.png)

   1. To save the pattern you just established, click **[!UICONTROL Save]**.
   1. Click **[!UICONTROL OK]** three times and then click **[!UICONTROL Finish]**. La richiesta di tracciato filtrato viene ora generata.
