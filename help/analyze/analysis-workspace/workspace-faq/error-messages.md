---
description: Scopri gli errori e la risoluzione dei problemi di Analysis Workspace.
title: Errori e risoluzione dei problemi
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 100%

---

# Errori e risoluzione dei problemi

È possibile che, durante l’interazione con Analysis Workspace, si verifichino errori che possono influire sulla funzionalità e sulle prestazioni. Di seguito sono elencati i tipi di errore più comuni, il motivo per cui si verificano e le ottimizzazioni possibili.

## Messaggi di errore

Alcuni messaggi di errore comuni che potrebbero verificarsi durante l’utilizzo di Analysis Workspace:

| Messaggio di errore | Perché si verifica l’errore? | Ottimizzazione |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una suite di rapporti specifica. Questo errore è causato da richieste API, progetti pianificati, rapporti pianificati, avvisi pianificati e utenti simultanei che eseguono richieste di generazione di rapporti. | Distribuisci le richieste e le pianificazioni per la suite di rapporti in modo più uniforme durante l’intera giornata.<p>Gli amministratori possono utilizzare il [Reporting Activity Manager per identificare e annullare le richieste](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md) che utilizzano la capacità di reporting.</p> |
| [!UICONTROL This report is too complex. Please review best practices for building Analysis Workspace reports.] | La richiesta di reporting è troppo grande e non può essere eseguita. Questo errore è causato da timeout dovuti alla complessità della richiesta. | Semplifica la richiesta. Ad esempio, riduci l’intervallo di date, semplifica i criteri di segmentazione o rimuovi alcune colonne o righe nella tabella. In alternativa, potresti anche suddividere la tabella in richieste separate. |
| [!UICONTROL The report suite is currently exceeding its reporting capacity. Please simplify the request or try again later.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una suite di rapporti specifica. Questo errore è causato da richieste API, progetti pianificati e utenti simultanei che eseguono richieste di reporting. | Distribuisci le richieste e le pianificazioni per la suite di rapporti in modo più uniforme durante l’intera giornata. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe sta riscontrando un problema da risolvere. | Invia il codice di errore all’Assistenza clienti. |
| [!UICONTROL Error 500: Failed to load page] | I problemi relativi alla rete locale, come le [impostazioni del firewall](/help/technotes/ip-addresses.md) aziendale, contribuiscono a questo errore. Inoltre, è possibile che Adobe stia affrontando un problema che necessita di essere risolto. | Prova a eseguire di nuovo l’accesso dopo alcuni minuti. Se il problema persiste, invia il codice ID istanza EIM all’Assistenza clienti. |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | La tabella contiene troppe celle a forma libera (righe * colonne). | Rimuovi alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |


## Risoluzione dei problemi

Quando utilizzi Analysis Workspace, puoi usare le informazioni riportate di seguito per risolvere alcuni problemi comuni.

| Problema | Come risolverlo |
|---|---|
| Quando trascino una metrica, un messaggio indica *Dati non validi*. | Il messaggio indicante che i dati non sono validi significa che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel report. Ad esempio, due metriche posizionate una sopra all’altra non possono essere restituite come dati, in quanto non è possibile visualizzare due metriche in questo modo. Posiziona invece le metriche una accanto all’altra. |
| Quando trascino una metrica, non visualizzo dati effettivi, ma solo zeri. | Se crei correttamente un report Workspace, ma non sono presenti dati, puoi controllare alcuni elementi:<ul><li>Se hai applicato un segmento nel report, i criteri del segmento potrebbero non corrispondere ad alcun dato. Prova a rimuovere il segmento o a regolare la definizione del segmento.</li><li>Controlla l’intervallo di date in alto a destra e accertati che sia impostato sul valore desiderato.</li><li>Vai al tuo sito web e utilizza il [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it) per convalidare i dati raccolti.</li></ul> |



<!--
# Common error messages

You may encounter errors when interacting with Analysis Workspace that will also influence performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

| Error message | Why does this occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. <p>Administrators can use the [Reporting Activity Manager to identify and cancel requests](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md) that are consuming reporting capacity. |
| [!UICONTROL The report suite is currently exceeding its reporting capacity. Please simplify the request or try again later.] |  Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe is experiencing an issue that needs to be resolved. | Try refreshing your project and if the problem persists, submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](/help/technotes/ip-addresses.md), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Your segment criteria or report filter is too broad. | Narrow your search text criteria and try the request again. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Non-default attribution is not supported for the dimension that you are using. | Replace the dimension in your table with one that is compatible with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |
-->