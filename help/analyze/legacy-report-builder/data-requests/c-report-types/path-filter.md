---
description: Descrive i passaggi necessari per applicare filtri a un rapporto di percorsi.
title: Filtrare un rapporto di percorso mediante la Creazione guidata richieste
feature: Report Builder
role: User, Admin
exl-id: 085351b3-4d9c-45cf-b2a8-379f05932b26
TQID: https://experienceleague.adobe.com/DQ75Rl9mhTocg9aDfBfTYvwUZxb875iEynjc7BCcy90
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 373
ht-degree: 4%

---

# Filtrare un rapporto di percorso mediante la Creazione guidata richieste

{{legacy-arb}}

Descrive i passaggi necessari per applicare filtri a un rapporto di percorsi.

In questo esempio vengono utilizzati i percorsi delle sezioni del sito.

1. In Adobe Report Builder, fare clic su **[!UICONTROL Create]** per aprire la Creazione guidata richieste.
1. Seleziona la suite di rapporti corretta.
1. Nella visualizzazione struttura a sinistra, selezionare **[!UICONTROL Paths]** > **[!UICONTROL Site Sections]** > **[!UICONTROL Site Section Paths]**.

   ![Schermata che mostra i percorsi della sezione del sito selezionati.](assets/site_section_path_1.png)

1. Specifica le date appropriate.

1. Fai clic su **[!UICONTROL Next]**.

1. Nel passaggio 2 della procedura guidata fare clic sul collegamento **[!UICONTROL Top 1-10 (pattern applied)]** in **[!UICONTROL Row Labels]**. In un report di percorsi, viene applicato un pattern per impostazione predefinita.

   ![Schermata che mostra il modello di percorso predefinito.](assets/site_section_path_2.png)

1. Selezionare l&#39;opzione **[!UICONTROL Filter]**.

   ![Schermata che evidenzia l&#39;opzione Filtro.](assets/filter_option.png)

1. Nella finestra di dialogo **[!UICONTROL Define 'Site Section Paths' Path Pattern]**, puoi specificare
   * Grado iniziale del primo report.
   * Il numero di voci che si desidera visualizzare nel rapporto.
1. Fare clic su **[!UICONTROL Edit]** per definire un pattern di percorso.

1. Se desideri un pattern personalizzato, trascina un elemento **[!UICONTROL Pattern Objects]** dall&#39;elenco a sinistra a **[!UICONTROL Pattern Build Canvas]** a destra.

   ![](assets/custom_pattern.png)

1. È inoltre possibile selezionare un pattern predefinito dall&#39;elenco a discesa **[!UICONTROL Select a Pattern]** e modificarlo. Di seguito sono riportati i pattern disponibili:

   ![](assets/select_a_pattern.png)

   Alcuni di questi modelli sono specifici di Report Builder: Pattern elemento successivo del percorso di ingresso, Pattern elemento precedente del percorso di uscita, Pattern elemento successivo.

## Per modificare un pattern predefinito

Dopo aver selezionato una serie, potete modificare una serie predefinita.

1. Continuando dalla procedura precedente, selezionate la serie. Ad esempio, selezionare **[!UICONTROL Exited Site Pattern]**:

   ![Schermata che evidenzia il modello selezionato.](assets/exited_site_pattern.png)

1. Definisci il percorso della sezione del sito che l’utente segue prima di uscire. Fai clic su **[!UICONTROL Specific Item(s): 0 selected]**. Puoi definire questo percorso selezionandolo da un intervallo di celle se stai modificando una richiesta esistente o selezionandolo da un elenco di sezioni.

1. Per selezionare da un intervallo di celle di una richiesta precedente, selezionare **[!UICONTROL From range of cells]** e fare clic sull&#39;icona del selettore di celle. Selezionare quindi le celle dal report.

   ![Schermata che mostra le opzioni da scegliere da un intervallo di celle o da un elenco.](assets/choose_site_section_paths.png)

1. Per selezionare da un elenco di sezioni del sito, selezionare **[!UICONTROL From list]** e fare clic su **[!UICONTROL Add]**.

1. Spostare gli elementi dalla colonna **[!UICONTROL Available Elements]** alla colonna **[!UICONTROL Selected Elements]** selezionandoli e facendo clic sulla freccia arancione. Fare clic su **[!UICONTROL OK]**.

   ![Schermata che mostra gli elementi disponibili e gli elementi selezionati.](assets/move_site_section_elements.png)

1. Per salvare il modello appena stabilito, fare clic su **[!UICONTROL Save]**.

1. Fare clic tre volte su **[!UICONTROL OK]**, quindi su **[!UICONTROL Finish]** per generare il percorso filtrato.
