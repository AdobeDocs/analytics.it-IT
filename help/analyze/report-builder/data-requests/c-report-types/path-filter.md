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

In questo esempio vengono utilizzati i percorsi delle sezioni del sito.

1. In Adobe Report Builder, fai clic su **[!UICONTROL Create]** per aprire la Creazione guidata richieste.
1. Seleziona la suite di rapporti corretta.
1. Nella struttura a sinistra, seleziona **[!UICONTROL Paths]** > **[!UICONTROL Site Sections]** > **[!UICONTROL Site Section Paths]**.

   ![](assets/site_section_path_1.png)

1. Specifica le date appropriate.
1. Fai clic su **[!UICONTROL Next]** (Usa modello di attribuzione non predefinito).
1. Nel passaggio 2 della procedura guidata, sotto **[!UICONTROL Row Labels]**, fare clic su **[!UICONTROL Top 1-10 (pattern applied)]** collegamento. In un report di percorsi, viene applicato un pattern per impostazione predefinita.

   ![](assets/site_section_path_2.png)

1. Seleziona l&#39;opzione **[!UICONTROL Filter]**.

   ![](assets/filter_option.png)

1. In **[!UICONTROL Define 'Site Section Paths' Path Pattern]** finestra di dialogo, puoi specificare
   1. la classificazione iniziale del primo rapporto.
   1. il numero di voci che si desidera visualizzare nel rapporto.
1. Clic **[!UICONTROL Edit]** per definire una serie di tracciati.
1. Se desideri un pattern personalizzato, trascina e rilascia qualsiasi **[!UICONTROL Pattern Objects]** dall&#39;elenco a sinistra a **[!UICONTROL Pattern Build Canvas]** a destra.

   ![](assets/custom_pattern.png)

1. È inoltre possibile selezionare una serie predefinita dall&#39;elenco **[!UICONTROL Select a Pattern]** e modificarlo. Di seguito sono riportati i pattern disponibili:

   ![](assets/select_a_pattern.png)

   Alcuni di questi modelli sono specifici di Report Builder: Motivo elemento successivo del percorso di immissione, Pattern elemento precedente del percorso di uscita, Pattern elemento successivo.
1. Per modificare un pattern predefinito:
   1. Selezionala. Ad esempio, seleziona la **[!UICONTROL Exited Site Pattern]**: ![](assets/exited_site_pattern.png)

   1. Ora è necessario definire il percorso della sezione del sito che l’utente segue prima di uscire. Fai clic su **[!UICONTROL Specific Item(s): 0 selected]**. Puoi definire questo percorso selezionandolo da un intervallo di celle (se stai modificando una richiesta esistente) o selezionandolo da un elenco di sezioni.
   1. Per selezionare da un intervallo di celle di una richiesta precedente, seleziona **[!UICONTROL From range of cells]** e fai clic sull’icona del selettore di celle. Selezionare quindi le celle dal report. ![](assets/choose_site_section_paths.png)

   1. Per effettuare una selezione da un elenco di sezioni del sito, selezionare **[!UICONTROL From list]** e fai clic su **[!UICONTROL Add]**.
   1. Sposta elementi da **[!UICONTROL Available Elements]** colonna al **[!UICONTROL Selected Elements]** selezionandoli e facendo clic sulla freccia arancione. Il clic **[!UICONTROL OK]**. ![](assets/move_site_section_elements.png)

   1. Per salvare il pattern appena stabilito, fate clic su **[!UICONTROL Save]**.
   1. Clic **[!UICONTROL OK]** tre volte e quindi fare clic su **[!UICONTROL Finish]**. Ora viene generata la richiesta di percorso filtrato.
