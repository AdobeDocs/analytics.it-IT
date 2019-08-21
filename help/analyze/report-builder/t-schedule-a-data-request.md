---
description: Potete pianificare i rapporti in base all'ora e al formato di file definiti.
seo-description: Potete pianificare i rapporti in base all'ora e al formato di file definiti.
seo-title: Pianificazione di una richiesta dati
solution: Analytics
title: Pianificazione di una richiesta dati
topic: Generatore di report
uuid: f 6 d 8 c 90 f-e 185-4 d 60-8035-f 20 f 74 bfcd 89
translation-type: tm+mt
source-git-commit: ed8cfa41a2495c884f1096ea54624820bf3a9e07

---


# Pianificare le cartelle di lavoro

Potete pianificare le cartelle di lavoro, specificare opzioni di consegna avanzate, specificare i destinatari e visualizzare la cronologia delle pianificazioni. Le opzioni di consegna avanzate consentono di configurare i documenti di lavoro che si desidera inviare a un determinato momento o a intervalli specifici. Potete anche specificare il formato di file in cui inviare la cartella di lavoro.

Ad esempio, potete pianificare la pubblicazione di cartelle di lavoro immediatamente o secondo una pianificazione periodica e specificare il formato di file in [!DNL Advanced Delivery Options]. Il limite di dimensione file è 5 MB per il caricamento di una cartella di lavoro.

Inoltre, dopo aver creato una pianificazione di cartelle di lavoro in Generatore di report, potete visualizzare e modificare la pianificazione in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**. (consultate [Pianificazione dei report e distribuzione](/help/analyze/reports-analytics/scheduling.md) nell'Aiuto di Reporting e analisi.)

>[!NOTE]
>
>Per pianificare una cartella di lavoro, è necessario installare Excel 2007 o il pacchetto di compatibilità installato. Potete disporre di un massimo di 10 cartelle di lavoro pianificate per Licenza Generatore di report. Tuttavia, potete aumentare questo numero sottraendo da altre licenze. A questo scopo, accedete **[!UICONTROL Admin]** a &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Report Builder Reports]**. Una cartella di lavoro che è stata pianificata (o caricata nella Libreria di Workcartelle) e non è stata toccata (aggiornata, sostituita) in più di 28 mesi verrà eliminata.

>[!NOTE]
>
>Il «Tempo di consegna»/«Ora del giorno» immesso dall'utente specifica l'ora in cui la cartella di lavoro deve iniziare elaborazione, non l'ora in cui verrà effettivamente consegnata. La data e l'ora effettive in cui la cartella di lavoro verrà distribuita dipende principalmente dal tempo necessario per l'elaborazione (i documenti di lavoro complessi e di grandi dimensioni richiedono più tempo rispetto alle cartelle di lavoro più semplici). Ad esempio, se una cartella di lavoro impiega 15 minuti da elaborare, il tempo di consegna effettivo sarà almeno 15 minuti oltre il «Tempo di consegna»/«Ora del giorno» specificato originariamente.
>Inoltre, esistono molti altri fattori che possono aumentare ulteriormente il ritardo prima della distribuzione della cartella di lavoro:
>
> * **L'esecuzione contemporanea di numerose pianificazioni dello stesso tipo** può sovraccaricare il sistema. Il sistema Pianificazione consente solo alcuni (5-10) cartelle di lavoro di qualsiasi tipo da eseguire simultaneamente; pertanto, quando tutte le versioni di un determinato tipo sono pianificate contemporaneamente, alcuni dovranno attendere in linea per il termine di altri documenti di lavoro prima di iniziare l'elaborazione. Questo problema può essere mitigato pianificando le cartelle di lavoro della società in tempi rapidizzati durante il giorno o l'ora, anziché simultaneamente.
> * A parte il tipo di cartella di lavoro, le cartelle di lavoro saranno anche in linea se l'azienda ha **più di 15-20 di qualsiasi tipo di cartella di lavoro pianificata contemporaneamente (per tutti i tipi di cartelle)**. Questa operazione può essere mitigata rendendo difficoltosa la pianificazione temporale, evitando che venga eseguita contemporaneamente.
> * **I problemi nei servizi** a valle richiesti dal programma di pianificazione possono influire anche sulla distribuzione delle cartelle di lavoro. Ad esempio, se utilizzate indipendentemente le API per eseguire le cartelle di lavoro e compilare la coda delle richieste API, i vostri documenti di lavoro pianificati potrebbero venire distribuiti lentamente mentre siete competitivi per quella risorsa.
> * **La latenza della suite di rapporti** (un ritardo nella raccolta dati) può anche ritardare alcune cartelle di lavoro pianificate.


## Pianificare una cartella di lavoro

1. Generate e salvate una cartella di lavoro.
1. Nella barra degli strumenti di Generatore di report, fate clic **[!UICONTROL Schedule]** su.

   [!UICONTROL Scheduled Reports] La scheda riepiloga tutte le attività create, oltre al numero di operazioni rimanenti.
1. Nella **[!UICONTROL Scheduled Reports]** scheda, fate clic **[!UICONTROL New]** su.
1. Viene visualizzata la procedura guidata di base della pianificazione:

   ![](assets/simple-schedule-wizard.png)

1. In [!UICONTROL Basic Scheduling Wizard], configurate le seguenti opzioni:

| Campo | Descrizione |
|--- |--- |
| Seleziona Rapporto | Nome della cartella di lavoro. Per i nuovi rapporti pianificati, questo campo viene compilato con il nome del cartella di lavoro attivo. |
| Seleziona | Visualizza la pagina Seleziona rapporto. Potete selezionare un rapporto dal server (dove vengono archiviate tutte le cartelle di lavoro precedentemente pianificate) o dal computer locale. Se selezionate una cartella di lavoro dall'unità locale in formato. xls, il file converte il file in. xlsx. Come parte di tale conversione, il file viene aperto in Excel e reso attivo. Se la cartella di lavoro selezionata per il rapporto pianificata ha lo stesso nome file della cartella di lavoro attualmente aperta in Excel, il sistema seleziona il file locale anziché quello caricato in precedenza. Se selezionate un rapporto dall'archivio di pianificazione, viene creata una copia della cartella di lavoro sul server, con il nome file aggiornato con 1. Il rapporto appena creato utilizza la cartella di lavoro copiata. |
| Personalizza | Consente di personalizzare il formato della data. |
| A | Se applicabile, visualizza la rubrica di Outlook. |
| Invia a: E-mail | Destinatario e-mail della cartella di lavoro. |
| Invia a: Elenco pubblicazione | Visualizza un elenco degli elenchi di distribuzione disponibili per questa società. |
| Power BI | Per ulteriori informazioni, consultate [Pubblicare la cartella di lavoro su Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md) . |
| Oggetto | Descrizione definita dall'utente. |
| Pianificazione | Consente di specificare quando inviare la cartella di lavoro. (immediatamente, su base giornaliera, giornaliera, settimanale, mensile e annuale). |

## Opzioni di consegna avanzate

1. Fate clic per **[!UICONTROL Advanced Delivery Options]** configurare i file e le opzioni di pubblicazione:

| Campo | Descrizione |
|--- |--- |
| **Scheda Pianificazione** |  |
| Ora di consegna | Consente di pianificare la cartella di lavoro immediatamente o per un momento successivo. L'ora del giorno è relativa al fuso orario specificato nel computer. |
| Pattern di ricorrenza | Invia la cartella di lavoro in base alle selezioni. |
| Intervallo di ricorrenza | Consente di specificare quando avviare e interrompere la ricezione della cartella di lavoro. Nota: La pianificazione di una cartella di lavoro il primo giorno di qualsiasi periodo (settimana, mese, trimestre o anno) restituisce dati solo per il primo giorno. |
| **scheda Opzioni file** |  |
| Formato file | Consente di selezionare un formato di consegna Excel 2007 (.xlsx) o 2003 (. xls).pdf. csv. mht.txt e. xml. |
| Destinazione file | Specifica e-mail o FTP. Le opzioni della pagina variano a seconda della selezione. Per l'FTP, dovrai accertarti che l'host sia disponibile all'esterno. |
| Elenco pubblicazione | Se inviate la cartella di lavoro pianificata a più elenchi di pubblicazione, la cartella di lavoro viene eseguita una volta per ogni elenco. Le suite di rapporti variabili vengono sostituite dalla suite di rapporti assegnata all'elenco di pubblicazione. |
| Lingua contenuto file | Specifica la lingua da utilizzare per la lettera di copertina. È possibile selezionare Cinese (Semplificato o Tradizionale), Tedesco, Francese, Giapponese, Coreano, Portoghese o Spagnolo. |
| **scheda Opzioni pubblicazione** |  |
| Pubblicazione su Power BI | <ul><li>Pubblicare la cartella di lavoro su Power BI</li><li>Pubblica tutte le richieste di Generatore di report come datasets Power BI</li><li>Pubblica tutte le tabelle formattate come datasets Power BI</li></ul> |
| Etichettate questo report Power BI come | Dettagli etichettatura |

1. Fate clic **[!UICONTROL OK]** su, quindi fate clic **[!UICONTROL Exit]** su.

   Generatore di report visualizza la cartella di lavoro pianificata in Task Manager [pianificata](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31).

