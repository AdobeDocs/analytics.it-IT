---
description: Puoi pianificare l’invio dei rapporti in base all’ora e al formato di file definiti.
title: Pianificare una richiesta di dati
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 3%

---


# Pianificare cartelle di lavoro

È possibile pianificare le cartelle di lavoro, specificare le opzioni di consegna avanzate, specificare i destinatari e visualizzare la cronologia della pianificazione. Le opzioni di consegna avanzate consentono di configurare le cartelle di lavoro che si desidera inviare in un momento specifico o a intervalli specifici. È inoltre possibile specificare il formato del file in cui inviare la cartella di lavoro.

Ad esempio, è possibile pianificare la consegna immediata delle cartelle di lavoro o in base a una pianificazione periodica e specificare il formato del file in [!DNL Advanced Delivery Options]. Il limite di dimensione del file è di 5 MB per il caricamento di una cartella di lavoro.

Inoltre, dopo aver creato una pianificazione della cartella di lavoro in Report Builder, è possibile visualizzare e modificare la pianificazione in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**. (Consulta [Pianificazione e distribuzione dei rapporti](/help/analyze/reports-analytics/scheduling.md) nella guida di Reports &amp; Analytics.)

>[!NOTE]
>
>Per pianificare una cartella di lavoro è necessario che sia installato Excel 2007 o il pacchetto di compatibilità. È possibile disporre di un massimo di 10 cartelle di lavoro pianificate per licenza al Report Builder. Tuttavia, è possibile aumentare questo numero sottraendo da altre licenze. Per farlo, vai su **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]** > **[!UICONTROL Report Builder Reports]**. Verrà eliminata una cartella di lavoro pianificata (o caricata nella libreria della cartella di lavoro) che non è stata toccata (aggiornata, sostituita) in più di 28 mesi.

>[!NOTE]
>
>Il valore &quot;Ora di consegna&quot;/&quot;Ora del giorno&quot; immesso dall&#39;utente specifica l&#39;ora in cui la cartella di lavoro deve iniziare l&#39;elaborazione, non l&#39;ora in cui verrà effettivamente consegnata. Il tempo effettivo per la consegna della cartella di lavoro dipende principalmente dal tempo necessario per l&#39;elaborazione (l&#39;elaborazione di cartelle di lavoro complesse e di grandi dimensioni richiede più tempo rispetto a quelle più semplici). Ad esempio, se l’elaborazione di una cartella di lavoro richiede 15 minuti, il tempo di consegna effettivo sarà di almeno 15 minuti oltre il tempo di consegna originariamente specificato, &quot;Ora di consegna&quot;/&quot;Ora del giorno&quot;.
>Inoltre, ci sono diversi altri fattori che possono aumentare ulteriormente il ritardo prima che la cartella di lavoro venga effettivamente consegnata:
>
> * **L&#39;esecuzione di molte pianificazioni diverse dello stesso tipo nello stesso** momento può sovraccaricare il sistema. Il sistema di programmazione consente solo l&#39;esecuzione simultanea di alcune cartelle di lavoro (5-10) di un tipo qualsiasi, quindi quando più di 5-10 sono tutti programmati contemporaneamente, alcuni dovranno attendere il completamento di altre cartelle di lavoro prima che possano iniziare l&#39;elaborazione. Questo problema può essere attenuato pianificando le cartelle di lavoro di un&#39;azienda in orari scaglionati per tutto il giorno o l&#39;ora, anziché simultaneamente.
> * Oltre al tipo di cartella di lavoro specifico, le cartelle di lavoro attendono anche in linea se l&#39;azienda ha **più di 15-20 di qualsiasi tipo di cartella di lavoro pianificato contemporaneamente (in tutti i diversi tipi di cartella di lavoro)**. Questo può essere attenuato dai tempi di pianificazione sbalorditivi invece di averne molti eseguiti contemporaneamente.
> * **I problemi relativi ai** servizi a valle su cui si basa lo strumento di pianificazione possono influire anche sulla consegna delle cartelle di lavoro. Ad esempio, se utilizzi in modo indipendente le API per eseguire le cartelle di lavoro e compilare la coda di richiesta API, le cartelle di lavoro pianificate potrebbero essere distribuite lentamente mentre ti trovi in competizione per tale risorsa.
> * **La latenza della suite di rapporti**  (un ritardo nella raccolta dei dati) può anche ritardare alcune cartelle di lavoro pianificate.


## Pianificare una cartella di lavoro

1. Generare e salvare una cartella di lavoro.
1. Sulla barra degli strumenti del Report Builder, fai clic su **[!UICONTROL Schedule]**.

   La scheda [!UICONTROL Scheduled Reports] riepiloga tutte le attività create e il numero di attività rimanenti.
1. Nella scheda **[!UICONTROL Scheduled Reports]** fai clic su **[!UICONTROL New]**.
1. Viene visualizzata la Pianificazione guidata di base:

   ![](assets/simple-schedule-wizard.png)

1. In [!UICONTROL Basic Scheduling Wizard], configura le seguenti opzioni:

| Campo | Descrizione |
|--- |--- |
| Seleziona Rapporto | Nome della cartella di lavoro. Per i nuovi rapporti pianificati, questo campo viene compilato con il nome della cartella di lavoro attiva. |
| Seleziona | Visualizza la pagina Seleziona rapporto . È possibile selezionare un report dal server (in cui sono memorizzate tutte le cartelle di lavoro pianificate in precedenza) o dal computer locale. Se si seleziona una cartella di lavoro dall&#39;unità locale in formato .xls, il sistema converte il file in .xlsx. Come parte di tale conversione, il file viene aperto in Excel e reso attivo. Se la cartella di lavoro selezionata per il report programmato ha lo stesso nome file della cartella di lavoro attualmente aperta in Excel, il sistema seleziona il file locale invece del file caricato in precedenza. Se si seleziona un report dall&#39;archivio di pianificazione, viene creata una copia della cartella di lavoro sul server, con il nome del file aggiornato con 1. Il report pianificato appena creato utilizza la cartella di lavoro copiata. |
| Personalizza | Consente di personalizzare il formato della data. |
| Su | Visualizza la Rubrica di Outlook, se applicabile. |
| Invia a: E-mail | Il destinatario e-mail della cartella di lavoro. |
| Invia a: Elenco di pubblicazione | Visualizza un elenco delle liste di distribuzione disponibili per la società. |
| Power BI | Per ulteriori informazioni, consulta [Pubblica cartella di lavoro in Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md) . |
| Oggetto | Una descrizione definita dall’utente. |
| Pianificazione | Consente di specificare quando inviare la cartella di lavoro. (Immediatamente, oraria, giornaliera, settimanale, mensile e annuale). |

## Opzioni di consegna avanzate

1. Fai clic su **[!UICONTROL Advanced Delivery Options]** per configurare i file e le opzioni di pubblicazione:

| Campo | Descrizione |
|--- |--- |
| **Scheda Pianificazione** |  |
| Tempo di consegna | Consente di pianificare la cartella di lavoro immediatamente o per un momento successivo. L&#39;ora del giorno è relativa al fuso orario specificato nel computer. |
| Pattern di ricorrenza | Invia la cartella di lavoro in base alle selezioni effettuate. |
| Intervallo di ricorrenza | Consente di specificare quando iniziare e interrompere la ricezione della cartella di lavoro.   Nota:  La pianificazione di una cartella di lavoro il primo giorno di qualsiasi periodo corrente (settimana, mese, trimestre o anno) restituisce i dati solo per il primo giorno. |
| **Scheda Opzioni file** |  |
| Formato file | Consente di selezionare un formato di consegna di Excel 2007 ( .xlsx) o 2003 ( .xls), .pdf, .csv, .mht, .txt e .xml. |
| Destinazione file | Specifica e-mail o FTP. Le opzioni della pagina variano a seconda della selezione. Per l&#39;FTP, dovrai accertarti che l&#39;host sia disponibile all&#39;esterno. |
| Elenco di pubblicazione | Se si invia la cartella di lavoro pianificata a più elenchi di pubblicazione, la cartella di lavoro viene eseguita una volta per ogni elenco. Le suite di rapporti variabili vengono sostituite dalla suite di rapporti assegnata all’elenco di pubblicazione. |
| Lingua del contenuto del file | Specifica la lingua da utilizzare per la lettera di presentazione. È possibile selezionare Cinese (semplificato o tradizionale), Tedesco, Francese, Giapponese, Coreano, Portoghese brasiliano o Spagnolo. |
| **Scheda Opzioni di pubblicazione** |  |
| Pubblicazione su Power BI | <ul><li>Pubblica cartella di lavoro in Power BI</li><li>Pubblicare tutte le richieste di Report Builder come set di dati di Power BI</li><li>Pubblicare tutte le tabelle formattate come set di dati Power BI</li></ul> |
| Etichettare questo Power BI come | Dettagli di etichettatura |

1. Fai clic su **[!UICONTROL OK]**, quindi su **[!UICONTROL Exit]**.

   Il Report Builder visualizza la cartella di lavoro pianificata in [Gestione attività pianificata](/help/analyze/report-builder/r-arb-scheduled-reports.md).

