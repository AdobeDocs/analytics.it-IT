---
description: Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.
subtopic: Schedule
title: Pianificazione e distribuzione del rapporto
topic: Reports and analytics
uuid: 1230b0f3-e026-4b83-b231-14d6f75a3836
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1620'
ht-degree: 5%

---


# Pianificazione e distribuzione del rapporto

Informazioni sulla pianificazione, il download e la distribuzione dei rapporti.

Quando pianifichi la consegna di un report in un&#39;applicazione di Adobe Analytics puoi utilizzare gli strumenti Scheduling (Pianificazione) e Distribution (Distribuzione) per visualizzare i file automaticamente inviati e modificati o per terminare le consegne.

A causa delle differenze nei meccanismi di elaborazione e nelle piattaforme, i vari tipi di rapporti scaricabili e pianificati disponibili in Adobe  Analytics presentano limitazioni diverse per quanto riguarda il numero massimo di righe che possono elaborare in una singola richiesta. Di seguito sono riportati i limiti di ciascuna:

* Word, CSV, Excel, HTML e PDF: Lo stesso numero di righe visibili nel report. Per impostazione predefinita, questo limite è di 50 righe ma può aumentare fino a 200. I rapporti di suddivisione hanno un limite rigido di 50 righe.
* Estratti dati: 50.000 righe
* Data warehouse: Senza limiti

Tali limitazioni riguardano i singoli rapporti pianificati e scaricati; le dashboard sono limitate alla quantità di spazio disponibile all&#39;interno di un reportlet.

>[!NOTE]
>
>Il valore &quot;Ora consegna&quot;/&quot;Ora del giorno&quot; immesso dall&#39;utente specifica l&#39;ora in cui il rapporto deve iniziare l&#39;elaborazione, non l&#39;ora in cui verrà effettivamente consegnato. Il tempo effettivo per la presentazione della relazione dipende in primo luogo dal tempo necessario per l&#39;elaborazione (l&#39;elaborazione di relazioni complesse e di grandi dimensioni richiede più tempo rispetto a quella di relazioni più semplici). Ad esempio, se l&#39;elaborazione di un rapporto richiede 15 minuti, il tempo di consegna effettivo sarà di almeno 15 minuti oltre il &quot;Tempo di consegna&quot;/&quot;Ora del giorno&quot; originariamente specificato.
>Inoltre, vi sono altri fattori che possono aumentare ulteriormente il ritardo prima che la relazione sia effettivamente pubblicata:
>
> * **Esecuzione contemporanea** di diversi programmi dello stesso tipo (ad esempio, molti dashboard, ecc.) può sovraccaricare il sistema. Il sistema di programmazione consente solo l&#39;esecuzione simultanea di alcuni (5-10) rapporti di un tipo, pertanto, quando più di 5-10 sono tutti programmati contemporaneamente, alcuni dovranno attendere il completamento di altri rapporti prima di poter iniziare l&#39;elaborazione. Questo problema può essere attenuato pianificando i report di un&#39;azienda in orari scaglionati per tutto il giorno o l&#39;ora, anziché simultaneamente.
> * A parte il tipo di rapporto specifico (dashboard, ecc.), i report saranno in linea anche se la società ha **più di 15-20 di qualsiasi tipo di rapporto pianificato contemporaneamente (tra tutti i diversi tipi di rapporto)**. Questo può essere attenuato dai tempi di programmazione sbalorditivi invece di avere molti di essi in esecuzione allo stesso momento.
> * **I problemi relativi ai servizi** a valle su cui si basa l&#39;Utilità di pianificazione possono anche influenzare la consegna dei report. Ad esempio, se utilizzate in modo indipendente le API per eseguire i report e completare la coda di richieste API, i report pianificati potrebbero essere distribuiti lentamente mentre siete in competizione per quella risorsa.
> * **La latenza** della suite di rapporti (un ritardo nella raccolta dei dati) può anche ritardare alcuni rapporti pianificati.



## Inviare un rapporto {#task_27642CD33D484FD0BF59EBD159EEF52C}

Passaggi che descrivono come scaricare e inviare i rapporti per e-mail in vari formati e pianificare la consegna di un rapporto.

1. Run a report, then click **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Specificate le opzioni di consegna:

   | Opzione | Descrizione |
   |--- |--- |
   | Formato | Selezionate PDF o HTML. |
   | Invia a | Fornite un indirizzo e-mail per ricevere il rapporto. |
   | Oggetto | Oggetto del messaggio e-mail. |
   | Pianificazione | Selezionare questa opzione per inviare il rapporto immediatamente o a un intervallo diverso. |

1. Fate clic **[!UICONTROL Advanced Delivery Options]** per specificare un programma di consegna.

| Opzione | Descrizione |
|--- |--- |
| Nome file report | Specifica il nome del rapporto. The default format is `<report name> for <suite> - <report date range>`. Per specificare un nome personalizzato, selezionare [!UICONTROL Custom]. |
| Formato report | Consente di specificare i formati PDF, CSV, Excel, HTML, Word o Mobile da distribuire. Se selezionate CSV, potete anche specificare la codifica per CSV:<ul><li>Shift-JIS: Codifica caratteri giapponese.</li><li>EUC-JP: Codice Unix esteso, principalmente per giapponese, coreano e cinese semplificato.</li></ul> |
| Sommario report | <ul><li>Numero di righe nella tabella: Specifica il numero di righe che si desidera visualizzare nella tabella del rapporto che si sta inviando.</li><li>Lingua per intestazione e piè di pagina: Specifica la lingua dell’intestazione e del piè di pagina.</li><li>Commenti: Specifica il testo che viene visualizzato all&#39;inizio del rapporto.</li></ul> |
| Invia file firma digitale | Quando richiedi un rapporto, ad esempio un rapporto con segnalibro o richieste di Data warehouse, puoi richiedere una firma dati. La firma digitale di Adobe non limita l&#39;accesso ai dati da parte degli utenti, ma lo scopo del file di firma digitale (.sig) è di verificare la validità del file di rapporto consegnato. Utilizzando la firma digitale, i destinatari del rapporto possono verificare che il file provenga da Adobe e non sia stato modificato. |
| Destinazione report | <ul><li>E-mail: Consente di configurare le impostazioni dell’indirizzo e-mail, l’oggetto e le note.</li><li>FTP: Consente di configurare le impostazioni FTP, inclusi host, porta, directory, nome utente e password.</li></ul> |

1. Fai clic su **[!UICONTROL Scheduling Options]**.

| Opzione | Descrizione |
|--- |--- |
| Invia rapporto ora | Invia il rapporto immediatamente. |
| Pianifica in un secondo momento | Visualizza le opzioni per specificare un intervallo di tempo e le opzioni di consegna. |
| Frame di tempo rapporto | **Problema corretto**: Impedisce l&#39;avanzamento della data al passaggio del tempo. **Rotolamento**: Consente l&#39;avanzamento della data al passaggio dell&#39;ora. Alcune considerazioni:<ul><li>Se selezionate Rolling per le date di inizio e di fine e selezionate un rapporto giornaliero per il giorno precedente, ogni giorno riceverete un messaggio e-mail con un rapporto per il giorno precedente.</li><li>Se selezionate Fisso per il giorno iniziale e continuate per il giorno finale, il primo giorno riceverete un rapporto per il giorno precedente. Il secondo giorno si riceve un rapporto per i due giorni precedenti, il terzo giorno si riceve un rapporto per i tre giorni precedenti e così via.</li><li>Se selezionate Fisso per le date di inizio e di fine, ogni giorno viene visualizzato un rapporto identico per i giorni specificati.</li><li>Non è possibile selezionare una data di inizio continuo e una data di fine fissa.</li></ul> |
| Frequenza di consegna | <ul><li>**Orario**: Invia l’e-mail ogni ora, ogni altra ora o qualsiasi altro intervallo di ore.</li><li>**Giornaliero**: Invia l’e-mail ogni giorno, ogni altro giorno, ogni terzo giorno o qualsiasi altro intervallo di giorni. Potete anche farli inviare ogni giorno feriale.</li><li>**Settimanale**: Invia l’e-mail ogni settimana, altra settimana, ogni tre settimane o qualsiasi altro intervallo di settimane. È inoltre possibile specificare il giorno della settimana in cui viene inviato.</li><li>**Mensile**: Specifica l’intervallo in numero di mesi e puoi anche selezionare il giorno del mese in cui viene inviato, o il giorno della settimana in una settimana specifica del mese.</li><li>**Annuale**: Specifica il giorno dell&#39;anno in cui viene inviato il rapporto, oppure puoi inviarlo in un giorno specifico della settimana in qualsiasi settimana dell&#39;anno.</li><li>**Ora del giorno**: Si applica al fuso orario associato alla suite di rapporti selezionata.</li></ul> |
| Opzioni di consegna finale | <ul><li>**Mai fine**: Non specifica alcuna fine.</li><li>**Fine dopo`value`le occorrenze**: Specifica il numero di occorrenze prima della fine del recapito.</li><li>**Fine data**: Consente di specificare una data specifica. Se si desidera elaborare i dati alla stessa data dei dati del rapporto, il rapporto contiene solo i dati inseriti nel database al momento dell&#39;invio del rapporto. Poiché l&#39;elaborazione completa per un giorno può richiedere fino a 24 ore, i dati completi potrebbero non essere disponibili al momento dell&#39;invio del rapporto. Per i dati completi, imposta sempre il tempo di elaborazione per 24 ore dopo la fine del periodo di reporting.</li></ul> |

## Stampare un rapporto {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Passaggi che descrivono come stampare un rapporto.

1. Esegui un report.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Print]**.  ![](assets/print.png)

## Download a report using basic options {#task_43660107A1C9485D92981CD75B562577}

Scarica informazioni dettagliate su un rapporto specifico nei formati PDF, CSV, Excel o Raw Data Export.

1. In **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** , selezionate un rapporto da visualizzare.
1. Fai clic su **[!UICONTROL Download]**.

   ![](assets/download_basic.png)

1. Selezionate il formato desiderato per il rapporto:

   * **[!UICONTROL PDF]**: Specifica che il rapporto verrà scaricato in Adobe PDF, che consente di condividere il rapporto con altri utenti, indipendentemente dal computer in cui è in esecuzione il destinatario.
   * **[!UICONTROL CSV]**: Specifica che il rapporto verrà scaricato in [!DNL .csv] (formato di valori separati da virgole).
   * **[!UICONTROL Excel]**: Specifica che il rapporto verrà scaricato in formato Microsoft Excel, che consente di condividere il rapporto con altri utenti che possono aprirlo in un programma per fogli di calcolo.
   * **[!UICONTROL Word]**: Specifica che il rapporto verrà scaricato in formato Microsoft Word.
   >[!NOTE]
   >
   >Se utilizzate uno dei formati di esportazione non elaborati per scaricare un rapporto e il nome della pagina è vuoto, Adobe  Analytics probabilmente non ha avuto abbastanza tempo per elaborare i dati. Scaricate il rapporto in un secondo momento.

## Gestire i rapporti pianificati {#task_C17677C543454FF2B06D10EA5652DFBC}

Informazioni sulla gestione dei rapporti pianificati.

In [!UICONTROL Schedule Reports Manager], puoi modificare ed eliminare consegne ricorrenti di rapporti. Puoi programmare le consegne in modo che i rapporti vengano inviati via e-mail o FTP a un indirizzo specifico. Puoi configurare queste pianificazioni per inviare automaticamente i rapporti a intervalli specificati per una durata di tempo o indefinita, oppure per interrompere la consegna di un rapporto periodico.

The [!UICONTROL Schedule Report Manager] shows the items that a specific user has created. Se l’account dell’utente è disabilitato nell’applicazione, tutte le consegne programmate vengono interrotte.

1. Per accedere al manager, fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Scheduled Reports]**.

## Condivisione di un collegamento di rapporto {#task_9711DDE9E140451B8C914EC5513E21EC}

Procedura che descrive come condividere un rapporto generando un collegamento (URL) da inviare a un altro utente.

Quando il destinatario fa clic sul collegamento, il sistema richiede le credenziali di accesso (nome società, nome utente e password). Dopo l’accesso, al destinatario viene mostrato il rapporto generato dall’utente originale. Si applicano le restrizioni di autorizzazione standard.

**Condivisione di un collegamento a un rapporto**

1. Esegui un report.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Link to This Report]**.

## Annullamento dell&#39;iscrizione ai rapporti pianificati {#concept_6B48360F935740B6851BA85D32DEF637}

Potete annullare l’iscrizione ai rapporti pianificati. Non riceverai più il rapporto anche se il tuo nome utente viene aggiunto nuovamente al rapporto pianificato.

>[!IMPORTANT]
>
>Per ricevere nuovamente il rapporto, è necessario creare una nuova pianificazione.

Per annullare l’iscrizione a un rapporto pianificato:

1. Visualizzate l’e-mail con il collegamento al rapporto da cui desiderate annullare l’iscrizione.

   ![](assets/unsubscribe-email.png)

1. Fare clic sul **[!UICONTROL click here]** collegamento accanto a **[!UICONTROL To cancel automatic delivery of this report]**.

1. Conferma di voler annullare la consegna del rapporto.

   >[!NOTE]
   >
   >Questo flusso di lavoro è lo stesso sia che si tratti del pianificatore dei report o del destinatario del report.

L&#39;annullamento della sottoscrizione a un rapporto non annulla il rapporto pianificato.

Per annullare un rapporto pianificato, andate al Gestore pianificazione e fate clic sulla X rossa accanto al nome del rapporto. [Altro...](/help/analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
