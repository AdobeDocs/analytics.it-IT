---
description: Scopri le descrizioni dei campi per Gestione attività pianificata.
title: Informazioni su Gestione attività pianificata
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 21%

---

# Attività programmate Manager

Il [!UICONTROL Scheduled Task Manager] consente di visualizzare un elenco dei rapporti pianificati esistenti, con i relativi destinatari, i dettagli della pianificazione e i formati di file. Consente inoltre di riattivare le cartelle di lavoro pianificate che non sono state eseguite.

## Sospensione delle attività pianificate meno recenti

Il 21 aprile 2022 sono state implementate modifiche alle attività pianificate in Report Builder nell’ambito delle attività di ottimizzazione delle prestazioni e della consegna. Tali modifiche includevano la rimozione della possibilità che le consegne pianificate avessero “termine dopo x occorrenze”. In risposta a diverse richieste dei clienti che necessitano di più tempo per esplorare e implementare alternative, abbiamo deciso di ripristinare questa opzione in modo limitato fino al **31 gennaio 2023**.

Continuerai a pianificare attività orarie di Report Builder e a farle terminare dopo un massimo di 99 occorrenze. Si prega di notare che il ripristino della funzione si applica solo alle attività orarie; il “termine dopo x occorrenze” rimarrà non disponibile per tutti gli altri intervalli di consegna (giornalieri, settimanali, mensili e annuali).

Tieni presente che questa opzione diventerà obsoleta il 31 gennaio 2023.
Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe.

In particolare, questa pausa si applica a **tutte le attività create prima del 31 gennaio 2020**. Non verranno eliminate attività, cartelle di lavoro o dati. Le attività più vecchie di due anni verranno sospese e non verranno inviate altre attività pianificate.

Tutte le attività che desideri riprendere l’invio possono essere riattivate. Accedi al Report Builder e avvia la [!UICONTROL Scheduled Task Manager]. Clic **[!UICONTROL Reactivate]** per l’attività pianificata che desideri riprendere l’invio. Le attività riattivate avranno una scadenza predefinita di 18 mesi, a meno che non venga scelta una data di scadenza più breve.

Inoltre, qualsiasi attività con una data di creazione inferiore a due anni e senza data di scadenza corrente (o con una data di scadenza superiore a due anni) avrà una data di scadenza predefinita di 18 mesi. La nuova data di scadenza sarà il 15 ottobre 2023. Puoi modificare questa data di scadenza, purché la nuova scadenza sia inferiore a 18 mesi. Al momento della scadenza, l’attività verrà sospesa. È tuttavia possibile riattivare l&#39;attività con una nuova data di scadenza di 18 mesi. Non verranno eliminate attività, cartelle di lavoro o dati.

Lo scopo di questa pausa è gestire e gestire in modo efficace il database delle attività pianificate per garantire prestazioni e consegna ottimali per le attività e le cartelle di lavoro necessarie. D’ora in avanti, verranno applicati i seguenti nuovi criteri di governance. Dopo il 31 gennaio 2023, tutte le attività avranno una scadenza massima di 18 mesi. Dopo 18 mesi, le attività scadute verranno sospese e potranno essere riattivate in base alle esigenze.

## Configurare le attività pianificate

| Campo | Descrizione |
| --- | --- |
| **[!UICONTROL Scheduled Reports tab]** | |
| [!UICONTROL Report Name] | Indica il nome dell&#39;attività pianificata. |
| [!UICONTROL Email/FTP] | L’indirizzo e-mail o FTP del destinatario. **Nota:** Se selezioni l’opzione e-mail, i rapporti di dimensioni superiori a 1 MB vengono automaticamente allegati all’e-mail come file .zip. Questa funzione consente di mantenere le dimensioni del file allegato ridotte e non può essere disabilitata. |
| [!UICONTROL Publishing Options] | Questa colonna elenca i Power BI se uno dei [Power BI opzioni di pubblicazione](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html) è selezionato. |
| [!UICONTROL Schedule] | Tipo di consegna pianificata. |
| [!UICONTROL File Format] | Il formato di consegna del rapporto, ad esempio Excel, PDF, HTML e così via. |
| [!UICONTROL Reactivate] | Quando una cartella di lavoro pianificata non viene eseguita correttamente, il Report Builder tenta di eseguirla altre due volte ogni quindici minuti. Dopo tre tentativi falliti, il Report Builder disattiva la pianificazione e visualizza il pulsante Riattiva. Quando riattivi una cartella di lavoro, la consegna pianificata viene riavviata dal momento in cui è stata disattivata.<p>Ad esempio, se una cartella di lavoro pianificata è stata disattivata 14 giorni fa e viene riattivata oggi, viene eseguita per ogni giorno mancante e verrà consegnata 14 volte. Se non si desidera che la cartella di lavoro venga consegnata per i giorni mancanti, è possibile eliminare la cartella di lavoro pianificata e quindi crearne una nuova utilizzando gli stessi parametri di pianificazione.<p>**Nota:** Non riattivare una cartella di lavoro se non si conosce il motivo per cui è stata disattivata dal sistema. Per risolvere i problemi, scaricare una cartella di lavoro disattivata e aggiornarla sul lato client. Se non vengono visualizzati errori, dovrebbe essere possibile riattivarli. |
| [!UICONTROL Last sent] | La data e l’ora dell’ultimo invio del rapporto. |
| **Scheda Destinatario** | |
| [!UICONTROL Recipient email] | Il destinatario e-mail del rapporto. |
| [!UICONTROL Reports] | I rapporti inviati a ciascun destinatario. |
| **Scheda Cronologia rapporti** | |
| [!UICONTROL File Name] | Indica il nome dell&#39;attività pianificata. |
| [!UICONTROL Date] | La data e l’ora dell’ultimo invio del rapporto. |
| [!UICONTROL Status] | Lo stato indica se il report è stato inviato o meno. |
| [!UICONTROL Email/FTP] | L’indirizzo e-mail o FTP del destinatario del rapporto. |
| [!UICONTROL File Format] | Il formato di consegna del rapporto, ad esempio Excel, PDF, HTML e così via. |
