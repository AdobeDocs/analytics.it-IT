---
description: Descrizioni dei campi per Gestione attività pianificata.
title: Attività programmate Manager
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
source-git-commit: 9a16f3942505028624e5c07568342a9acac898d7
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 6%

---

# Attività programmate Manager

La [!UICONTROL Scheduled Task Manager] ti consente di visualizzare un elenco dei rapporti pianificati esistenti, nonché dei relativi destinatari, dettagli della pianificazione e formati di file. Consente inoltre di riattivare le cartelle di lavoro pianificate non eseguite.

## Sospensione delle attività pianificate precedenti

Il 21 aprile 2022 sono state implementate modifiche alle attività pianificate in Report Builder nell’ambito delle attività di ottimizzazione delle prestazioni e della consegna. Tali modifiche includevano la rimozione della possibilità di avere consegne pianificate &quot;end after x events&quot; (termine dopo gli eventi x). In risposta a diverse richieste dei clienti che richiedono più tempo per esplorare e implementare alternative, abbiamo deciso di ripristinare questa opzione in modo limitato fino a **31 gennaio 2023**.

Sarà possibile continuare a pianificare le attività al Report Builder orario e farle terminare dopo un massimo di 99 occorrenze. Si prega di notare che lo smantellamento si applica solo alle attività orarie; la &quot;fine dopo x occorrenze&quot; rimarrà non disponibile per tutti gli altri intervalli di consegna (giornalieri, settimanali, mensili e annuali).

Tieni presente che questa opzione diventerà obsoleta il 31 gennaio 2023.
Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe.

In particolare, questa pausa si applica a **eventuali attività create prima del 31 gennaio 2020**. Non verranno eliminate attività, cartelle di lavoro o dati. Le attività con una durata superiore a due anni verranno messe in pausa e non verranno inviate altre attività pianificate.

È possibile riattivare tutte le attività che si desidera riprendere l’invio. Accedi a Report Builder e avvia il [!UICONTROL Scheduled Task Manager]. Fai clic su **[!UICONTROL Reactivate]** per l’attività pianificata da riprendere l’invio. Qualsiasi attività che viene riattivata avrà una scadenza predefinita di 18 mesi, a meno che non venga selezionata una data di scadenza più breve.

Inoltre, per qualsiasi attività con una data di creazione inferiore a due anni e senza data di scadenza corrente (o con una data di scadenza superiore a due anni) verrà applicata una data di scadenza predefinita di 18 mesi. La nuova data di scadenza sarà il 15 ottobre 2023. Puoi modificare questa data di scadenza, purché la nuova scadenza sia inferiore a 18 mesi. Al momento della scadenza, l’attività verrà sospesa. Tuttavia, puoi riattivare l’attività con una nuova data di scadenza di 18 mesi. Non verranno eliminate attività, cartelle di lavoro o dati.

Lo scopo di questa pausa è quello di gestire e mantenere in modo efficace il database delle attività pianificate per garantire prestazioni e consegne ottimali per le attività e le cartelle di lavoro necessarie. D’ora in avanti, verranno applicati i seguenti nuovi criteri di governance. Dopo il 31 gennaio 2023, tutte le attività avranno una data di scadenza massima di 18 mesi. Dopo 18 mesi, le attività scadute verranno messe in pausa e possono essere riattivate in base alle esigenze.

## Configurare le attività pianificate

| Campo | Descrizione |
| --- | --- |
| **[!UICONTROL Scheduled Reports tab]** |  |
| [!UICONTROL Report Name] | Indica il nome dell&#39;attività pianificata. |
| [!UICONTROL Email/FTP] | Indirizzo e-mail o FTP del destinatario. **Nota:** Se è selezionata l’opzione e-mail, i rapporti di dimensioni superiori a 1 MB vengono automaticamente allegati all’e-mail come file .zip. Questa funzione consente di mantenere le dimensioni ridotte del file allegato e non può essere disabilitata. |
| [!UICONTROL Publishing Options] | Questa colonna elenca i Power BI se uno dei [Opzioni di pubblicazione Power BI](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html) è selezionato. |
| [!UICONTROL Schedule] | Tipo di consegna pianificata. |
| [!UICONTROL File Format] | Il formato di consegna del rapporto, ad esempio Excel, PDF, HTML e così via. |
| [!UICONTROL Reactivate] | Quando una cartella di lavoro pianificata non viene eseguita, il Report Builder tenta di eseguire la cartella di lavoro due volte ogni quindici minuti. Dopo tre tentativi non riusciti, il Report Builder disattiva la pianificazione e visualizza il pulsante Riattiva . Quando si riattiva una cartella di lavoro, la consegna pianificata viene riavviata dal momento in cui è stata disattivata.<p>Ad esempio, se una cartella di lavoro pianificata è stata disattivata 14 giorni fa e la riattiva oggi, viene eseguita per ogni giorno mancante e verrà consegnata 14 volte. Se non si desidera che la cartella di lavoro venga consegnata per i giorni mancanti, è possibile eliminare la cartella di lavoro pianificata e quindi creare una nuova cartella di lavoro pianificata utilizzando gli stessi parametri di pianificazione.<p>**Nota:** Non riattivare una cartella di lavoro a meno che non si conosca il motivo per cui è stata disattivata dal sistema. Per risolvere i problemi, scarica una cartella di lavoro disattivata e aggiornala sul lato client. Se non viene visualizzato alcun errore, è necessario essere in grado di riattivarlo. |
| [!UICONTROL Last sent] | Data e ora dell’ultimo invio del rapporto. |
| **Scheda Destinatario** |  |
| [!UICONTROL Recipient email] | Il destinatario e-mail del rapporto. |
| [!UICONTROL Reports] | I rapporti inviati a ciascun destinatario. |
| **Scheda Cronologia rapporti** |  |
| [!UICONTROL File Name] | Indica il nome dell&#39;attività pianificata. |
| [!UICONTROL Date] | Data e ora dell’ultimo invio del rapporto. |
| [!UICONTROL Status] | Lo stato indica se il rapporto è stato inviato o meno. |
| [!UICONTROL Email/FTP] | Indirizzo e-mail o FTP del destinatario del rapporto. |
| [!UICONTROL File Format] | Il formato di consegna del rapporto, ad esempio Excel, PDF, HTML e così via. |
