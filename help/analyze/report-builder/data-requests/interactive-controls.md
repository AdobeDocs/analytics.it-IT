---
description: I controlli interattivi consentono di modificare segmenti e intervalli di date per una o più richieste direttamente dal foglio di lavoro. Questo offre maggiore flessibilità durante l'aggiornamento delle richieste di generatore di report.
seo-description: I controlli interattivi consentono di modificare segmenti e intervalli di date per una o più richieste direttamente dal foglio di lavoro. Questo offre maggiore flessibilità durante l'aggiornamento delle richieste di generatore di report.
seo-title: Controlli interattivi
solution: Analytics
title: Controlli interattivi
topic: Generatore di report
uuid: 5 f 324 b 61-e 032-455 e -9947-5037 f 013 e 0 fa
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Controlli interattivi

I controlli interattivi consentono di modificare segmenti e intervalli di date per una o più richieste direttamente dal foglio di lavoro. Questo offre maggiore flessibilità durante l'aggiornamento delle richieste di generatore di report.

I controlli interattivi sono stati creati in risposta a un flusso di lavoro comune in cui gli analisti creano i documenti di lavoro e condividono questi libri di lavoro con l'organizzazione marketing. I controlli interattivi offrono agli esperti di mercato la possibilità di modificare e aggiornare le richieste senza dover avere conoscenze approfondite sul funzionamento del generatore di report. Tenete presente che per aggiornare una richiesta, il destinatario del cartella di lavoro deve essere un utente di generatore di report. Tali controlli funzionano all'interno delle cartelle di lavoro pianificate. Sono disponibili due tipi di controlli interattivi:

* Intervallo date continuo
* Segmenti

>[!IMPORTANT]
>
>Affinché i controlli interattivi funzionino è necessario disporre di Generatore di report v 5.0. &gt;
>* Se esegui Microsoft Excel in Windows ma esegui una versione inferiore di generatore di report o se non hai installato un generatore di report: Potete modificare il valore nel controllo interattivo, ma non aggiornare la richiesta associata né aggiornare i parametri associati della richiesta.
>* Se in Excel si esegue Excel, modificando il valore nel controllo viene visualizzato il seguente messaggio: «Impossibile trovare la macrò Adobe. reportbuilder. Bridge. formcontrolclick. Event».
>



>[!IMPORTANT]
>
>Non alterare con il nome del controllo. Per visualizzare il nome, impostate lo stato attivo sul controllo e il nome del controllo compare subito sopra la griglia Excel, nell'angolo in alto a sinistra.

## Implement interactive date range control {#section_39B228F2D2C44985863D31424C953280}

1. In Step 1 of the Request Wizard select, for example, the **[!UICONTROL Page]** report.
1. Next to the **[!UICONTROL Commonly Used Dates]** drop down, click the **[!UICONTROL Control Settings]** icon:

   ![](assets/date_range_control.png)

1. Nella finestra di dialogo Impostazioni controllo, selezionate tutti gli elementi intervallo di date che desiderate visualizzare nel controllo interattivo. Inoltre, specificate la posizione della cella in alto a sinistra del controllo.

   ![](assets/control_settings.png)

1. Osservate l'opzione "Aggiornamento automatico delle richieste collegate durante la selezione degli elementi".

   * Se questa opzione è attivata, tutte le richieste che utilizzano questo controllo vengono aggiornate.
   * Se non sono stati selezionati, i parametri di richiesta associati vengono aggiornati, ma la richiesta non viene aggiornata.

1. Fai clic su **[!UICONTROL OK]**. Il controllo viene visualizzato nella posizione della cella specificata:

   ![](assets/date_range_control_interactive.png)

1. Ora puoi cambiare l'intervallo di date e la richiesta verrà aggiornata con quell'intervallo di date.
1. Potete anche copiare la richiesta e fare clic con il pulsante destro del mouse per utilizzare una delle due opzioni Incolla richiesta:

   * **[!UICONTROL Paste Request]** &gt; **[!UICONTROL Use Absolute Input Cell]**. Ciò significa che la richiesta copiata indicherà lo stesso controllo interattivo degli intervalli di date della richiesta originale.

   * **[!UICONTROL Paste Request]**&gt; **[!UICONTROL Use Relative input Cell]**. Ciò significa che la richiesta copiata indicherà il proprio controllo.

      >[!NOTE]
      >
      >Potete usare la funzionalità di controllo nativo Taglia Excel e Copia/Incolla. Il generatore di report riconosce automaticamente i controlli aggiunti appena.

## Implement interactive segment control {#section_5003D3F724644280BF1BCD6E1B0CB784}

L'implementazione del controllo interattivo dei segmenti è simile all'implementazione del controllo degli intervalli di date.

1. In Step 1 of the Request Wizard, next to the **[!UICONTROL Segment]** drop-down list, select the Segment Control Settings icon:

   ![](assets/segment_interactive_1.png)

1. Nella finestra di dialogo Impostazioni controllo segmenti, seleziona i segmenti da includere nel menu a discesa. Inoltre, specificate la posizione della cella in alto a sinistra del controllo.

   ![](assets/segment_drop_down_properties.png)

1. Il nuovo controllo interattivo viene ora visualizzato nella cartella di lavoro:

   ![](assets/segment_interactive_3.png)

