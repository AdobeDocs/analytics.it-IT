---
description: Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.
seo-description: Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.
seo-title: Pianificazione e distribuzione del rapporto
solution: Analytics
subtopic: Pianificazione
title: Pianificazione e distribuzione del rapporto
topic: Reports and Analytics
uuid: 1230 b 0 f 3-e 026-4 b 83-b 231-14 d 6 f 75 a 3836
translation-type: tm+mt
source-git-commit: cca2896eaaf3786e79e7bd389bcb5a409e3d357e

---


# Pianificazione e distribuzione del rapporto

Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.

Quando pianifichi la consegna di un report in un'applicazione di Adobe Analytics puoi utilizzare gli strumenti Scheduling (Pianificazione) e Distribution (Distribuzione) per visualizzare i file automaticamente inviati e modificati o per terminare le consegne.

A causa di differenze nei meccanismi di elaborazione e nelle piattaforme, i diversi tipi di rapporti scaricabili e pianificati disponibili in Adobe Analytics presentano limitazioni diverse rispetto al numero massimo di righe che possono essere elaborate in una singola richiesta. I limiti di ciascuna:

* Word, CSV, Excel, HTML e PDF: Lo stesso numero di righe visibili nel report. Per impostazione predefinita, questo limite è di 50 righe ma può aumentare fino a 200. I rapporti di analisi hanno un limite rigido di 50 righe.
* Estratti di dati: 50,000 righe
* Data Warehouse: Illimitato

Tali limitazioni sono per i singoli rapporti pianificati e scaricati; Le dashboard sono limitate alla quantità di spazio disponibile all'interno di un minirapporto.

>[!NOTE]
>
>Il "Tempo di consegna"/"Ora del giorno" immesso dall'utente specifica l'ora in cui deve iniziare l'elaborazione, non l'ora in cui verrà effettivamente consegnato. L'ora effettiva in cui il rapporto verrà distribuito dipende principalmente dal tempo necessario per la elaborazione (i rapporti complessi e di grandi dimensioni richiedono più tempo rispetto ai rapporti più semplici). Ad esempio, se un rapporto richiede 15 minuti da elaborare, il tempo di consegna effettivo sarà almeno 15 minuti oltre il «Tempo di consegna»/«Ora del giorno» specificato originariamente.
>Inoltre, esistono molti altri fattori che possono aumentare ulteriormente il ritardo prima di distribuire il rapporto:
>
> * **Esecuzione contemporanea di numerose pianificazioni dello stesso tipo** (ad esempio, molti dashboard, ecc.) può sovraccaricare il sistema. Il sistema Pianificazione consente solo alcuni (5-10) rapporti di qualsiasi tipo da eseguire simultaneamente; pertanto, quando si pianificano più di 5-10 contemporaneamente, alcuni dovranno attendere in linea per terminare altri rapporti prima di iniziare l'elaborazione. Questo problema può essere mitigato pianificando i report di una società in tempi rapidizzati durante il giorno o l'ora, anziché simultaneamente.
> * Oltre al tipo di rapporto specifico (Dashboard, ecc.), i rapporti saranno anche in linea se l'azienda ha **più di 15-20 di qualsiasi tipo di rapporto pianificato contemporaneamente (su tutti i tipi di rapporti)**. Questa operazione può essere mitigata rendendo difficoltosa la pianificazione temporale, evitando che venga eseguita contemporaneamente.
> * **I problemi nei servizi** a valle richiesti dal Pianificatore possono influire anche sulla distribuzione dei report. Ad esempio, se utilizzi in modo indipendente le API per eseguire rapporti e compilare la coda delle richieste API, i rapporti pianificati possono essere distribuiti lentamente mentre ti competi per tale risorsa.
> * **La latenza della suite di rapporti** (un ritardo nella raccolta dati) può anche ritardare alcuni rapporti pianificati.



## Invio di un rapporto {#task_27642CD33D484FD0BF59EBD159EEF52C}

Procedura che descrive come scaricare ed e-mail in diversi formati e pianificare un rapporto per la consegna.

1. Run a report, then click **[!UICONTROL More]** &gt; **[!UICONTROL Send]**.
1. Specificate le opzioni di consegna:

   | Opzione | Descrizione |
   |--- |--- |
   | Formato | Selezionare PDF o HTML. |
   | Invia a | Fornite un indirizzo e-mail per ricevere il rapporto. |
   | Oggetto | Oggetto dell'e-mail. |
   | Pianificazione | Seleziona per inviare il rapporto immediatamente o a un intervallo diverso. |

1. Fate clic su **[!UICONTROL Advanced Delivery Options]** per specificare una pianificazione di consegna.

| Opzione | Descrizione |
|--- |--- |
| Nome file rapporto | Specifica il nome del rapporto. Il formato predefinito `<report name> for <suite> - <report date range>`è. Per specificare un nome personalizzato [!UICONTROL Custom], selezionatelo. |
| Formato rapporto | Consente di specificare i formati PDF, CSV, Excel, HTML, Word o Mobile per la distribuzione. Se selezionate CSV, potete anche specificare la codifica per CSV:<ul><li>Shift-JIS: Codifica caratteri giapponese.</li><li>EUC-JP: Codice Unix esteso, principalmente per giapponese, coreano e cinese semplificato.</li></ul> |
| Sommario | <ul><li>Numero di righe nella tabella: Specifica il numero di righe da visualizzare nella tabella del rapporto che stai inviando.</li><li>Lingua per intestazione e piè di pagina: Specifica la lingua dell'intestazione e del piè di pagina.</li><li>Commenti: Specifica il testo che viene visualizzato all'inizio del rapporto.</li></ul> |
| Invia file firma digitale | Quando si richiede un rapporto, ad esempio un rapporto contrassegnato o le richieste di Data Warehouse, è possibile richiedere una firma dati. La firma digitale di Adobe non limita chi ha accesso ai dati, ma lo scopo del file di firma digitale (. sig) è quello di verificare la validità del file di report consegnato. Utilizzando la firma digitale, i destinatari del report possono verificare che il file sia passato da Adobe e non sia stato alterato. |
| Destinazione rapporto | <ul><li>E-mail: Consente di configurare le impostazioni dell'indirizzo e-mail, l'oggetto e le note.</li><li>FTP: Consente di configurare le impostazioni FTP, inclusi Ospitante, Porta, Directory, Nome utente e Password.</li></ul> |

1. Fai clic su **[!UICONTROL Scheduling Options]**.

| Opzione | Descrizione |
|--- |--- |
| Invia rapporto ora | Invia il rapporto immediatamente. |
| Pianifica per successivo | Visualizza le opzioni per specificare un intervallo di tempo e le opzioni di consegna. |
| Intervallo di tempo rapporto | **Problema corretto**: Impedisce l'avanzamento della data durante la trasmissione del tempo. **Scorrimento**: Consente l'avanzamento della data durante la trasmissione del tempo. Considerazioni:<ul><li>Se selezionate Scorrimento per le date di inizio e di fine e selezionate un rapporto giornaliero per il giorno precedente, riceverete un messaggio e-mail ogni giorno con un rapporto per il giorno precedente.</li><li>Se selezionate Fisso per il giorno iniziale e continua per il giorno finale, riceverete un rapporto per il giorno precedente. Il secondo giorno in cui riceverete un rapporto per i due giorni precedenti e il terzo giorno riceverete un rapporto per i tre giorni precedenti e così via.</li><li>Se selezionate Fisso per le date iniziale e finale, ogni giorno che ricevete un rapporto identico per i giorni specificati.</li><li>Non è possibile selezionare una data di inizio continua e una data di fine corretta.</li></ul> |
| Frequenza di consegna | <ul><li>**Orario**: Invia l'e-mail ogni ora, ogni ora, o qualsiasi altro intervallo di ore.</li><li>**Giornaliero**: Invia l'e-mail ogni giorno, ogni giorno, ogni terzo giorno o un altro intervallo di giorni. Puoi anche inviarlo ogni giorno feriale.</li><li>**Settimanale**: Invia l'e-mail ogni settimana, l'altra settimana, ogni terza settimana o qualsiasi altro intervallo di settimane. Potete anche specificare il giorno della settimana in cui viene inviato.</li><li>**Mensile**: Specifica l'intervallo in numero di mesi, inoltre è possibile selezionare il giorno del mese in cui viene inviato, oppure il giorno della settimana in una settimana specifica del mese.</li><li>**Annuale**: Specifica il giorno dell'anno su cui viene inviato il rapporto, oppure puoi inviarlo in un giorno specifico della settimana in qualsiasi settimana dell'anno.</li><li>**Ora del giorno**: Si applica al fuso orario associato alla suite di rapporti selezionata.</li></ul> |
| Opzioni di consegna finale | <ul><li>**Non terminare**: Non specifica alcuna fine.</li><li>**Termina dopo`value`occorrenze**: Specifica il numero di occorrenze prima della fine della consegna.</li><li>**Termina su**: Consente di specificare una data specifica. Se si desidera elaborare i dati nella stessa data dei dati del rapporto, il rapporto contiene solo i dati che sono stati immessi nel database al momento dell'invio del rapporto. Poiché l'elaborazione completa per un giorno può richiedere fino a 24 ore, i dati completi potrebbero non essere disponibili al momento dell'invio del report. Per i dati completi, impostare sempre il tempo di elaborazione di 24 ore dopo la fine del periodo di reporting.</li></ul> |

## Stampare un rapporto {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Procedura che descrive come stampare un rapporto.

1. Esegui un report.
1. Clic **[!UICONTROL More]** &gt; **[!UICONTROL Print]**.  ![](assets/print.png)

## Download a report using basic options {#task_43660107A1C9485D92981CD75B562577}

Scarica informazioni dettagliate su un rapporto specifico nei formati di esportazione PDF, CSV, Excel o Raw.

1. In **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** , selezionate un rapporto da visualizzare.
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

## Gestire i rapporti pianificati {#task_C17677C543454FF2B06D10EA5652DFBC}

Informazioni sulla gestione dei report pianificati.

In [!UICONTROL Schedule Reports Manager], puoi modificare ed eliminare le consegne ricorrenti dei rapporti. Puoi programmare le consegne in modo che i rapporti vengano inviati via e-mail o FTP a un indirizzo specifico. Puoi configurare queste pianificazioni per inviare automaticamente i rapporti a intervalli specificati per un periodo di tempo o indefinito, oppure interrompere la consegna di un rapporto periodico.

The [!UICONTROL Schedule Report Manager] shows the items that a specific user has created. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte.

1. Per accedere al manager, fate clic **[!UICONTROL Analytics]** su &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Scheduled Reports]**.

## Condividere un collegamento di rapporti {#task_9711DDE9E140451B8C914EC5513E21EC}

Procedura che descrive come condividere un rapporto generando un collegamento (URL) per l'invio a un altro utente.

Quando il destinatario fa clic sul collegamento, richiede le credenziali di accesso (nome società, nome utente e password). Dopo l'accesso, al destinatario viene mostrato il rapporto generato dall'utente originale. Si applicano restrizioni alle autorizzazioni standard.

**Per condividere un collegamento di rapporti**

1. Esegui un report.
1. Clic **[!UICONTROL More]** &gt; **[!UICONTROL Link to This Report]**.

## Annullare l'iscrizione ai rapporti pianificati {#concept_6B48360F935740B6851BA85D32DEF637}

Puoi annullare l'iscrizione ai rapporti pianificati. Il rapporto non verrà più visualizzato, anche se il nome utente viene nuovamente aggiunto al report pianificato.

>[!IMPORTANT]
>
>Per ricevere nuovamente il rapporto, è necessario creare una nuova pianificazione.

Per annullare l'iscrizione a un rapporto pianificato:

1. Visualizzate l'e-mail con il collegamento al rapporto da cui desiderate annullare l'iscrizione.

   ![](assets/unsubscribe-email.png)

1. Fate clic sul **[!UICONTROL click here]** collegamento accanto **[!UICONTROL To cancel automatic delivery of this report]**.

1. Confermate la cancellazione della consegna dei rapporti.

   >[!NOTE]
   >
   >Questo flusso di lavoro è uguale sia che tu sia il programmatore di report o il destinatario del report.

La cancellazione di un rapporto non annulla il rapporto pianificato.

Per annullare un rapporto pianificato, andate a Schedule Manager (Gestione pianificazione) e fate clic sulla X rossa accanto al nome del report. [Altro...](../../analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
