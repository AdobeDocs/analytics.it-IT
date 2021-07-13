---
description: I controlli interattivi consentono di modificare segmenti e intervalli di date per una o più richieste direttamente dal foglio di lavoro. Questo offre maggiore flessibilità durante l’aggiornamento delle richieste di Report Builder.
title: Controlli interattivi
uuid: 5f324b61-e032-455e-9947-5037f013e0fa
feature: Report Builder
role: User, Admin
exl-id: 2340ff31-1478-4a54-a4c3-c51e73c39109
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---

# Controlli interattivi

I controlli interattivi consentono di modificare segmenti e intervalli di date per una o più richieste direttamente dal foglio di lavoro. Questo offre maggiore flessibilità durante l’aggiornamento delle richieste di Report Builder.

I controlli interattivi sono stati creati in risposta a un flusso di lavoro comune in cui gli analisti creano cartelle di lavoro e condividono tali cartelle di lavoro con l’organizzazione di marketing. I controlli interattivi consentono agli addetti al marketing di modificare e aggiornare le richieste senza dover conoscere in dettaglio il funzionamento di Report Builder. Per aggiornare una richiesta, il destinatario della cartella di lavoro deve essere un utente del generatore di report. Questi controlli funzionano all&#39;interno delle cartelle di lavoro pianificate. Sono attualmente disponibili due tipi di controlli interattivi:

* Intervallo date continuo
* Segmenti

>[!IMPORTANT]
>
>Per il funzionamento dei controlli interattivi è necessario che sia installato Report Builder v5.0. >
>* Se Microsoft Excel è in esecuzione su Windows ma è in esecuzione una versione inferiore di Report Builder o se non è installato Report Builder: Puoi modificare il valore nel controllo interattivo, ma non aggiornerà la richiesta associata, né aggiornerà i parametri associati alla richiesta.
>* Se esegui Excel su Mac, la modifica del valore nel controllo causerà la visualizzazione del seguente messaggio: &quot;Impossibile trovare la macro &#39;Adobe.ReportBuilder.Bridge.FormControlClick.Event&#39;.&quot;

>



>[!IMPORTANT]
>
>Non manomettere il nome del controllo. (Per visualizzare il nome, impostare lo stato attivo sul controllo e il nome del controllo viene visualizzato a destra sopra la griglia Excel, nell&#39;angolo in alto a sinistra.)

## Implementare il controllo interattivo dell’intervallo di date {#section_39B228F2D2C44985863D31424C953280}

1. Nel passaggio 1 della Creazione guidata richieste selezionare, ad esempio, il rapporto **[!UICONTROL Page]**.
1. Accanto al menu a discesa **[!UICONTROL Commonly Used Dates]** , fai clic sull&#39;icona **[!UICONTROL Control Settings]** :

   ![](assets/date_range_control.png)

1. Nella finestra di dialogo Impostazioni controllo, selezionare tutti gli elementi dell’intervallo di date che si desidera visualizzare nel controllo interattivo. Inoltre, specificare la posizione della cella superiore sinistra del controllo.

   ![](assets/control_settings.png)

1. Osserva l’opzione &quot;Aggiorna automaticamente le richieste collegate alla selezione di elementi&quot;.

   * Se questa opzione è selezionata, vengono aggiornate tutte le richieste che utilizzano questo controllo.
   * Se non è selezionato, i parametri di richiesta associati vengono aggiornati, ma la richiesta non viene aggiornata.

1. Fai clic su **[!UICONTROL OK]**. Il controllo viene visualizzato nella posizione della cella specificata:

   ![](assets/date_range_control_interactive.png)

1. Ora puoi modificare l’intervallo di date e la richiesta verrà aggiornata con tale intervallo di date.
1. Puoi anche copiare la richiesta e fare clic con il pulsante destro del mouse per utilizzare una delle due opzioni Incolla richiesta :

   * **[!UICONTROL Paste Request]** > **[!UICONTROL Use Absolute Input Cell]**. Ciò significa che la richiesta copiata punta allo stesso controllo di intervallo di date interattivo della richiesta originale.

   * **[!UICONTROL Paste Request]**> **[!UICONTROL Use Relative input Cell]**. Ciò significa che la richiesta copiata punta al proprio controllo.

      >[!NOTE]
      >
      >È possibile utilizzare la funzionalità di controllo Taglia, Copia e Incolla di Microsoft Excel nativa. Report Builder riconosce automaticamente i nuovi controlli aggiunti.

## Implementare il controllo interattivo dei segmenti {#section_5003D3F724644280BF1BCD6E1B0CB784}

L’implementazione del controllo del segmento interattivo è simile all’implementazione del controllo dell’intervallo di date.

1. Nel passaggio 1 della Creazione guidata richieste, accanto all&#39;elenco a discesa **[!UICONTROL Segment]** , seleziona l&#39;icona Impostazioni controllo segmenti :

   ![](assets/segment_interactive_1.png)

1. Nella finestra di dialogo Impostazioni controllo segmenti, seleziona i segmenti che desideri includere nel menu a discesa. Inoltre, specificare la posizione della cella superiore sinistra del controllo.

   ![](assets/segment_drop_down_properties.png)

1. Il nuovo controllo interattivo verrà ora visualizzato nella cartella di lavoro:

   ![](assets/segment_interactive_3.png)
