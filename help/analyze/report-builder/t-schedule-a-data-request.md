---
description: Scopri come pianificare i rapporti.
title: Come pianificare una richiesta di dati
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
feature: Report Builder
role: User, Admin
exl-id: 6aaadaa8-d68f-4a03-8838-53a61b152e31
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 3%

---

# Pianificare le cartelle di lavoro

È possibile pianificare le cartelle di lavoro, specificare opzioni di consegna avanzate, specificare i destinatari e visualizzare la cronologia della pianificazione. Le opzioni di consegna avanzate consentono di configurare le cartelle di lavoro da inviare in un momento specifico o a intervalli. È inoltre possibile specificare il formato di file in cui inviare la cartella di lavoro.

È ad esempio possibile pianificare la consegna delle cartelle di lavoro immediatamente o in base a una pianificazione periodica e specificare il formato di file in [!DNL Advanced Delivery Options]. La dimensione massima del file è di 5 MB per il caricamento di una cartella di lavoro.

Inoltre, dopo aver creato una pianificazione della cartella di lavoro in Report Builder, è possibile visualizzarla e modificarla in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**. (vedere [Pianificazione e distribuzione del rapporto](/help/analyze/reports-analytics/scheduling.md) nella guida di Reports &amp; Analytics.)

>[!NOTE]
>
>Per pianificare una cartella di lavoro è necessario che sia installato Excel 2007 o il pacchetto di compatibilità. È possibile disporre di un massimo di 10 cartelle di lavoro pianificate per licenza Report Builder. Tuttavia, è possibile aumentare questo numero sottraendo da altre licenze. Per farlo, vai a **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Company settings]** > **[!UICONTROL Report Builder Reports]**. Una cartella di lavoro pianificata (o caricata nella libreria cartelle di lavoro) e che non è stata toccata (aggiornata o sostituita) in più di 28 mesi verrà eliminata.

>[!NOTE]
>
>L&#39;opzione &quot;Orario di consegna&quot;/&quot;Ora del giorno&quot; immessa dall&#39;utente specifica l&#39;ora in cui la cartella di lavoro deve iniziare l&#39;elaborazione, non l&#39;ora in cui verrà effettivamente consegnata. Il tempo effettivo di consegna della cartella di lavoro dipende principalmente dal tempo necessario per l&#39;elaborazione (l&#39;elaborazione di cartelle di lavoro complesse e di grandi dimensioni richiede più tempo rispetto a quelle più semplici). Ad esempio, se l’elaborazione di una cartella di lavoro richiede 15 minuti, il tempo di consegna effettivo sarà di almeno 15 minuti oltre il &quot;Orario di consegna&quot;/&quot;Ora del giorno&quot; originariamente specificato.
>Inoltre, esistono diversi altri fattori che possono aumentare ulteriormente il ritardo prima che la cartella di lavoro venga effettivamente consegnata:
>
> * **Esecuzione simultanea di più pianificazioni diverse dello stesso tipo** può sovraccaricare il sistema. Il sistema di pianificazione consente solo l’esecuzione simultanea di poche (5-10) cartelle di lavoro di qualsiasi tipo; pertanto, quando sono pianificate più di 5-10 cartelle di lavoro alla volta, alcune dovranno attendere il completamento delle altre prima di poter iniziare l’elaborazione. Questo problema può essere attenuato pianificando le cartelle di lavoro di un’azienda in momenti diversi nel corso della giornata o dell’ora, anziché simultaneamente.
> * Oltre al tipo di cartella di lavoro specifico, le cartelle di lavoro attendono in linea anche se l’azienda ha **più di 15-20 di qualsiasi tipo di cartella di lavoro pianificata contemporaneamente (in tutti i diversi tipi di cartella di lavoro)**. Questo problema può essere risolto scaglionando i tempi di pianificazione invece di eseguirne molti contemporaneamente.
> * **Problemi nei servizi a valle** su cui si basa lo scheduler può influire anche sulla consegna delle cartelle di lavoro. Ad esempio, se utilizzi le API in modo indipendente per eseguire le cartelle di lavoro e riempire la coda di richieste API, le cartelle di lavoro pianificate potrebbero consegnarsi lentamente mentre competi per quella risorsa.
> * **Latenza suite di rapporti** (un ritardo nella raccolta dei dati) può anche ritardare alcune cartelle di lavoro pianificate.

## Pianificare una cartella di lavoro

1. Generare e salvare una cartella di lavoro.
1. Sulla barra degli strumenti del Report Builder fare clic su **[!UICONTROL Schedule]**.

   Il [!UICONTROL Scheduled Reports] La scheda riepiloga tutte le attività create e il numero di attività rimanenti.
1. Nella scheda **[!UICONTROL Scheduled Reports]** fai clic su **[!UICONTROL New]**. La Programmazione guidata di base mostra le opzioni utilizzate per definire il rapporto programmato.

   ![Schermata che mostra la Programmazione guidata di base.](assets/simple-schedule-wizard.png)

1. In [!UICONTROL Basic Scheduling Wizard], configura le seguenti opzioni:

| Campo | Descrizione |
|--- |--- |
| Seleziona Rapporto | Nome della cartella di lavoro. Per i nuovi rapporti pianificati, questo campo viene compilato con il nome della cartella di lavoro attiva. |
| Seleziona | Visualizza la pagina Seleziona report. È possibile selezionare un report dal server in cui sono memorizzate tutte le cartelle di lavoro pianificate in precedenza oppure dal computer locale. Se si seleziona una cartella di lavoro dall&#39;unità locale in formato xls, il file verrà convertito in formato xlsx. Come parte di tale conversione, il file viene aperto in Excel e reso attivo. Se la cartella di lavoro selezionata per il report pianificato ha lo stesso nome file della cartella di lavoro attualmente aperta in Excel, il sistema seleziona il file locale invece del file caricato in precedenza. Se si seleziona un report dall&#39;archivio di pianificazione, nel server viene creata una copia della cartella di lavoro con il nome del file aggiornato a 1. Il rapporto pianificato appena creato utilizza la cartella di lavoro copiata. |
| Personalizza | Consente di personalizzare il formato della data. |
| Su | Visualizza la Rubrica di Outlook, se applicabile. |
| Invia a: e-mail | Destinatario e-mail della cartella di lavoro. |
| Invia a: elenco di pubblicazione | Visualizza un elenco delle liste di distribuzione disponibili per la società. |
| Power BI | Consulta [Pubblica cartella di lavoro in Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md) per ulteriori informazioni. |
| Oggetto | Descrizione definita dall&#39;utente. |
| Pianificazione | Consente di specificare quando inviare la cartella di lavoro. (Immediatamente, ogni ora, ogni giorno, ogni settimana, ogni mese e ogni anno). |

## Opzioni di consegna avanzate

1. Clic **[!UICONTROL Advanced Delivery Options]** per configurare le opzioni di file e pubblicazione:

| Campo | Descrizione |
|--- |--- |
| **Scheda Pianificazione** |  |
| Tempi di consegna | Consente di pianificare la cartella di lavoro immediatamente o in un secondo momento. L&#39;ora del giorno è relativa al fuso orario specificato nel computer. |
| Pattern di ricorrenza | Invia la cartella di lavoro in base alle selezioni effettuate. |
| Intervallo di ricorrenza | Consente di specificare quando avviare e interrompere la ricezione della cartella di lavoro.   Nota: la programmazione di una cartella di lavoro nel primo giorno di un periodo corrente (settimana, mese, trimestre o anno) restituisce i dati solo per il primo giorno. |
| **Scheda Opzioni file** |  |
| Formato file | Consente di selezionare un formato di consegna di Excel 2007 ( .xlsx) o 2003 ( .xls), .pdf, .csv, .mht, .txt e .xml. |
| Destinazione file | Specifica e-mail o FTP. Le opzioni nella pagina cambiano a seconda della selezione. Per l&#39;FTP, dovrai accertarti che l&#39;host sia disponibile all&#39;esterno. |
| Lingua contenuto file | Specifica la lingua da utilizzare per la lettera di accompagnamento. È possibile selezionare Cinese (semplificato o tradizionale), Tedesco, Francese, Giapponese, Coreano, Portoghese brasiliano o Spagnolo. |
| **Scheda Opzioni di pubblicazione** |  |
| Pubblicazione su Power BI | <ul><li>Pubblica cartella di lavoro in Power BI</li><li>Pubblica tutte le richieste di Report Builder come set di dati di Power BI</li><li>Pubblicare tutte le tabelle formattate come set di dati Power BI</li></ul> |
| Etichetta report Power BI come | Dettagli di etichettatura |

1. Fai clic su **[!UICONTROL OK]**, quindi su **[!UICONTROL Exit]**.

   Il Report Builder visualizza la cartella di lavoro pianificata nel [Gestione attività pianificata](/help/analyze/report-builder/r-arb-scheduled-reports.md).
