---
title: Creare E Modificare I Consolidamenti Di Classificazione
description: Spiega come creare, convalidare, eseguire, approvare e annullare i consolidamenti delle classificazioni.
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: cabddc619e0d2ddaba6b232eb4d72c60301f76bb
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 3%

---

# Creare e modificare i consolidamenti delle classificazioni

Un consolidamento dei set di classificazione consente di prendere classificazioni da più set di classificazione e combinarle in un unico set. Utilizzare questa interfaccia per creare un consolidamento del set di classificazione dall&#39;inizio alla fine. Questa interfaccia è particolarmente utile per le organizzazioni che passano dalle classificazioni legacy ai set di classificazione. Le organizzazioni che utilizzano già set di classificazione non devono utilizzare questo flusso di lavoro di consolidamento.

## Creare un consolidamento {#create-a-consolidation}


>[!CONTEXTUALHELP]
>id="classificationsets_consolidation_setpriority"
>title="Priorità del set di classificazione"
>abstract="Il ![Key](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Key_18_N.svg) *set di classificazione* è il set di classificazione di base e definisce lo schema generale e ha la precedenza in tutti i conflitti di unione. Gli altri set di classificazione vengono applicati in ordine crescente."


Per creare un consolidamento delle classificazioni, nell’interfaccia principale di Adobe Analytics:

1. Seleziona **[!UICONTROL Classification sets]** dal menu **[!UICONTROL Components]**.
1. Nel gestore **[!UICONTROL Classification Sets]**, selezionare la scheda **[!UICONTROL Consolidations]**.
1. Nel gestore **[!UICONTROL Classification Sets - Consolidations]**, selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]**.
1. Nella finestra di dialogo **[!UICONTROL New Consolidation]**

   ![Set di classificazione - Nuovo consolidamento](assets/classifications-sets-consolidations-new.png)
   1. Immetti **[!UICONTROL Name]**. Ad esempio: `Consolidation Example`.
   1. Immetti **[!UICONTROL Description (optional)]**. Ad esempio: `Example classification set`.
   1. Immettere uno o più indirizzi di posta elettronica (separati da virgola) in **[!UICONTROL Notify of issues]**. Gli utenti ricevono notifiche e-mail in caso di problemi.
   1. Selezionare un set di classificazione dal menu a discesa **[!UICONTROL Classification Set To Match]**.

      L&#39;elenco a sinistra **[!UICONTROL Source Classification Set]** contiene set di classificazione simili a quello selezionato e disponibili per il consolidamento. L&#39;elenco corretto viene compilato automaticamente con il set di classificazione ![Chiave](/help/assets/icons/Key.svg) selezionato. Il set di base ha definito lo schema generale e ha sempre la precedenza in tutti i conflitti di unione.

   1. Seleziona i set di classificazione da consolidare dall&#39;elenco a sinistra e rilascia i set selezionati nell&#39;elenco a destra sotto la ![Chiave](/help/assets/icons/Key.svg) base **[!UICONTROL _set di classificazione_]** selezionata.

      I set di classificazione aggiuntivi vengono consolidati in ordine crescente quando si esegue il consolidamento. Se una chiave esiste in più set aggiuntivi, viene considerato il valore della chiave dal set di classificazione di classificazione di livello superiore. Se esiste una chiave sia nel set di base ![Chiave](/help/assets/icons/Key.svg) che in qualsiasi altro set, viene utilizzato il valore del set di base.

      Per gestire i valori utilizzati per le chiavi, sposta i singoli set di classificazione selezionati nell’elenco tramite trascinamento. È inoltre possibile sostituire ![Chiave](/help/assets/icons/Key.svg) **[!UICONTROL _set di classificazione_]** con un set di classificazione selezionato tramite trascinamento della selezione.

   1. Selezionare **[!UICONTROL Save]** per salvare il consolidamento della classificazione. Seleziona **[!UICONTROL Cancel]** per annullare.

Una volta salvato, il consolidamento delle classificazioni viene convalidato automaticamente per il consolidamento. Questa convalida garantisce che ogni singolo set di classificazione sia valido per questo consolidamento. Dopo l&#39;operazione, la voce nell&#39;elenco di consolidamento delle classificazioni mostra lo stato **[!UICONTROL Validated]**.

Dopo aver creato un consolidamento, i passaggi successivi sono i seguenti:

* [Riconvalida](#re-validate) il consolidamento della classificazione dopo aver apportato modifiche alla configurazione iniziale.
* [Esegui](#run) il consolidamento delle classificazioni.
* [Approva](#approve) il consolidamento delle classificazioni.



<!--
         
  

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]** > **[!UICONTROL Add]**

The following fields are available when creating a consolidation:

* **[!UICONTROL Name]**: The name of the consolidation.
* **[!UICONTROL Notify of issues]**: A comma-delimited list of email addresses that are notified of issues with this consolidation.
* **[!UICONTROL Dataset to match]**: A drop-down list of all classification sets.

Once you select a classification set, a table with two columns appears:

* The right column contains all classification sets that you want to consolidate. It starts with the classification set selected using the above drop-down list.
* The left column contains all classification sets eligible to be merged with the originally selected dataset. **Schemas must exactly match to be eligible for consolidation**. If schemas do not match the selected classification set, they do not appear in this left column.

Drag the desired classification sets from the available column on the left to the consolidation column on the right. Once the consolidation is given a name and two or more classification sets are in the right column, click **[!UICONTROL Save & Continue]**.

-->

## Modificare un consolidamento

Per modificare il consolidamento di una classificazione, nell’interfaccia principale di Adobe Analytics:

1. Seleziona **[!UICONTROL Classification sets]** dal menu **[!UICONTROL Components]**.
1. Nel gestore **[!UICONTROL Classification Sets]**, selezionare la scheda **[!UICONTROL Consolidations]**.
1. Nel gestore **[!UICONTROL Classification Sets Consolidations]**:
   1. Seleziona il nome del consolidamento della classificazione. Viene visualizzata la finestra di dialogo **[!UICONTROL Consolidation: _nome consolidamento classificazione_]**. L&#39;aspetto e le azioni disponibili dipendono dallo stato corrente del consolidamento e dalla possibilità di modificare il consolidamento della classificazione.

      | Azioni disponibili | Descrizione |
      |---|---|
      | ![Annulla](/help/assets/icons/Cancel.svg) **[!UICONTROL Cancel]** | [Annulla il consolidamento](#cancel). |
      | ![Segno di spunta](/help/assets/icons/Checkmark.svg) **[!UICONTROL Re-Validate]** | [Riconvalida il consolidamento](#re-validate). |
      | ![Riproduci](/help/assets/icons/Play.svg) **[!UICONTROL Run]** | [Esegui il consolidamento](#run). |
      | ![AlzaTendina](/help/assets/icons/ThumbUp.svg) **[!UICONTROL Approve]** | [Approva il consolidamento](#approve). |



### Riconvalida

È possibile convalidare nuovamente un consolidamento della classificazione nella finestra di dialogo Consolidamento: consolidamento della classificazione. Un ![avviso](/help/assets/icons/Alert.svg) potrebbe fornire informazioni aggiuntive sui problemi relativi al consolidamento che richiedono la riconfigurazione del consolidamento.

![Set Di Classificazione - Nuova Convalida Del Consolidamento](assets/classifications-sets-consolidations-validated.png)

Per convalidare nuovamente il consolidamento della classificazione:

1. Riconfigurare il consolidamento utilizzando la stessa interfaccia di trascinamento utilizzata per creare il consolidamento.
1. Seleziona ![Segno di spunta](/help/assets/icons/Checkmark.svg) **[!UICONTROL Re-Validate]**. La convalida garantisce che ogni singolo set di classificazione sia valido per questo consolidamento. In caso di esito positivo, viene visualizzato un messaggio popup: ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Successfully submitted consolidation for validation!]**
1. Selezionare ![CrossSize400](/help/assets/icons/CrossSize400.svg) per chiudere la finestra di dialogo. In alternativa, selezionare ![Riproduci](/help/assets/icons/Play.svg) **[!UICONTROL Run]** per eseguire il consolidamento oppure ![Annulla](/help/assets/icons/Cancel.svg) **[!UICONTROL Cancel]** per annullare la classificazione.



<!--
Once you have created a consolidation, a list of source datasets appears on the right. The **[!UICONTROL Validate]** button makes sure that each individual classification set is valid for this consolidation. You can reorder the classification steps here to determine priority in cases of mismatched classification values. **The highest classification set in the list overwrites any mismatched values in other classification sets.**

-->

### Eseguire

Una volta convalidato correttamente un consolidamento di classificazione, puoi eseguirlo.

Per eseguire un consolidamento delle classificazioni:

1. Seleziona ![Riproduci](/help/assets/icons/Play.svg) **[!UICONTROL Run]**. Un messaggio di avviso popup visualizza ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Successfully submitted consolidation for processing!]**
1. Selezionare ![CrossSize400](/help/assets/icons/CrossSize400.svg) per chiudere la finestra di dialogo.


### Approvazione {#approve}


>[!CONTEXTUALHELP]
>id="classificationsets_consolidations_mismatch"
>title="Mancata corrispondenza"
>abstract="La percentuale di mancate corrispondenze chiave quando il valore nel set di classificazione consolidato non corrisponde al set di classificazione di origine."

>[!CONTEXTUALHELP]
>id="classificationsets_consolidations_absent"
>title="Assente"
>abstract="La percentuale di chiavi nel set di classificazione consolidato, ma non nel set di classificazione di origine."

Una volta eseguito correttamente un consolidamento della classificazione, lo stato del consolidamento è ![StatusOrange](/help/assets/icons/StatusOrange.svg) **[!UICONTROL Waiting for Approval]**. L&#39;approvazione di un consolidamento delle classificazioni sostituisce i singoli set di classificazione con il set di classificazione consolidato e i singoli set di classificazione vengono rimossi.

![Set di classificazione - Consolidamento in attesa di approvazione](assets/classifications-sets-consolidations-waitingforapproval.png)

Per approvare un consolidamento del set di classificazione:

1. Utilizzare **[!UICONTROL Similarity Reports]** per rivedere il consolidamento. Questo rapporto mostra una tabella con le seguenti colonne:

   * **[!UICONTROL Classification Set Name]**: nome del set di classificazione.
   * **[!UICONTROL Mismatch]**: percentuale di righe in cui i valori chiave non corrispondono al set di classificazione di origine. Se la percentuale di mancata corrispondenza è elevata, la mancata corrispondenza può indicare che i dati di classificazione sono troppo diversi. Controlla e assicurati che i set di classificazione selezionati abbiano dati di classificazione simili.
   * **[!UICONTROL Absent]**: percentuale di righe in cui i valori chiave si trovano nel set di classificazione ![Chiave](/help/assets/icons/Key.svg) ma non nel set di classificazione di origine. Tutte le righe assenti vengono aggiunte al set di classificazione consolidato.

1. Se il consolidamento delle classificazioni è pronto per l&#39;approvazione, selezionare ![Segno di spunta](/help/assets/icons/Checkmark.svg) **[!UICONTROL Approve]**. Una finestra di dialogo **[!UICONTROL Approve Consolidation?]** richiede conferma. Selezionare **[!UICONTROL Approve]** per approvare il consolidamento. Seleziona **[!UICONTROL Cancel]** per annullare.

Una volta approvato, viene creato il set di classificazione consolidato. Stato impostato su **[!UICONTROL Complete]**.


### Annulla

Puoi annullare un consolidamento delle classificazioni prima dell’approvazione.

Per annullare un consolidamento delle classificazioni:

1. Seleziona **[!UICONTROL Cancel]**.

   Una volta annullato il consolidamento, non è possibile riprendere il consolidamento.
1. Selezionare **[!UICONTROL Cancel Consolidation]** per annullare il consolidamento. Selezionare **[!UICONTROL Go Back]** per ripristinare l&#39;annullamento.
