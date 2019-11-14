---
description: Descrive i passaggi necessari per applicare filtri a un report di percorsi.
solution: Analytics
title: Filtrare un rapporto di percorso mediante la Creazione guidata richieste
topic: Report builder
uuid: 9b22d5b5-7ae8-49a2-90ae-0c1075562bbe
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Filtrare un rapporto di percorso mediante la Creazione guidata richieste

Descrive i passaggi necessari per applicare filtri a un report di percorsi.

In questo esempio vengono utilizzati i percorsi di sezione del sito.

1. In Generatore di report Adobe, fate clic **[!UICONTROL Create]** per aprire la Richiesta guidata.
1. Seleziona la suite di rapporti giusta.
1. Nella vista ad albero a sinistra, selezionate **[!UICONTROL Paths]** &gt; **[!UICONTROL Site Sections]** &gt; **[!UICONTROL Site Section Paths]**.

   ![](assets/site_section_path_1.png)

1. Specificate le date appropriate.
1. Fai clic su **[!UICONTROL Next]**.
1. Nel Passaggio 2 della procedura guidata, in **[!UICONTROL Row Labels]**, fare clic sul **[!UICONTROL Top 1-10 (pattern applied)]** collegamento. In un rapporto percorso, per impostazione predefinita viene applicato un pattern.

   ![](assets/site_section_path_2.png)

1. Seleziona l'opzione **[!UICONTROL Filter]**.

   ![](assets/filter_option.png)

1. Nella **[!UICONTROL Define 'Site Section Paths' Path Pattern]** finestra di dialogo potete specificare
   1. il livello iniziale del primo rapporto.
   1. il numero di voci da visualizzare in questo rapporto.
1. Fare clic **[!UICONTROL Edit]** per definire un pattern di percorso.
1. Se si desidera un pattern personalizzato, trascinare uno qualsiasi **[!UICONTROL Pattern Objects]** dall'elenco a sinistra verso **[!UICONTROL Pattern Build Canvas]** destra.

   ![](assets/custom_pattern.png)

1. È inoltre possibile selezionare un pattern predefinito dall'elenco a **[!UICONTROL Select a Pattern]** discesa e modificarlo. Di seguito sono riportati i pattern disponibili:

   ![](assets/select_a_pattern.png)

   Alcuni di questi pattern sono specifici per il generatore di report: Pattern elemento successivo del percorso di immissione, Pattern elemento precedente del percorso di uscita, Pattern elemento successivo.
1. Per modificare un pattern predefinito,
   1. Selezionatela. Ad esempio, selezionare **[!UICONTROL Exited Site Pattern]**: ![](assets/exited_site_pattern.png)

   1. A questo punto è necessario definire il percorso della sezione del sito che l'utente segue prima di uscire. Fai clic su **[!UICONTROL Specific Item(s): 0 selected]**. È possibile definire questo percorso selezionando da un intervallo di celle (se si sta modificando una richiesta esistente) oppure selezionando da un elenco di sezioni.
   1. Per selezionare da un intervallo di celle da una richiesta precedente, selezionare **[!UICONTROL From range of cells]** e fare clic sull'icona del selettore di celle. Quindi scegliete le celle dal rapporto. ![](assets/choose_site_section_paths.png)

   1. Per selezionare da un elenco di sezioni del sito, selezionare **[!UICONTROL From list]** e fare clic su **[!UICONTROL Add]**.
   1. Spostate gli elementi dalla **[!UICONTROL Available Elements]** colonna alla **[!UICONTROL Selected Elements]** colonna selezionandoli e facendo clic sulla freccia arancione. Il clic **[!UICONTROL OK]**. ![](assets/move_site_section_elements.png)

   1. Per salvare il pattern appena stabilito, fare clic su **[!UICONTROL Save]**.
   1. Fare clic **[!UICONTROL OK]** tre volte, quindi fare clic **[!UICONTROL Finish]**. Ora viene generata la richiesta del percorso filtrato.
