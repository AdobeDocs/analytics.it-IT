---
description: Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.
subtopic: Schedule
title: Pianificazione e distribuzione del rapporto
uuid: 1230b0f3-e026-4b83-b231-14d6f75a3836
feature: Reports & Analytics Basics
role: User, Admin
exl-id: ec59d365-f294-41da-ae36-3b4ebe64ab23
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '1718'
ht-degree: 11%

---

# Pianificazione e distribuzione del rapporto

Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.

>[!IMPORTANT]
>Il 21 aprile 2022 è stata annunciata la rimozione di diverse funzioni specifiche dei rapporti pianificati in preparazione della scadenza del ciclo di vita di Reports &amp; Analytics, precedentemente annunciata. Queste funzionalità includevano la possibilità di pianificare nuovi rapporti e nuovi estratti di dati. In risposta alle richieste dei clienti che necessitano di un’estensione e per facilitare la transizione da Reports &amp; Analytics, abbiamo deciso di estendere l’accesso a queste funzioni fino al 31 gennaio 2023. Si prega di notare che le scadenze per i rapporti e gli estratti dei dati continueranno a essere limitate a nove mesi; la consegna del report e dell’estrazione dei dati verrà sospesa alla fine di questo periodo, a meno che la pianificazione non venga riattivata. [Ulteriori informazioni](/help/analyze/reports-analytics/scheduled-reports-eol.md)

Quando pianifichi la consegna di un report in un&#39;applicazione di Adobe Analytics puoi utilizzare gli strumenti Scheduling (Pianificazione) e Distribution (Distribuzione) per visualizzare i file automaticamente inviati e modificati o per terminare le consegne.

A causa delle differenze nei meccanismi di elaborazione e nelle piattaforme, i vari tipi di rapporti scaricabili e pianificati disponibili in Adobe Analytics presentano limitazioni diverse per quanto riguarda il numero massimo di righe che è possibile elaborare in una singola richiesta. Di seguito sono riportati i limiti di ogni:

* Word, CSV, Excel, HTML e PDF: lo stesso numero di righe visibili nel rapporto. Per impostazione predefinita questo limite è di 50 righe, ma può essere aumentato fino a 200. I rapporti sulle suddivisioni hanno un limite massimo di 50 righe.
* Estratti di dati: 50.000 righe
* Data Warehouse: Illimitata

Queste limitazioni si applicano ai singoli rapporti pianificati e scaricati; le dashboard sono limitate alla quantità di spazio disponibile all’interno di un reportlet.

## Tempo di consegna e tempo di elaborazione

La &quot;Data e ora di consegna&quot; o &quot;Ora del giorno&quot; immessa dall’utente specifica l’ora in cui deve iniziare l’elaborazione del rapporto, non l’ora in cui verrà effettivamente consegnato. Il momento in cui il rapporto verrà consegnato si basa principalmente sul tempo necessario per l’elaborazione. L’elaborazione di rapporti complessi e di grandi dimensioni richiede più tempo rispetto a quelli più semplici. Ad esempio, se l’elaborazione di un rapporto richiede 15 minuti, il tempo di consegna effettivo sarà di almeno 15 minuti oltre il &quot;Orario di consegna&quot; o il &quot;Giorno&quot; originariamente specificati.

Vi sono inoltre diversi altri fattori che possono aumentare ulteriormente il ritardo prima che la relazione venga effettivamente consegnata:

* **Esecuzione simultanea di più pianificazioni diverse dello stesso tipo** (ad esempio, molte dashboard, ecc.) può sovraccaricare il sistema. Il sistema di pianificazione consente solo l’esecuzione simultanea di alcuni (5-10) rapporti di qualsiasi tipo. Quando sono pianificati più di 5-10 rapporti alla volta, alcuni dovranno attendere la fine di altri rapporti prima di poter iniziare l’elaborazione. Questo problema può essere attenuato pianificando i rapporti di un’azienda in momenti diversi nel corso della giornata o dell’ora, anziché simultaneamente.
* Oltre al tipo di rapporto specifico (dashboard, ecc.), i rapporti attenderanno in linea anche se l’azienda ha **più di 15-20 rapporti di qualsiasi tipo pianificati contemporaneamente (per tutti i diversi tipi di rapporti)**. Questo problema può essere risolto scaglionando i tempi di pianificazione invece di eseguirne molti contemporaneamente.
* **Problemi nei servizi a valle** su cui si basa il modulo di pianificazione può influenzare anche la consegna dei rapporti. Ad esempio, se utilizzi le API in modo indipendente per eseguire i rapporti e riempire la coda di richieste API, i rapporti pianificati potrebbero essere consegnati lentamente mentre competi per quella risorsa.
* **Latenza suite di rapporti** (un ritardo nella raccolta dei dati) può anche ritardare alcuni rapporti pianificati.


## Inviare un rapporto {#task_27642CD33D484FD0BF59EBD159EEF52C}

Per scaricare e inviare i rapporti tramite e-mail in diversi formati e pianificare la consegna di un rapporto:

1. Esegui un rapporto, quindi fai clic su **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Specifica le opzioni di consegna:

   | Opzione | Descrizione |
   |--- |--- |
   | Formato | Seleziona PDF o HTML. |
   | Invia a | Specifica un indirizzo e-mail per ricevere il rapporto. |
   | Oggetto | Oggetto dell’e-mail. |
   | Pianificazione | Seleziona questa opzione per inviare il rapporto immediatamente o a un intervallo diverso. |

1. Clic **[!UICONTROL Advanced Delivery Options]** per specificare una pianificazione di consegna.

| Opzione | Descrizione |
| --- |--- |
| Nome file report | Specifica il nome del report. Il formato predefinito è `<report name> for <suite> - <report date range>`. Per specificare un nome personalizzato, seleziona [!UICONTROL Custom]. |
| Formato rapporto | Consente di specificare i formati PDF, CSV, Excel, HTML, Word o Mobile per la consegna. Se selezioni CSV, puoi anche specificare la codifica per CSV:<ul><li>Shift-JIS: codifica di caratteri giapponese.</li><li>EUC-JP: codice Unix esteso, principalmente per giapponese, coreano e cinese semplificato.</li></ul> |
| Contenuto del rapporto | <ul><li>Numero di righe nella tabella: specifica il numero di righe che si desidera visualizzare nella tabella del rapporto che si sta inviando.</li><li>Language for header and footer (Lingua per intestazione e piè di pagina): specifica la lingua dell&#39;intestazione e del piè di pagina.</li><li>Commenti: specifica il testo che viene visualizzato all&#39;inizio del rapporto.</li></ul> |
| Invia file di firma digitale | Quando richiedi un rapporto, ad esempio un rapporto con segnalibro o richieste Data Warehouse, puoi richiedere una firma dati. La firma digitale di Adobe non limita gli utenti che hanno accesso ai dati, ma lo scopo del file di firma digitale (.sig) è quello di verificare la validità del file di report consegnato. Utilizzando la firma digitale, i destinatari del report possono verificare che il file provenga da un Adobe e non sia stato modificato. |
| Destinazione rapporto | <ul><li>E-mail: consente di configurare le impostazioni dell’indirizzo e-mail, l’oggetto e le note.</li><li>FTP: consente di configurare le impostazioni FTP, inclusi Host, Porta, Directory, Nome utente e Password.</li></ul> |

1. Fai clic su **[!UICONTROL Scheduling Options]** (Usa modello di attribuzione non predefinito).

| Opzione | Descrizione |
|--- |--- |
| Invia rapporto ora | Invia il report immediatamente. |
| Pianifica per un momento successivo | Visualizza le opzioni per specificare un intervallo di tempo e le opzioni di consegna. |
| Intervallo di tempo rapporto | **Fisso**: impedisce che la data avanzi con il passare del tempo. **Continuo**: consente di anticipare la data col passare del tempo. Alcune considerazioni:<ul><li>Se selezioni Rinnovo sia per la data di inizio che per la data di fine e selezioni un rapporto giornaliero per il giorno precedente, riceverai un’e-mail ogni giorno con un rapporto per il giorno precedente.</li><li>Se si seleziona Fisso per il giorno di inizio e continuo per il giorno di fine, si riceve il primo giorno un rapporto per il giorno precedente. Il secondo giorno si riceve un rapporto per i due giorni precedenti, il terzo giorno si riceve un rapporto per i tre giorni precedenti e così via.</li><li>Se si seleziona Fisso sia per la data di inizio che per la data di fine, ogni giorno si riceve un rapporto identico per i giorni specificati.</li><li>Non è possibile selezionare una data di inizio continua e una data di fine fissa.</li></ul> |
| Frequenza di consegna | <ul><li>**Ogni ora**: consegna l’e-mail ogni ora, a ore alterne o con qualsiasi altro intervallo di ore.</li><li>**Giornaliero**: invia l’e-mail ogni giorno, a giorni alterni, ogni tre giorni o qualsiasi altro intervallo di giorni. Puoi anche inviarlo ogni giorno feriale.</li><li>**Ogni settimana**: invia l’e-mail ogni settimana, a settimane alterne, ogni tre settimane o qualsiasi altro intervallo di settimane. Puoi anche specificare il giorno della settimana in cui viene inviato.</li><li>**Mensile**: specifica l’intervallo in numeri di mesi; è inoltre possibile selezionare il giorno del mese in cui viene inviato o il giorno della settimana in una settimana specifica del mese.</li><li>**Annuale**: specifica il giorno dell’anno in cui viene inviato il rapporto, oppure è possibile inviarlo in un giorno specifico della settimana in qualsiasi settimana dell’anno.</li><li>**Ora del giorno**: si applica al fuso orario associato alla suite di rapporti selezionata.</li></ul> |
| Opzioni di fine consegna | <ul><li>**Non terminare mai**: non specifica alcuna fine.</li><li>**Termina dopo `value` occorrenze**: specifica il numero di occorrenze prima della fine della consegna.</li><li>**Fine il**: consente di specificare una data specifica. Se si desidera elaborare i dati nella stessa data dei dati del report, il report contiene solo i dati inseriti nel database al momento dell&#39;invio del report. Poiché l’elaborazione completa per un giorno può richiedere fino a 24 ore, i dati completi potrebbero non essere disponibili al momento dell’invio del rapporto. Per i dati completi, imposta sempre il tempo di elaborazione per 24 ore dopo la fine del periodo di reporting.</li></ul> |

## Stampare un rapporto {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Per stampare un rapporto:

1. Esegui un rapporto.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Print]**.  ![](assets/print.png)

## Scaricare un rapporto utilizzando le opzioni di base {#task_43660107A1C9485D92981CD75B562577}

Scarica informazioni dettagliate su un rapporto specifico nei formati PDF, CSV, Excel o Esportazione dati non elaborati.

1. In entrata  **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** , seleziona un rapporto da visualizzare.
1. Fai clic su **[!UICONTROL Download]** (Usa modello di attribuzione non predefinito).

   ![](assets/download_basic.png)

1. Seleziona il formato desiderato per il rapporto:

   * **[!UICONTROL PDF]**: specifica che il report verrà scaricato in Adobe PDF, consentendo la condivisione del report con altri utenti, indipendentemente dal computer in cui il destinatario è in esecuzione.
   * **[!UICONTROL CSV]**: specifica che il rapporto verrà scaricato in [!DNL .csv] (formato di valori separati da virgole).
   * **[!UICONTROL Excel]**: specifica che il report verrà scaricato in formato Microsoft Excel, che consente di condividere il report con altri utenti che possono aprirlo in un foglio di calcolo.
   * **[!UICONTROL Word]**: specifica che il report verrà scaricato in formato Microsoft Word.

   >[!NOTE]
   >
   >Se utilizzi uno dei formati di esportazione non elaborati per scaricare un rapporto e il nome della pagina è vuoto, è probabile che Adobe Analytics non abbia avuto abbastanza tempo per elaborare i dati. Scarica il rapporto in un secondo momento.

## Gestire i rapporti pianificati {#task_C17677C543454FF2B06D10EA5652DFBC}

Informazioni sulla gestione dei rapporti pianificati.

In [!UICONTROL Schedule Reports Manager], puoi modificare ed eliminare le consegne ricorrenti di rapporti. Puoi programmare le consegne in modo che i rapporti vengano inviati via e-mail o FTP a un indirizzo specifico. Puoi configurare queste pianificazioni in modo da inviare automaticamente i rapporti a intervalli specifici per una durata di tempo o indefinita, oppure interrompere la consegna di un rapporto ricorrente.

Il [!UICONTROL Schedule Report Manager] mostra gli elementi creati da un utente specifico. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte.

1. Per accedere al manager, fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Scheduled reports]**.

## Condividere un collegamento a un rapporto {#task_9711DDE9E140451B8C914EC5513E21EC}

Puoi condividere un rapporto generando un collegamento di rapporto (URL) da inviare a un altro utente.

Quando il destinatario fa clic sul collegamento, il sistema richiede le credenziali di accesso (nome società, nome utente e password). Dopo aver effettuato l’accesso, al destinatario viene mostrato il rapporto generato dall’utente originale. Si applicano le limitazioni di autorizzazione standard.

Per condividere un collegamento a un rapporto:

1. Esegui un rapporto.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Link to This Report]**.

## Annulla iscrizione ai report pianificati {#concept_6B48360F935740B6851BA85D32DEF637}

Puoi annullare l’abbonamento ai rapporti pianificati. Non riceverai più il rapporto anche se il tuo nome utente viene aggiunto nuovamente al rapporto pianificato.

>[!IMPORTANT]
>
>Per ricevere nuovamente il rapporto, è necessario creare una nuova pianificazione.

Per annullare l’abbonamento a un rapporto pianificato:

1. Visualizza l’e-mail con il collegamento al rapporto da cui desideri annullare l’abbonamento.

   ![](assets/unsubscribe-email.png)

1. Fai clic su **[!UICONTROL click here]** collegamento accanto a **[!UICONTROL To cancel automatic delivery of this report]**.

1. Conferma di voler annullare la consegna del rapporto.

   >[!NOTE]
   >
   >Questo flusso di lavoro è lo stesso indipendentemente dal fatto che tu sia il responsabile della pianificazione o il destinatario del rapporto.

L’annullamento dell’abbonamento a un rapporto non annulla il rapporto pianificato.

Per annullare un rapporto pianificato, accedi a Gestione programmi e fai clic sulla X rossa accanto al nome del rapporto. [Altro...](/help/analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
