---
description: I controlli interattivi consentono di modificare segmenti e intervalli di date per una o più richieste direttamente dal foglio di lavoro. Questo offre maggiore flessibilità quando si aggiornano le richieste del generatore di report.
title: Controlli interattivi
topic: Report builder
uuid: 5f324b61-e032-455e-9947-5037f013e0fa
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Controlli interattivi

I controlli interattivi consentono di modificare segmenti e intervalli di date per una o più richieste direttamente dal foglio di lavoro. Questo offre maggiore flessibilità quando si aggiornano le richieste del generatore di report.

I controlli interattivi sono stati creati in risposta a un flusso di lavoro comune in cui gli analisti creano cartelle di lavoro e condividono tali cartelle di lavoro con l&#39;organizzazione di marketing. I controlli interattivi consentono agli esperti di marketing di modificare e aggiornare le richieste senza dover conoscere in dettaglio il funzionamento del generatore di report. Per aggiornare una richiesta, il destinatario della cartella di lavoro deve essere un utente generatore di report. Questi controlli funzionano all&#39;interno di cartelle di lavoro pianificate. Sono attualmente disponibili due tipi di controlli interattivi:

* Intervallo date di rolling
* Segmenti

>[!IMPORTANT]
>
>Per il funzionamento dei controlli interattivi è necessario disporre di Generatore di report v5.0. >
>* Se Microsoft Excel è in esecuzione su Windows ma è in esecuzione una versione inferiore del generatore di report o se non è installato il generatore di report: È possibile modificare il valore nel controllo interattivo, ma non aggiornerà la richiesta associata né aggiornerà i parametri associati della richiesta.
>* Se si esegue Excel in Mac, modificando il valore nel controllo verrà visualizzato il seguente messaggio: &quot;Impossibile trovare la macro &#39;Adobe.ReportBuilder.Bridge.FormControlClick.Event&#39;.&quot;
>



>[!IMPORTANT]
>
>Non alterare il nome del controllo. Per visualizzare il nome, impostare lo stato attivo sul controllo e il nome del controllo viene visualizzato a destra sopra la griglia di Excel, nell&#39;angolo superiore sinistro.

## Implementazione del controllo interattivo dell&#39;intervallo di date {#section_39B228F2D2C44985863D31424C953280}

1. Nel passaggio 1 della Richiesta guidata selezionare, ad esempio, il **[!UICONTROL Page]** rapporto.
1. Accanto all&#39; **[!UICONTROL Commonly Used Dates]** elenco a discesa, fai clic sull&#39;icona **[!UICONTROL Control Settings]** :

   ![](assets/date_range_control.png)

1. Nella finestra di dialogo Impostazioni controllo, selezionare tutti gli elementi dell&#39;intervallo di date che si desidera visualizzare nel controllo interattivo. Inoltre, specificare la posizione della cella superiore sinistra del controllo.

   ![](assets/control_settings.png)

1. Notate l&#39;opzione &quot;Aggiorna automaticamente le richieste collegate alla selezione degli elementi&quot;.

   * Se questa opzione è selezionata, tutte le richieste che utilizzano questo controllo vengono aggiornate.
   * Se non è selezionata, i parametri di richiesta associati vengono aggiornati, ma la richiesta non viene aggiornata.

1. Fai clic su **[!UICONTROL OK]**. Il controllo viene visualizzato nella posizione cella specificata:

   ![](assets/date_range_control_interactive.png)

1. Ora puoi modificare l&#39;intervallo di date e la richiesta verrà aggiornata con tale intervallo.
1. Potete anche copiare la richiesta e fare clic con il pulsante destro del mouse per utilizzare una delle due opzioni Incolla richiesta:

   * **[!UICONTROL Paste Request]** > **[!UICONTROL Use Absolute Input Cell]**. Ciò significa che la richiesta copiata indicherà lo stesso controllo intervallo di date interattivo della richiesta originale.

   * **[!UICONTROL Paste Request]**> **[!UICONTROL Use Relative input Cell]**. Ciò significa che la richiesta copiata indicherà il proprio controllo.

      >[!NOTE]
      >
      >È possibile utilizzare la funzionalità di controllo Taglia, Copia e Incolla di Microsoft Excel nativa. Il generatore di report riconosce automaticamente i nuovi controlli aggiunti.

## Implementare il controllo interattivo dei segmenti {#section_5003D3F724644280BF1BCD6E1B0CB784}

L’implementazione del controllo del segmento interattivo è simile all’implementazione del controllo dell’intervallo di date.

1. Nel passaggio 1 della Richiesta guidata, accanto all&#39;elenco a **[!UICONTROL Segment]** discesa, selezionate l&#39;icona Impostazioni controllo segmenti:

   ![](assets/segment_interactive_1.png)

1. Nella finestra di dialogo Impostazioni controllo segmenti, selezionate i segmenti da includere nel menu a discesa. Inoltre, specificare la posizione della cella superiore sinistra del controllo.

   ![](assets/segment_drop_down_properties.png)

1. Il nuovo controllo interattivo verrà ora visualizzato nella cartella di lavoro:

   ![](assets/segment_interactive_3.png)

