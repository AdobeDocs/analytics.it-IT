---
description: Descrive i passaggi necessari per applicare filtri a un rapporto di percorsi.
title: Filtrare un rapporto di percorso mediante la Creazione guidata richieste
feature: Report Builder
role: User, Admin
exl-id: 085351b3-4d9c-45cf-b2a8-379f05932b26
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 6%

---

# Filtrare un rapporto di percorso mediante la Creazione guidata richieste

Descrive i passaggi necessari per applicare filtri a un rapporto di percorsi.

In questo esempio vengono utilizzati i percorsi della sezione del sito.

1. In Adobe Report Builder, fai clic su **[!UICONTROL Create]** per aprire la Creazione guidata richieste.
1. Seleziona la suite di rapporti giusta.
1. Nella vista ad albero a sinistra, seleziona **[!UICONTROL Paths]** > **[!UICONTROL Site Sections]** > **[!UICONTROL Site Section Paths]**.

   ![](assets/site_section_path_1.png)

1. Specifica le date appropriate.
1. Fai clic su **[!UICONTROL Next]**.
1. Nel passaggio 2 della procedura guidata, in **[!UICONTROL Row Labels]**, fai clic su **[!UICONTROL Top 1-10 (pattern applied)]** link. In un rapporto di percorso, un pattern viene applicato per impostazione predefinita.

   ![](assets/site_section_path_2.png)

1. Seleziona l&#39;opzione **[!UICONTROL Filter]**.

   ![](assets/filter_option.png)

1. In **[!UICONTROL Define 'Site Section Paths' Path Pattern]** è possibile specificare
   1. il grado iniziale del primo rapporto.
   1. il numero di voci da visualizzare nel rapporto.
1. Fai clic su **[!UICONTROL Edit]** per definire un pattern di tracciato.
1. Se desideri un pattern personalizzato, trascina e rilascia qualsiasi **[!UICONTROL Pattern Objects]** dall&#39;elenco a sinistra nella **[!UICONTROL Pattern Build Canvas]** a destra.

   ![](assets/custom_pattern.png)

1. È inoltre possibile selezionare un pattern predefinito dal **[!UICONTROL Select a Pattern]** elenco a discesa e modificalo. Di seguito sono riportati i pattern disponibili:

   ![](assets/select_a_pattern.png)

   Alcuni di questi pattern sono specifici per Report Builder: Pattern articolo successivo del percorso di ingresso, Pattern articolo precedente del percorso di uscita, Pattern articolo successivo.
1. Per modificare un pattern predefinito, procedere come segue.
   1. Selezionala. Ad esempio, seleziona la **[!UICONTROL Exited Site Pattern]**: ![](assets/exited_site_pattern.png)

   1. Ora è necessario definire il percorso della sezione del sito che l’utente segue prima di uscire. Fai clic su **[!UICONTROL Specific Item(s): 0 selected]**. Puoi definire questo percorso selezionando da un intervallo di celle (se modifichi una richiesta esistente) o selezionando da un elenco di sezioni.
   1. Per selezionare un intervallo di celle da una richiesta precedente, seleziona **[!UICONTROL From range of cells]** quindi fai clic sull’icona del selettore di celle. Quindi scegli le celle dal rapporto. ![](assets/choose_site_section_paths.png)

   1. Per selezionare da un elenco di sezioni del sito, selezionare **[!UICONTROL From list]** e fai clic su **[!UICONTROL Add]**.
   1. Sposta elementi dal **[!UICONTROL Available Elements]** nella colonna **[!UICONTROL Selected Elements]** selezionandoli e facendo clic sulla freccia arancione. Fai clic su **[!UICONTROL OK]**. ![](assets/move_site_section_elements.png)

   1. Per salvare il pattern appena stabilito, fare clic su **[!UICONTROL Save]**.
   1. Fai clic su **[!UICONTROL OK]** tre volte e quindi fai clic su **[!UICONTROL Finish]**. Viene ora generata la richiesta di percorso filtrato.
