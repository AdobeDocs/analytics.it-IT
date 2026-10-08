---
description: Scopri gli errori e la risoluzione dei problemi di Analysis Workspace.
title: Errori e risoluzione dei problemi
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
TQID: 'https://experienceleague.adobe.com/Kr34CyT7YxRqKRdwpaLN-DZwHhLbaT663Gj-pc5Wd8s'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
    internal-label: Alerts
  - id: c457b289-f974-4a67-a5b6-dec3ffa77675
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 93%
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

Quando utilizzi Analysis Workspace, puoi utilizzare le informazioni riportate di seguito per risolvere alcuni problemi comuni.

| Problema | Come risolverlo |
|---|---|
| Quando trascino una metrica, un messaggio indica *Dati non validi*. | Il messaggio indicante che i dati non sono validi significa che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel report. Ad esempio, due metriche posizionate una sopra all’altra non possono essere restituite come dati, in quanto non è possibile visualizzare due metriche in questo modo. Posiziona invece le metriche una accanto all’altra. |
| Quando trascino una metrica, non visualizzo dati effettivi, ma solo zeri. | Se crei correttamente un report Workspace, ma non sono presenti dati, puoi controllare alcuni elementi:<ul><li>Se hai applicato un segmento nel report, i criteri del segmento potrebbero non corrispondere ad alcun dato. Prova a rimuovere il segmento o a regolare la definizione del segmento.</li><li>Controlla l’intervallo di date in alto a destra e accertati che sia impostato sul valore desiderato.</li><li>Accedi al tuo sito Web e utilizza [Adobe Experience Platform Debugger](https://experienceleague.adobe.com/it/docs/experience-platform/debugger/home) per convalidare i dati raccolti.</li></ul> |
