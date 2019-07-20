---
description: Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.
seo-description: Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.
seo-title: Pianificazione e distribuzione dei report
solution: Analytics
subtopic: Pianificazione
title: Pianificazione e distribuzione dei report
topic: Reports & Analytics
uuid: 1230 b 0 f 3-e 026-4 b 83-b 231-14 d 6 f 75 a 3836
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Pianificazione e distribuzione dei report

Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.

## Report schedule and distribution {#concept_4EA333DFC7FD4E9CA086385A3DA10BE9}

Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.

Quando pianifichi la consegna di un report in un'applicazione di Adobe Analytics puoi utilizzare gli strumenti Scheduling (Pianificazione) e Distribution (Distribuzione) per visualizzare i file automaticamente inviati e modificati o per terminare le consegne.

A causa di differenze nei meccanismi di elaborazione e nelle piattaforme, i diversi tipi di rapporti scaricabili e pianificati disponibili in Adobe Analytics presentano limitazioni diverse rispetto al numero massimo di righe che possono essere elaborate in una singola richiesta. I limiti di ciascuna:

* Word, CSV, Excel, HTML e PDF: Lo stesso numero di righe visibili nel report. Per impostazione predefinita, questo limite è di 50 righe ma può aumentare fino a 200. I rapporti di analisi hanno un limite rigido di 50 righe.
* Estratti di dati: 50,000 righe
* Data Warehouse: Illimitato

Tali limitazioni sono relative a singoli rapporti pianificati e scaricati; Le dashboard sono limitate alla quantità di spazio disponibile all'interno di un minirapporto.

## Send a report {#task_27642CD33D484FD0BF59EBD159EEF52C}

Procedura che descrive come scaricare ed e-mail in diversi formati e pianificare un rapporto per la consegna.

<!-- 

t_send_report.xml

 -->

1. Run a report, then click **[!UICONTROL More]** &gt; **[!UICONTROL Send]**.
1. Specificate le opzioni di consegna:

   | Opzione | Descrizione |
   |--- |--- |
   | Formato | Selezionare PDF o HTML. |
   | Invia a | Fornite un indirizzo e-mail per ricevere il rapporto. |
   | Oggetto | Oggetto dell'e-mail. |
   | Pianificazione | Seleziona per inviare il rapporto immediatamente o a un intervallo diverso. |

1. Click **[!UICONTROL Advanced Delivery Options]** to specify a delivery schedule.

   <table id="choicetable_2934E54FEE6E4D33B07EAC21F6DF628E"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Opzione </th> 
   <th class="chdeschd"> Descrizione </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Nome file rapporto</strong></td> 
   <td class="chdesc stentry"> <p>Specifica il nome del rapporto. The default format is <code> &lt;report name&gt; for &lt;suite&gt; - &lt;report date range&gt; </code>. </p> <p>To specify a custom name, select <span class="uicontrol"> Custom </span>. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Formato rapporto</strong></td> 
   <td class="chdesc stentry"> <p>Consente di specificare i formati PDF, CSV, Excel, HTML, Word o Mobile per la distribuzione. Se selezionate CSV, potete anche specificare la codifica per CSV: </p> <p> 
      <ul id="ul_4A2EB8D9512246589994052CF482BFD7"> 
      <li id="li_A4FC4D795A9D4F92AAB187ACDFBA180D"> <p> <span class="uicontrol"> Shift-JIS </span>: Codifica caratteri giapponese. </p> </li> 
      <li id="li_405C7EC97F994D649A50F84466FADA3D"> <p> <span class="uicontrol"> EUC-JP </span>: Codice Unix esteso, principalmente per giapponese, coreano e cinese semplificato. </p> </li> 
      </ul> </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Sommario</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Numero di righe nella tabella </span>: Specifica il numero di righe da visualizzare nella tabella del rapporto che stai inviando. </p> <p> <span class="uicontrol"> Lingua per intestazione e piè </span>di pagina: Specifica la lingua dell'intestazione e del piè di pagina. </p> <p> <span class="uicontrol"> Commenti </span>: Specifica il testo che viene visualizzato all'inizio del rapporto. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Invia file firma digitale</strong></td> 
   <td class="chdesc stentry"> <p>Quando si richiede un rapporto, ad esempio un rapporto contrassegnato o un data warehouse, è possibile richiedere una firma dati. La firma digitale di Adobe non limita chi ha accesso ai dati, ma lo scopo del file di firma digitale (. sig) è quello di verificare la validità del file di report consegnato. Utilizzando la firma digitale, i destinatari del report possono verificare che il file sia passato da Adobe e non sia stato alterato. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Destinazione rapporto</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> E-mail </span>: Consente di configurare le impostazioni dell'indirizzo e-mail, l'oggetto e le note. </p> <p> <span class="uicontrol"> FTP </span>: Consente di configurare le impostazioni FTP, inclusi Ospitante, Porta, Directory, Nome utente e Password. </p> </td> 
   </tr> 
   </table>

1. Fai clic su **[!UICONTROL Scheduling Options]**.

   <table id="choicetable_589A39087F4C497D8913364FFF0125B7"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Opzione </th> 
   <th class="chdeschd"> Descrizione </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Invia rapporto ora</strong></td> 
   <td class="chdesc stentry"> <p>Invia il rapporto immediatamente. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Pianifica per successivo</strong></td> 
   <td class="chdesc stentry"> <p>Visualizza le opzioni per specificare un intervallo di tempo e le opzioni di consegna. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Intervallo di tempo rapporto</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Problema corretto </span>: Impedisce l'avanzamento della data durante la trasmissione del tempo. </p> <p> <span class="uicontrol"> Scorrimento </span>: Consente l'avanzamento della data durante la trasmissione del tempo. Considerazioni: </p> <p> 
      <ul id="ul_5CDCCBEFEB364800A428614183A0E6A1"> 
      <li id="li_37B8F32A9E3B4979B5239A58F0C5A71C"> <p>Se selezioni la rotazione per le date iniziale e finale e selezioni un rapporto giornaliero per il giorno precedente, riceverai un messaggio e-mail ogni giorno con un rapporto per il giorno precedente. </p> </li> 
      <li id="li_83FFD2400C6A453783CDD9BB3B9BA3F9"> <p>Se selezionate fisso per il giorno iniziale e continua per il giorno finale, riceverete un rapporto per il giorno precedente. Il secondo giorno in cui riceverete un rapporto per i due giorni precedenti e il terzo giorno riceverete un rapporto per i tre giorni precedenti e così via. </p> </li> 
      <li id="li_28F8552D699841BC942058247D39DBB9"> <p>Se selezionate fisso per le date iniziale e finale, ogni giorno che ricevete un rapporto identico per i giorni specificati. </p> </li> 
      <li id="li_A594A6E2A4044ED6AC0A80F88EB203B3"> <p>Non è possibile selezionare un avvio continuo e una data di fine fissa. </p> </li> 
      </ul> </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Frequenza di consegna</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Orario </span>: Invia l'e-mail ogni ora, ogni ora, o qualsiasi altro intervallo di ore. </p> <p> <span class="uicontrol"> Giornaliero </span>: Invia l'e-mail ogni giorno, ogni giorno, ogni terzo giorno o un altro intervallo di giorni. Puoi anche inviarlo ogni giorno feriale. </p> <p> <span class="uicontrol"> Settimanale </span>: Invia l'e-mail ogni settimana, l'altra settimana, ogni terza settimana o qualsiasi altro intervallo di settimane. Potete anche specificare il giorno della settimana in cui viene inviato. </p> <p> <span class="uicontrol"> Mensile </span>: Specifica l'intervallo in numero di mesi, inoltre è possibile selezionare il giorno del mese in cui viene inviato, oppure il giorno della settimana in una settimana specifica del mese. </p> <p> <span class="uicontrol"> Annuale </span>: Specifica il giorno dell'anno su cui viene inviato il rapporto, oppure puoi inviarlo in un giorno specifico della settimana in qualsiasi settimana dell'anno. </p> <p> <span class="uicontrol"> Ora del giorno </span>: Si applica al fuso orario associato alla suite di rapporti selezionata. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Opzioni di consegna finale</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Non terminare </span>: Non specifica alcuna fine. </p> <p> <span class="uicontrol"> Termina dopo &lt; valore &gt; occorrenze </span>: Specifica il numero di occorrenze prima della fine della consegna. </p> <p> <span class="uicontrol"> Termina su </span>: Consente di specificare una data specifica. </p> <p>Se si desidera elaborare i dati nella stessa data dei dati del rapporto, il rapporto contiene solo i dati che sono stati immessi nel database al momento dell'invio del rapporto. Poiché l'elaborazione completa per un giorno può richiedere fino a 24 ore, i dati completi potrebbero non essere disponibili al momento dell'invio del report. Per i dati completi, impostare sempre il tempo di elaborazione di 24 ore dopo la fine del periodo di reporting. </p> </td> 
   </tr> 
   </table>

## Print a report {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Procedura che descrive come stampare un rapporto.

<!-- 

t_reports_print.xml

 -->

1. Esegui un report.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Print]**.  ![](assets/print.png)

## Download a report using basic options {#task_43660107A1C9485D92981CD75B562577}

Scarica informazioni dettagliate su un rapporto specifico nei formati di esportazione PDF, CSV, Excel o Raw.

<!-- 

t_download-report.xml

 -->

1. In  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** , select a report to view.
1. Fai clic su **[!UICONTROL Download]**.

   ![](assets/download_basic.png)

1. Selezionate il formato desiderato per il rapporto:

   * **[!UICONTROL PDF]**: Specifica che il rapporto verrà scaricato in Adobe PDF, che consente di condividere il rapporto con altri, indipendentemente dal sistema computer in esecuzione.
   * **[!UICONTROL CSV]**: Indica che il rapporto verrà scaricato in [!DNL .csv] (formato con valori separati da virgole).
   * **[!UICONTROL Excel]**: Specifica che il rapporto verrà scaricato in formato Microsoft Excel, che consente di condividere il rapporto con altri utenti che possono aprirlo in un programma foglio di calcolo.
   * **[!UICONTROL Word]**: Specifica che il rapporto verrà scaricato in formato Microsoft Word.
   >[!NOTE]
   >
   >Se utilizzate uno dei formati di esportazione non elaborati per scaricare un rapporto e il nome della pagina è vuoto, Adobe Analytics probabilmente non aveva tempo sufficiente per elaborare i dati. Scaricate il report in un secondo momento.

## Manage scheduled reports {#task_C17677C543454FF2B06D10EA5652DFBC}

Informazioni sulla gestione dei report pianificati.

<!-- 

t_schedule_manage.xml

 -->

In the [!UICONTROL Schedule Reports Manager], you can edit and delete recurring report deliveries. Puoi programmare le consegne in modo che i rapporti vengano inviati via e-mail o FTP a un indirizzo specifico. Puoi configurare queste pianificazioni per inviare automaticamente i rapporti a intervalli specificati per un periodo di tempo o indefinito, oppure interrompere la consegna di un rapporto periodico.

The [!UICONTROL Schedule Report Manager] shows the items that a specific user has created. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte.

1. To access the manager, click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Scheduled Reports]**.

## Share a report link {#task_9711DDE9E140451B8C914EC5513E21EC}

Procedura che descrive come condividere un rapporto generando un collegamento (URL) per l'invio a un altro utente.

<!-- 

t_reports_share_link.xml

 -->

Quando il destinatario fa clic sul collegamento, richiede le credenziali di accesso (nome società, nome utente e password). Dopo l'accesso, al destinatario viene mostrato il rapporto generato dall'utente originale. Si applicano restrizioni alle autorizzazioni standard.

**Per condividere un collegamento di rapporti**

1. Esegui un report.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Link to This Report]**.

## Unsubscribe from scheduled reports {#concept_6B48360F935740B6851BA85D32DEF637}

Puoi annullare l'iscrizione ai rapporti pianificati. Il rapporto non verrà più visualizzato, anche se il nome utente viene nuovamente aggiunto al report pianificato.

<!-- 

t_schedule_unsubscribe.xml

 -->

>[!IMPORTANT]
>
>Per ricevere nuovamente il rapporto, è necessario creare una nuova pianificazione.

Per annullare l'iscrizione a un rapporto pianificato:

1. Visualizzate l'e-mail con il collegamento al rapporto da cui desiderate annullare l'iscrizione.

   ![](assets/unsubscribe-email.png)

1. Click the **[!UICONTROL click here]** link next to **[!UICONTROL To cancel automatic delivery of this report]**.

1. Confermate la cancellazione della consegna dei rapporti.

   >[!NOTE]
   >
   >Questo flusso di lavoro è uguale sia che tu sia il programmatore di report o il destinatario del report.

La cancellazione di un rapporto non annulla il rapporto pianificato.

Per annullare un rapporto pianificato, andate a Schedule Manager (Gestione pianificazione) e fate clic sulla X rossa accanto al nome del report. [Altro...](../../analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
