---
description: Scopri come utilizzare il Reporting Activity Manager per diagnosticare e risolvere i problemi di capacità durante i periodi in cui si verificano picchi di reporting.
title: Reporting Activity Manager
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: e7346b11a7d3eb4c18ec02df6c8a07574e02a2b4
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 93%

---

# Reporting Activity Manager

>[!NOTE]
>
>Questa funzionalità è attualmente in fase di test beta

Il [!UICONTROL Reporting Activity Manager] ti consente di visualizzare la capacità di reporting per ogni suite di rapporti della tua organizzazione. In qualità di Amministratore, offre una visibilità dettagliata sul consumo di reporting e ti aiuta a diagnosticare e risolvere facilmente i problemi di capacità durante i periodi in cui si verificano picchi di reporting.

Quando la tua organizzazione raggiunge la capacità di richiesta di reporting e si verifica un peggioramento delle prestazioni, ora è disponibile un modo per diagnosticare autonomamente i problemi di reporting senza l’intervento dell’Assistenza clienti o dei tecnici di Adobe. Puoi gestire facilmente le code di reporting all’interno di un’unica interfaccia e agire immediatamente per migliorare l’esperienza degli utenti. Questo strumento:

* ti informa in tempo reale sulla capacità di reporting corrente nelle suite di rapporti.
* Fornisce informazioni dettagliate sulle query relative alle richieste di reporting correnti, sia in coda che in corso.
* Consente di ottimizzare la coda di reporting dando priorità ad alcune richieste di reporting e annullandone altre per liberare la capacità. In altre parole, puoi chiederti in tempo reale: il rapporto è necessario in questo momento o posso annullarlo a favore di rapporti più urgenti?

## Accedere a Reporting Activity Manager

In Adobe Analytics, gli amministratori accedono a **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

## Autorizzazioni

Per gestire l’attività di reporting è necessaria l’autorizzazione Amministratore prodotto di Analytics (in Adobe Admin Console).

![autorizzazione](/help/admin/admin/assets/rep-mgr-permission.png)

## Visualizzare la coda dei rapporti

All’apertura della pagina di panoramica di [!UICONTROL Reporting Activity] Manager, viene visualizzato un elenco delle suite di rapporti di base abilitate.

![coda dei rapporti](/help/admin/admin/assets/reporting-activity1.png)

| Elemento nell’interfaccia utente | Descrizione |
| --- | --- |
| **[!UICONTROL Report Suite]** | La suite di rapporti di base di cui si sta monitorando l’attività di reporting. |
| **[!UICONTROL Virtual Report Suite]** | Mostra tutte le suite di rapporti virtuali che confluiscono in questa suite di rapporti di base. Le suite di rapporti virtuali aggiungono complessità alle richieste di reporting a causa di ulteriori livelli di filtro e di segmentazione applicati. Tutte le richieste provenienti dalle suite di rapporti virtuali vengono combinate e ridotte alla suite di rapporti di base.<p>Ad esempio, se disponi di 10 richieste provenienti da 5 VRS, nella suite di rapporti a livello di base le richieste sono 50. In questo modo, si possono raggiungere molto rapidamente i limiti di capacità. |
| **[!UICONTROL Usage Capacity]** | In termini percentuali, quanta capacità di reporting della suite di rapporti viene utilizzata in tempo reale. |
| **[!UICONTROL Status]** | Quattro possibili indicatori di stato: <ul><li>**Rosso -[!UICONTROL At Capacity]**: la suite di rapporti ha raggiunto il limite massimo in termini di capacità di reporting. (100%) </li><li>**Giallo -[!UICONTROL Nearing capacity]**: questa suite di rapporti rischia di raggiungere la capacità massima. (90% - 99%)</li><li>**Verde -[!UICONTROL All good]**: la capacità di reporting è sufficiente. (0% - 89%)</li><li>**Grigio -[!UICONTROL Status pending/Not enabled]**: la capacità del rapporto non è disponibile.</li></ul> |

{style="table-layout:auto"}

### Altre azioni dell’attività di reporting

* Fai clic su **[!UICONTROL Refresh]** in alto a destra per aggiornare i risultati.
* Fai clic sulla stella a sinistra del nome della suite di rapporti per preferire questa suite di rapporti.
* Seleziona **[!UICONTROL Favorites]** in alto a sinistra per mostrare i tuoi preferiti.
* Cerca nelle suite di rapporti per nome o per ID nella barra di ricerca.
* Filtra le suite di rapporti in base al loro stato.

## Visualizzare l’attività di reporting per le singole suite di rapporti

Fai clic sul collegamento del titolo di una suite di rapporti per la quale vuoi visualizzare i dettagli.

![suite per report](/help/admin/admin/assets/indiv-report-ste.png)

### Grafico a linee

Il grafico a linee mostra l’attività di reporting per la suite di rapporti selezionata nelle ultime 2 ore.

* L’asse x mostra i dati della capacità di reporting nelle ultime 2 ore.
* L’asse y mostra il tempo medio di attesa di una query in secondi.
* Puoi passare il cursore del mouse sul grafico a linee per visualizzare i punti nel tempo e il tempo medio di attesa per quell’istante.

   ![dettaglio](/help/admin/admin/assets/detail.png)

### Filtro

È possibile filtrare la tabella per Applicazione (consulta l’elenco nella tabella seguente), per Utente e per Progetto.

![filter](/help/admin/admin/assets/filter.png)

### Numeri di riepilogo

![filter](/help/admin/admin/assets/summary_numbers.png)

I numeri di riepilogo mostrano le seguenti informazioni:

| Numero di riepilogo | Descrizione |
| --- | --- |
| [!UICONTROL Users] | Il numero di utenti che attualmente inviano richieste di reporting a questa suite di rapporti. |
| [!UICONTROL Projects] | Progetti Workspace, cartelle di lavoro di Report Builder, ecc. |
| [!UICONTROL Queries] | Numero di query attualmente in esecuzione. |
| [!UICONTROL Average Wait Time] | Tempo medio di attesa per tutte le query in esecuzione. |
| [!UICONTROL Usage Capacity] | La capacità di utilizzo corrente per questa suite di rapporti. |

{style="table-layout:auto"}

### Tabella

La tabella dettagliata seguente mostra i dettagli sulla suite di rapporti.

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL Query ID] | Può essere utilizzato per la risoluzione dei problemi. |
| [!UICONTROL Running Time] | Per quanto tempo la query è in esecuzione. |
| [!UICONTROL Wait Time] | Tempo di attesa della query prima dell’elaborazione. Generalmente a “0” quando c’è abbastanza capacità. |
| [!UICONTROL Start Time] | Quando la query ha iniziato l’elaborazione (ora locale dell’amministratore). |
| [!UICONTROL Application] | Le applicazioni supportate dalla [!UICONTROL Reporting Activity Manager] sono: <ul><li>Interfaccia utente di Analysis Workspace</li><li>Progetti pianificati in Workspace</li><li>Report Builder</li><li>Interfaccia utente di Builder: segmento, metriche calcolate, annotazioni, pubblico, ecc.</li><li>Chiamate API da 1.4 o 2.0 API</li><li>Avvisi intelligenti</li></ul> |
| [!UICONTROL User] | Utente che ha avviato la query. |
| [!UICONTROL Project] | Nomi di progetto Workspace salvati, ID di report API e così via (I metadati possono variare tra le varie applicazioni). |
| [!UICONTROL Month Boundaries] | Quanti limiti mensili attraversa una richiesta. Questo si aggiunge alla complessità della richiesta. |
| [!UICONTROL Columns] | Il numero di metriche e raggruppamenti in Workspace per misurare la complessità della richiesta. |
| [!UICONTROL Segments] | Quanti segmenti vengono applicati a questa richiesta. Questo si aggiunge alla complessità della richiesta. |
| [!UICONTROL Status] | Indicatori di stato: <ul><li>**In esecuzione**: richiesta in fase di elaborazione.</li><li>**In sospeso**: richiesta in attesa di elaborazione.</li></ul> |

{style="table-layout:auto"}

## Annullare le richieste di reporting

Per annullare una richiesta

1. Seleziona la casella a sinistra di uno o più **[!UICONTROL Query ID]** nella tabella e fai clic su **[!UICONTROL Cancel requests]** in basso.

   Puoi anche annullare le richieste in blocco visualizzando i dettagli per [!UICONTROL User], [!UICONTROL Project] oppure [!UICONTROL Application]. Le richieste successive per un progetto, un utente o un’applicazione che non erano in coda o in esecuzione al momento dell’annullamento possono ancora apparire quando l’attività viene aggiornata.

1. Nella finestra **[!UICONTROL Cancel x query]** che viene visualizzata, puoi modificare il messaggio di cancellazione se necessario.
1. Fai clic su **[!UICONTROL Continue]**.

   ![cancel-query](/help/admin/admin/assets/cancel-query.png)

Gli utenti di applicazioni in Workspace, ad esempio, vedranno il seguente avviso comparire nei loro progetti:

![cancel-user-notice](/help/admin/admin/assets/cancel-user-facing.png)

## Domande frequenti

| Domanda | Risposta |
| --- | --- |
| Posso acquistare una capacità di reporting aggiuntiva? | Questa funzionalità sarà disponibile a breve. |

{style="table-layout:auto"}
