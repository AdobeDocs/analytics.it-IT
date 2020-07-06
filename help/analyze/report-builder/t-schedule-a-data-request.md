---
description: Potete pianificare l’invio dei rapporti in base all’ora e al formato definiti.
title: Pianificazione di una richiesta di dati
topic: Report builder
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 3%

---


# Pianificare i libri di lavoro

È possibile pianificare le cartelle di lavoro, specificare le opzioni di consegna avanzate, specificare i destinatari e visualizzare la cronologia delle pianificazioni. Le opzioni di consegna avanzate consentono di configurare le cartelle di lavoro che si desidera inviare in un momento specifico o a intervalli. È inoltre possibile specificare il formato di file in cui inviare la cartella di lavoro.

Ad esempio, è possibile pianificare l&#39;invio immediato delle cartelle di lavoro o in base a una pianificazione periodica, specificando il formato del file in [!DNL Advanced Delivery Options]. La dimensione massima del file è 5 MB per il caricamento di una cartella di lavoro.

Inoltre, dopo aver creato una pianificazione della cartella di lavoro in Generatore di report, puoi visualizzare e modificare la pianificazione in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**. (vedere Pianificazione e distribuzione [dei](/help/analyze/reports-analytics/scheduling.md) rapporti nella guida di Reporting e  Analytics).

>[!NOTE]
>
>Per pianificare una cartella di lavoro è necessario disporre di Excel 2007 o del pacchetto di compatibilità installato. È possibile disporre di un massimo di 10 cartelle di lavoro pianificate per ogni licenza Generatore di report. Tuttavia, potete aumentare questo numero sottraendo altre licenze. Per farlo, accedete a **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]** > **[!UICONTROL Report Builder Reports]**. Viene eliminata una cartella di lavoro pianificata (o caricata nella libreria della cartella di lavoro) che non è stata toccata (aggiornata, sostituita) in più di 28 mesi.

>[!NOTE]
>
>Il valore &quot;Tempo di consegna&quot;/&quot;Ora del giorno&quot; immesso dall&#39;utente specifica l&#39;ora in cui la cartella di lavoro deve iniziare l&#39;elaborazione, non l&#39;ora in cui verrà effettivamente consegnata. Il tempo effettivo per la consegna della cartella di lavoro dipende principalmente dal tempo necessario per l&#39;elaborazione (l&#39;elaborazione di cartelle di lavoro complesse e di grandi dimensioni richiede più tempo rispetto a quelle più semplici). Ad esempio, se l&#39;elaborazione di una cartella di lavoro richiede 15 minuti, il tempo di consegna effettivo sarà di almeno 15 minuti oltre il &quot;Tempo di consegna&quot;/&quot;Ora del giorno&quot; specificato originariamente.
>Inoltre, esistono altri fattori che possono aumentare ulteriormente il ritardo prima della consegna effettiva della cartella di lavoro:
>
> * **L&#39;esecuzione simultanea** di molte pianificazioni diverse dello stesso tipo può sovraccaricare il sistema. Il sistema di programmazione consente solo l&#39;esecuzione simultanea di alcune (5-10) cartelle di lavoro di qualsiasi tipo, pertanto, quando più di 5-10 sono tutte pianificate contemporaneamente, alcuni dovranno attendere la fine di altre cartelle di lavoro prima di poter iniziare l&#39;elaborazione. Questo problema può essere attenuato pianificando i libri di lavoro di un&#39;azienda in orari scaglionati per tutto il giorno o l&#39;ora, anziché simultaneamente.
> * A parte il tipo di cartella di lavoro specifico, le cartelle di lavoro attendono anche in linea se la società ha **più di 15-20 tipi di cartella di lavoro programmati contemporaneamente (tra tutti i tipi di cartella di lavoro diversi)**. Questo può essere attenuato dai tempi di programmazione sbalorditivi invece di avere molti di essi in esecuzione allo stesso momento.
> * **I problemi relativi ai servizi** a valle su cui si basa il modulo di pianificazione possono anche influire sulla consegna delle cartelle di lavoro. Ad esempio, se si utilizzano le API in modo indipendente per eseguire le cartelle di lavoro e compilare la coda di richieste API, le cartelle di lavoro pianificate potrebbero essere distribuite lentamente mentre si è in competizione per tale risorsa.
> * **La latenza** della suite di rapporti (un ritardo nella raccolta dei dati) può anche ritardare alcune cartelle di lavoro pianificate.


## Pianificare una cartella di lavoro

1. Generare e salvare una cartella di lavoro.
1. Nella barra degli strumenti del Generatore di report, fai clic su **[!UICONTROL Schedule]**.

   La [!UICONTROL Scheduled Reports] scheda riepiloga tutte le attività create e il numero di attività rimanenti.
1. Nella scheda **[!UICONTROL Scheduled Reports]** fai clic su **[!UICONTROL New]**.
1. Viene visualizzata la Procedura guidata di pianificazione di base:

   ![](assets/simple-schedule-wizard.png)

1. In [!UICONTROL Basic Scheduling Wizard], configurate le seguenti opzioni:

| Campo | Descrizione |
|--- |--- |
| Seleziona Rapporto | Nome della cartella di lavoro. Per i nuovi rapporti pianificati, questo campo viene popolato con il nome attivo della cartella di lavoro. |
| Select | Visualizza la pagina Seleziona rapporto. È possibile selezionare un rapporto dal server (in cui sono memorizzate tutte le cartelle di lavoro pianificate in precedenza) o dal computer locale. Se si seleziona una cartella di lavoro dall&#39;unità locale in formato .xls, il file viene convertito in .xlsx dal sistema. Come parte di tale conversione, il file viene aperto in Excel e reso attivo. Se la cartella di lavoro selezionata per il rapporto pianificato ha lo stesso nome file della cartella di lavoro attualmente aperta in Excel, il sistema seleziona il file locale invece del file caricato in precedenza. Se si seleziona un rapporto dall&#39;archivio di programmazione, viene creata una copia della cartella di lavoro sul server, con il nome file aggiornato con 1. Il nuovo report pianificato creato utilizza la cartella di lavoro copiata. |
| Personalizza | Consente di personalizzare il formato della data. |
| A | Visualizza la Rubrica di Outlook, se applicabile. |
| Invia a: E-mail | Destinatario e-mail della cartella di lavoro. |
| Invia a: Elenco di pubblicazione | Visualizza un elenco di elenchi di distribuzione disponibili per la società. |
| Power BI | Per ulteriori informazioni, vedere [Pubblica cartella di lavoro in Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md) . |
| Oggetto | Una descrizione definita dall&#39;utente. |
| Pianificazione | Consente di specificare quando inviare la cartella di lavoro. (Immediatamente, ogni ora, giorno, settimana, mese e anno). |

## Opzioni di consegna avanzate

1. Fate clic **[!UICONTROL Advanced Delivery Options]** per configurare il file e le opzioni di pubblicazione:

| Campo | Descrizione |
|--- |--- |
| **Scheda Pianificazione** |  |
| Tempo di consegna | Consente di pianificare la cartella di lavoro immediatamente o per un momento successivo. L&#39;ora del giorno è relativa al fuso orario specificato nel computer. |
| Pattern di ricorrenza | Invia la cartella di lavoro in base alle selezioni effettuate. |
| Intervallo di ricorrenza | Consente di specificare quando avviare e interrompere la ricezione della cartella di lavoro.   Nota:  La pianificazione di una cartella di lavoro il primo giorno di un periodo corrente (settimana, mese, trimestre o anno) restituisce i dati solo per il primo giorno. |
| **Opzioni file, scheda** |  |
| Formato file | Consente di selezionare un formato di consegna di Excel 2007 ( .xlsx) o 2003 ( .xls), .pdf, .csv, .mht, .txt e .xml. |
| Destinazione file | Specifica E-mail o FTP. Le opzioni sulla pagina cambiano a seconda della selezione. Per l&#39;FTP, dovrai accertarti che l&#39;host sia disponibile all&#39;esterno. |
| Elenco di pubblicazione | Se si invia la cartella di lavoro pianificata a più elenchi di pubblicazione, la cartella di lavoro verrà eseguita una volta per ciascun elenco. Le suite per report variabili vengono sostituite dalla suite per report assegnata all&#39;elenco di pubblicazione. |
| Lingua contenuto file | Specifica la lingua da utilizzare per la lettera di copertina. Potete selezionare Cinese (semplificato o Tradizionale), Tedesco, Francese, Giapponese, Coreano, Portoghese brasiliano o Spagnolo. |
| **Opzioni di pubblicazione, scheda** |  |
| Pubblicazione in Power BI | <ul><li>Pubblica cartella di lavoro in Power BI</li><li>Pubblica tutte le richieste del Generatore di report come set di dati Power BI</li><li>Pubblica tutte le tabelle formattate come set di dati Power BI</li></ul> |
| Etichetta il report Power BI come | Etichettatura |

1. Fai clic su **[!UICONTROL OK]**, quindi su **[!UICONTROL Exit]**.

   Generatore di report visualizza la cartella di lavoro pianificata in Task Manager [pianificato](/help/analyze/report-builder/r-arb-scheduled-reports.md).

