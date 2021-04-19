---
description: Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.
subtopic: Schedule
title: Pianificazione e distribuzione del rapporto
uuid: 1230b0f3-e026-4b83-b231-14d6f75a3836
feature: Nozioni di base su Reports & Analytics, Reports and Analytics
role: Business Practitioner, Administrator
exl-id: ec59d365-f294-41da-ae36-3b4ebe64ab23
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 5%

---

# Pianificazione e distribuzione del rapporto

Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.

Quando pianifichi la consegna di un report in un&#39;applicazione di Adobe Analytics puoi utilizzare gli strumenti Scheduling (Pianificazione) e Distribution (Distribuzione) per visualizzare i file automaticamente inviati e modificati o per terminare le consegne.

A causa delle differenze nei meccanismi e nelle piattaforme di elaborazione, i vari tipi di rapporti scaricabili e pianificati disponibili in Adobe Analytics hanno limitazioni diverse rispetto al numero massimo di righe che possono elaborare in una singola richiesta. Di seguito sono riportati i limiti di ciascuno:

* Word, CSV, Excel, HTML e PDF: Lo stesso numero di righe visibili nel rapporto. Per impostazione predefinita questo limite è di 50 righe ma può aumentare fino a 200. I rapporti di suddivisione hanno un limite rigido di 50 righe.
* Estratti di dati: 50.000 righe
* Data Warehouse: Senza limiti

Tali limitazioni riguardano i singoli rapporti pianificati e scaricati; le dashboard sono limitate alla quantità di spazio disponibile all’interno di un reportlet.

>[!NOTE]
>
>Il valore &quot;Ora di consegna&quot;/&quot;Ora del giorno&quot; immesso dall’utente specifica l’ora in cui il rapporto deve iniziare l’elaborazione, non l’ora in cui verrà effettivamente consegnato. Il tempo effettivo di consegna del rapporto si basa principalmente sul tempo necessario all’elaborazione (l’elaborazione di rapporti complessi e di grandi dimensioni richiede più tempo rispetto a quella di rapporti più semplici). Ad esempio, se l’elaborazione di un rapporto richiede 15 minuti, il tempo di consegna effettivo sarà di almeno 15 minuti superiore a quello originariamente specificato come &quot;Ora di consegna&quot;/&quot;Ora del giorno&quot;.
>Inoltre, vi sono altri fattori che possono aumentare ulteriormente il ritardo prima che la relazione venga effettivamente presentata:
>
> * **Esecuzione simultanea di più pianificazioni dello stesso tipo**  (ad esempio, molte dashboard, ecc.) può sovraccaricare il sistema. Il sistema di programmazione consente solo l&#39;esecuzione simultanea di alcuni report (5-10) di un tipo qualsiasi, quindi quando più di 5-10 vengono tutti pianificati contemporaneamente, alcuni dovranno attendere il completamento di altri report prima che possano iniziare l&#39;elaborazione. Questo problema può essere attenuato pianificando i report di un&#39;azienda in orari scaglionati per tutto il giorno o l&#39;ora, anziché simultaneamente.
> * Oltre al tipo di rapporto specifico (dashboard, ecc.), i rapporti attendono anche se l’azienda ha **più di 15-20 tipi di rapporto pianificati contemporaneamente (per tutti i diversi tipi di rapporto)**. Questo può essere attenuato dai tempi di pianificazione sbalorditivi invece di averne molti eseguiti contemporaneamente.
> * **Anche i problemi relativi ai** servizi a valle su cui si basa lo scheduler possono influenzare la consegna dei report. Ad esempio, se utilizzi in modo indipendente le API per eseguire i rapporti e compilare la coda di richiesta API, i rapporti pianificati potrebbero essere consegnati lentamente mentre ti trovi in competizione per quella risorsa.
> * **La latenza della suite di rapporti**  (un ritardo nella raccolta dei dati) può anche ritardare alcuni rapporti pianificati.



## Invia un rapporto {#task_27642CD33D484FD0BF59EBD159EEF52C}

Passaggi che descrivono come scaricare ed inviare per e-mail i rapporti in diversi formati e come pianificare la consegna di un rapporto.

1. Esegui un rapporto, quindi fai clic su **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Specifica le opzioni di consegna:

   | Opzione | Descrizione |
   |--- |--- |
   | Formato | Selezionare PDF o HTML. |
   | Invia a | Fornisci un indirizzo e-mail per ricevere il rapporto. |
   | Oggetto | Oggetto dell&#39;e-mail. |
   | Pianificazione | Selezionare questa opzione per inviare il report immediatamente o a un intervallo diverso. |

1. Fai clic su **[!UICONTROL Advanced Delivery Options]** per specificare la pianificazione della consegna.

| Opzione | Descrizione |
|--- |--- |
| Nome file del rapporto | Specifica il nome del report. Il formato predefinito è `<report name> for <suite> - <report date range>`. Per specificare un nome personalizzato, selezionare [!UICONTROL Custom]. |
| Formato del rapporto | Consente di specificare i formati PDF, CSV, Excel, HTML, Word o Mobile da distribuire. Se selezioni CSV, puoi anche specificare la codifica per CSV:<ul><li>Shift-JIS: Codifica caratteri giapponese.</li><li>EUC-JP: Codice Unix esteso, principalmente per giapponese, coreano e cinese semplificato.</li></ul> |
| Contenuto del rapporto | <ul><li>Numero di righe nella tabella: Specifica il numero di righe che si desidera visualizzare nella tabella del rapporto che si sta inviando.</li><li>Lingua per intestazione e piè di pagina: Specifica la lingua dell&#39;intestazione e del piè di pagina.</li><li>Commenti: Specifica il testo visualizzato all&#39;inizio del report.</li></ul> |
| Invia file di firma digitale | Quando si richiede un rapporto, ad esempio un rapporto con segnalibro o richieste di Data Warehouse, è possibile richiedere una firma dati. La firma digitale di Adobe non limita l’accesso ai dati, ma lo scopo del file di firma digitale (.sig) è quello di verificare la validità del file di rapporto consegnato. Utilizzando la firma digitale, i destinatari del rapporto possono verificare che il file provenga da un Adobe e che non sia stato modificato. |
| Destinazione report | <ul><li>E-mail: Consente di configurare le impostazioni dell’indirizzo e-mail, l’oggetto e le note.</li><li>FTP: Consente di configurare le impostazioni FTP, inclusi Host, Porta, Directory, Nome utente e Password.</li></ul> |

1. Fai clic su **[!UICONTROL Scheduling Options]**.

| Opzione | Descrizione |
|--- |--- |
| Invia subito rapporto | Invia il rapporto immediatamente. |
| Pianificazione per un momento successivo | Visualizza le opzioni per specificare un intervallo di tempo e le opzioni di consegna. |
| Intervallo di tempo del rapporto | **Corretto**: Impedisce l’avanzamento della data con il passare del tempo. **Rolling**: Consente alla data di avanzare man mano che passa il tempo. Alcune considerazioni:<ul><li>Se selezioni Rolling per le date di inizio e di fine e selezioni un rapporto giornaliero per il giorno precedente, ricevi ogni giorno un’e-mail con un rapporto per il giorno precedente.</li><li>Se selezioni Fisso per il giorno iniziale e continuo per il giorno finale, il primo giorno riceverai un rapporto per il giorno precedente. Il secondo giorno riceverai un rapporto per i due giorni precedenti e il terzo giorno riceverai un rapporto per i tre giorni precedenti e così via.</li><li>Se selezioni Fisso per le date di inizio e di fine, ogni giorno ricevi un rapporto identico per i giorni specificati.</li><li>Non è possibile selezionare una data di inizio continua e una data di fine fissa.</li></ul> |
| Frequenza di consegna | <ul><li>**Orario**: Invia l’e-mail ogni ora, ogni altra ora o qualsiasi altro intervallo di ore.</li><li>**Giornaliero**: Invia l’e-mail ogni giorno, ogni altro giorno, ogni terzo giorno o qualsiasi altro intervallo di giorni. Puoi anche inviarlo ogni giorno feriale.</li><li>**Settimanale**: Invia l’e-mail ogni settimana, altra settimana, ogni terza settimana o qualsiasi altro intervallo di settimane. Puoi inoltre specificare il giorno della settimana in cui viene inviata.</li><li>**Mensile**: Specifica l&#39;intervallo in numeri di mesi e puoi anche selezionare il giorno del mese in cui viene inviato o il giorno della settimana in una settimana specifica del mese.</li><li>**Annuale**: Specifica il giorno dell&#39;anno in cui viene inviato il rapporto, oppure puoi inviarlo in un giorno specifico della settimana in una qualsiasi settimana dell&#39;anno.</li><li>**Ora del giorno**: Si applica al fuso orario associato alla suite di rapporti selezionata.</li></ul> |
| Opzioni di consegna finale | <ul><li>**Mai terminare**: Specifica l&#39;assenza di fine.</li><li>**Fine dopo  `value` le occorrenze**: Specifica il numero di occorrenze prima della fine della consegna.</li><li>**Fine**: Consente di specificare una data specifica. Se si desidera elaborare i dati alla stessa data dei dati del rapporto, quest&#39;ultimo contiene solo i dati inseriti nel database al momento dell&#39;invio del rapporto. Poiché l’elaborazione completa per un giorno può richiedere fino a 24 ore, al momento dell’invio del rapporto potrebbero non essere disponibili dati completi. Per i dati completi, imposta sempre il tempo di elaborazione per 24 ore dopo la fine del periodo di riferimento.</li></ul> |

## Stampa un report {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Passaggi che descrivono come stampare un rapporto.

1. Esegui un report.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Print]**.  ![](assets/print.png)

## Download di un rapporto utilizzando le opzioni di base {#task_43660107A1C9485D92981CD75B562577}

Scarica informazioni dettagliate su un rapporto specifico nei formati PDF, CSV, Excel o Raw Data Export.

1. In **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** , seleziona un rapporto da visualizzare.
1. Fai clic su **[!UICONTROL Download]**.

   ![](assets/download_basic.png)

1. Seleziona il formato desiderato per il rapporto:

   * **[!UICONTROL PDF]**: Specifica che il report verrà scaricato in Adobe PDF, che consente di condividere il report con altri utenti, indipendentemente dal computer in cui il destinatario è in esecuzione.
   * **[!UICONTROL CSV]**: Specifica che il report verrà scaricato in formato  [!DNL .csv] (valori separati da virgole).
   * **[!UICONTROL Excel]**: Specifica che il rapporto verrà scaricato in formato Microsoft Excel, che consente di condividere il rapporto con altri utenti che possono aprirlo in un programma per fogli di calcolo.
   * **[!UICONTROL Word]**: Specifica che il report verrà scaricato in formato Microsoft Word.

   >[!NOTE]
   >
   >Se si utilizza uno dei formati di esportazione non elaborati per scaricare un rapporto e il nome della pagina è vuoto, è probabile che Adobe Analytics non abbia avuto abbastanza tempo per elaborare i dati. Scarica il rapporto in un secondo momento.

## Gestire i rapporti pianificati {#task_C17677C543454FF2B06D10EA5652DFBC}

Informazioni sulla gestione dei rapporti pianificati.

In [!UICONTROL Schedule Reports Manager] puoi modificare ed eliminare consegne ricorrenti di rapporti. Puoi programmare le consegne in modo che i rapporti vengano inviati via e-mail o FTP a un indirizzo specifico. Puoi configurare queste pianificazioni in modo da inviare automaticamente i rapporti a intervalli specifici per una durata di tempo o indefinita oppure interrompere la consegna di un rapporto ricorrente.

Il [!UICONTROL Schedule Report Manager] mostra gli elementi creati da un utente specifico. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte.

1. Per accedere al manager, fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Scheduled Reports]**.

## Condividi un collegamento a un rapporto {#task_9711DDE9E140451B8C914EC5513E21EC}

Passaggi che descrivono come condividere un rapporto generando un collegamento a un rapporto (URL) da inviare a un altro utente.

Quando il destinatario fa clic sul collegamento, il sistema richiede le credenziali di accesso (nome società, nome utente e password). Dopo l’accesso, al destinatario viene mostrato il rapporto generato dall’utente originale. Si applicano restrizioni standard alle autorizzazioni.

**Per condividere un collegamento a un rapporto**

1. Esegui un report.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Link to This Report]**.

## Annulla l’iscrizione ai rapporti pianificati {#concept_6B48360F935740B6851BA85D32DEF637}

Puoi annullare l’iscrizione ai rapporti pianificati. Il rapporto non verrà più ricevuto anche se il nome utente viene aggiunto nuovamente al rapporto pianificato.

>[!IMPORTANT]
>
>Per ricevere nuovamente il rapporto, è necessario creare una nuova pianificazione.

Per annullare l’iscrizione a un rapporto pianificato:

1. Visualizza l’e-mail con il collegamento al rapporto di cui desideri annullare l’iscrizione.

   ![](assets/unsubscribe-email.png)

1. Fai clic sul collegamento **[!UICONTROL click here]** accanto a **[!UICONTROL To cancel automatic delivery of this report]**.

1. Conferma l’annullamento della consegna del rapporto.

   >[!NOTE]
   >
   >Questo flusso di lavoro è lo stesso sia che tu sia l’utilità di pianificazione dei report o il destinatario del report.

L’annullamento dell’abbonamento a un rapporto non annulla il rapporto pianificato.

Per annullare un rapporto pianificato, passare a Gestione pianificazione e fare clic sulla X rossa accanto al nome del rapporto. [Altro...](/help/analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
