---
description: Descrive i passaggi necessari per applicare filtri a un rapporto di percorsi.
title: Filtrare un rapporto di percorso mediante la Creazione guidata richieste
feature: Report Builder
role: User, Admin
exl-id: 085351b3-4d9c-45cf-b2a8-379f05932b26
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 5%

---

# Filtrare un rapporto di percorso mediante la Creazione guidata richieste

Descrive i passaggi necessari per applicare filtri a un rapporto di percorsi.

In questo esempio vengono utilizzati i percorsi delle sezioni del sito.

1. In Adobe Report Builder, fai clic su **[!UICONTROL Create]** per aprire la Creazione guidata richieste.
1. Seleziona la suite di rapporti corretta.
1. Nella struttura a sinistra, seleziona **[!UICONTROL Paths]** > **[!UICONTROL Site Sections]** > **[!UICONTROL Site Section Paths]**.

   ![Schermata che mostra i percorsi della sezione del sito selezionati.](assets/site_section_path_1.png)

1. Specifica le date appropriate.

1. Fai clic su **[!UICONTROL Next]** (Usa modello di attribuzione non predefinito).

1. Nel passaggio 2 della procedura guidata, sotto **[!UICONTROL Row Labels]**, fare clic su **[!UICONTROL Top 1-10 (pattern applied)]** collegamento. In un report di percorsi, viene applicato un pattern per impostazione predefinita.

   ![Schermata che mostra il pattern del percorso di default.](assets/site_section_path_2.png)

1. Seleziona l&#39;opzione **[!UICONTROL Filter]**.

   ![Screenshot che evidenzia l&#39;opzione Filtro.](assets/filter_option.png)

1. In **[!UICONTROL Define 'Site Section Paths' Path Pattern]** finestra di dialogo, puoi specificare
   * Grado iniziale del primo report.
   * Il numero di voci che si desidera visualizzare nel rapporto.
1. Clic **[!UICONTROL Edit]** per definire una serie di tracciati.

1. Se desideri un pattern personalizzato, trascina e rilascia qualsiasi **[!UICONTROL Pattern Objects]** dall&#39;elenco a sinistra a **[!UICONTROL Pattern Build Canvas]** a destra.

   ![](assets/custom_pattern.png)

1. È inoltre possibile selezionare una serie predefinita dall&#39;elenco **[!UICONTROL Select a Pattern]** e modificarlo. Di seguito sono riportati i pattern disponibili:

   ![](assets/select_a_pattern.png)

   Alcuni di questi modelli sono specifici di Report Builder: Motivo elemento successivo del percorso di immissione, Pattern elemento precedente del percorso di uscita, Pattern elemento successivo.

## Per modificare un pattern predefinito

Dopo aver selezionato una serie, potete modificare una serie predefinita.

1. Continuando dalla procedura precedente, selezionate la serie. Ad esempio, seleziona la **[!UICONTROL Exited Site Pattern]**:

   ![Schermata che evidenzia il pattern selezionato.](assets/exited_site_pattern.png)

1. Definisci il percorso della sezione del sito che l’utente segue prima di uscire. Fai clic su **[!UICONTROL Specific Item(s): 0 selected]**. Puoi definire questo percorso selezionandolo da un intervallo di celle se stai modificando una richiesta esistente o selezionandolo da un elenco di sezioni.

1. Per selezionare da un intervallo di celle di una richiesta precedente, seleziona **[!UICONTROL From range of cells]** e fai clic sull’icona del selettore di celle. Selezionare quindi le celle dal report.

   ![Schermata che mostra le opzioni per scegliere da un intervallo di celle o da un elenco.](assets/choose_site_section_paths.png)

1. Per effettuare una selezione da un elenco di sezioni del sito, selezionare **[!UICONTROL From list]** e fai clic su **[!UICONTROL Add]**.

1. Sposta elementi da **[!UICONTROL Available Elements]** colonna al **[!UICONTROL Selected Elements]** selezionandoli e facendo clic sulla freccia arancione. Il clic **[!UICONTROL OK]**.

   ![Schermata che mostra gli elementi disponibili e gli elementi selezionati.](assets/move_site_section_elements.png)

1. Per salvare il pattern appena stabilito, fate clic su **[!UICONTROL Save]**.

1. Clic **[!UICONTROL OK]** tre volte e quindi fare clic su **[!UICONTROL Finish]** per generare il percorso filtrato.
