---
description: I controlli interattivi consentono di modificare segmenti e intervalli di date per una o più richieste direttamente dal foglio di lavoro. Questo offre maggiore flessibilità nell’aggiornamento delle richieste di Report Builder.
title: Controlli interattivi
feature: Report Builder
role: User, Admin
exl-id: 2340ff31-1478-4a54-a4c3-c51e73c39109
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 1%

---

# Controlli interattivi

I controlli interattivi consentono di modificare segmenti e intervalli di date per una o più richieste direttamente dal foglio di lavoro. Questo offre maggiore flessibilità nell’aggiornamento delle richieste di Report Builder.

I controlli interattivi sono stati creati in risposta a un flusso di lavoro comune in cui gli analisti creano cartelle di lavoro e le condividono con l’organizzazione di marketing. I controlli interattivi consentono agli addetti al marketing di modificare e aggiornare le richieste senza dover conoscere a fondo il funzionamento del Report Builder. Per aggiornare una richiesta, il destinatario della cartella di lavoro deve essere un utente del Report Builder. Questi controlli funzionano all&#39;interno di cartelle di lavoro pianificate. Sono attualmente disponibili due tipi di controlli interattivi:

* Intervallo date continuo
* Segmenti

>[!IMPORTANT]
>
>Affinché i controlli interattivi funzionino è necessario che sia installato Report Builder v5.0. >
>* Se Microsoft Excel è in esecuzione ma è in esecuzione una versione di Report Builder precedente o se non è installato alcun Report Builder, è possibile modificare il valore nel controllo interattivo, ma non aggiornerà la richiesta associata né i parametri associati alla richiesta.
>* Se si esegue Excel su Mac, la modifica del valore nel controllo causerà la visualizzazione del seguente messaggio: &quot;Impossibile trovare la macro &#39;Adobe.ReportBuilder.Bridge.FormControlClick.Event&#39;.&quot;
>

>[!WARNING]
>
>Non manomettere il nome del controllo. Per visualizzare il nome, impostare lo stato attivo sul controllo e il nome del controllo viene visualizzato a destra sopra la griglia di Excel, nell&#39;angolo superiore sinistro.

## Implementare il controllo interattivo dell’intervallo di date {#section_39B228F2D2C44985863D31424C953280}

1. Nel passaggio 1 della Creazione guidata richieste selezionare, ad esempio, il report **[!UICONTROL Page]**.
1. Accanto all&#39;elenco a discesa **[!UICONTROL Commonly Used Dates]**, fare clic sull&#39;icona **[!UICONTROL Control Settings]**:

   ![Schermata del passaggio 1 della Creazione guidata richieste che evidenzia l&#39;icona Impostazioni controllo. ](assets/date_range_control.png)

1. Nella finestra di dialogo Impostazioni controllo selezionare tutti gli elementi dell&#39;intervallo di date che si desidera visualizzare nel controllo interattivo. Specificare inoltre la posizione della cella superiore sinistra del controllo.

   ![Schermata che mostra gli elementi dell&#39;intervallo di date selezionati e la posizione della cella superiore sinistra.](assets/control_settings.png)

1. Osserva l’opzione &quot;Aggiorna automaticamente le richieste collegate alla selezione dell’elemento&quot;.

   * Se questa opzione è selezionata, tutte le richieste che utilizzano questo controllo vengono aggiornate.
   * Se non è selezionata, i parametri di richiesta associati vengono aggiornati, ma la richiesta non viene aggiornata.

1. Fai clic su **[!UICONTROL OK]**. Il controllo viene visualizzato nella posizione della cella specificata:

1. Ora puoi modificare l’intervallo di date e la richiesta verrà aggiornata con tale intervallo.

   ![Schermata che mostra l&#39;intervallo di date selezionato.](assets/date_range_control_interactive.png)

1. Puoi anche copiare la richiesta e fare clic con il pulsante destro del mouse per utilizzare una delle due opzioni Incolla richiesta:

   * **[!UICONTROL Paste Request]** > **[!UICONTROL Use Absolute Input Cell]**. Ciò significa che la richiesta copiata punterà allo stesso controllo dell’intervallo di date interattivo della richiesta originale.

   * **[!UICONTROL Paste Request]**> **[!UICONTROL Use Relative input Cell]**. Ciò significa che la richiesta copiata punterà al proprio controllo.

     >[!NOTE]
     >
     >È possibile utilizzare la funzionalità nativa del controllo Taglia/Copia/Incolla di Microsoft Excel. Report Builder riconosce automaticamente i controlli appena aggiunti.

## Implementare il controllo interattivo dei segmenti {#section_5003D3F724644280BF1BCD6E1B0CB784}

L’implementazione del controllo del segmento interattivo è simile all’implementazione del controllo dell’intervallo di date.

1. Nel passaggio 1 della Creazione guidata richieste, accanto all&#39;elenco a discesa **[!UICONTROL Segment]**, selezionare l&#39;icona Impostazioni controllo segmento:

   ![Schermata dell&#39;icona Impostazioni controllo segmento.](assets/segment_interactive_1.png)

1. Nella finestra di dialogo Impostazioni controllo segmento, seleziona i segmenti da includere nel menu a discesa. Specificare inoltre la posizione della cella superiore sinistra del controllo.

   ![Schermata che mostra le impostazioni di controllo del segmento con i segmenti selezionati e la posizione della cella.](assets/segment_drop_down_properties.png)

1. Il nuovo controllo interattivo verrà ora visualizzato nella cartella di lavoro:

   ![Schermata che mostra il nuovo controllo interattivo selezionato.](assets/segment_interactive_3.png)
