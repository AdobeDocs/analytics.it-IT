---
description: Scopri come utilizzare Reporting Activity Manager per diagnosticare e risolvere i problemi di capacità durante i picchi di reporting.
title: Reporting Activity Manager
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 21270e1a4f05208525261969c2e6858df8647aa1
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 4%

---

# Reporting Activity Manager

>[!NOTE]
>
>Questa funzionalità è attualmente in fase di beta testing.

La [!UICONTROL Reporting Activity Manager] ti consente di visualizzare la capacità di reporting per ogni suite di rapporti della tua organizzazione. In qualità di Amministratore, offre una visibilità dettagliata sul consumo dei rapporti e ti aiuta a diagnosticare e risolvere facilmente i problemi di capacità durante i periodi di picco dei rapporti.

Quando la tua organizzazione raggiunge la capacità di richiesta di reporting e si verifica un peggioramento delle prestazioni di reporting, ora puoi diagnosticare autonomamente i problemi di reporting senza l’intervento dell’assistenza clienti o dell’ingegneria Adobe. Puoi gestire facilmente le code di reporting all’interno di un’unica interfaccia e agire immediatamente &#x200B; &#x200B; per migliorare l’esperienza degli utenti. Questo strumento:

* Ti informa in tempo reale della tua capacità di reporting corrente nelle suite di rapporti.
* Fornisce informazioni dettagliate sulle query dei report sulle richieste di reporting correnti, sia in coda che in corso.
* Consente di ottimizzare la coda dei rapporti dando priorità ad alcune richieste di reporting e annullandone altre per liberare la capacità. In altre parole, potete chiedere in tempo reale: la relazione è necessaria in questo momento o posso cancellarla a favore di relazioni più urgenti?

## Accedere a Reporting Activity Manager

In Adobe Analytics, gli amministratori accedono a **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

## Autorizzazioni

Per gestire l’attività di reporting è necessaria l’autorizzazione amministratore prodotto di Analytics (in Adobe Admin Console).

![autorizzazione](assets/rep-mgr-permission.png)

## Visualizza la coda dei report

All&#39;apertura della [!UICONTROL Reporting Activity] Nella pagina di panoramica di Manager viene visualizzato un elenco delle suite di rapporti di base abilitate.

![coda dei report](assets/reporting-activity1.png)

| Elemento nell’interfaccia utente | Descrizione |
| --- | --- |
| **[!UICONTROL Report Suite]** | La suite di rapporti di base di cui stai monitorando l’attività di reporting. |
| **[!UICONTROL Virtual Report Suite]** | Mostra tutte le suite di rapporti virtuali che si inseriscono in questa suite di rapporti di base. Le suite di rapporti virtuali aggiungono complessità alle richieste di reporting a causa di ulteriori livelli di filtro e segmentazione applicati. Tutte le richieste provenienti dalle suite di rapporti virtuali vengono combinate e vengono ridotte alla suite di rapporti di base.<p>Ad esempio, se hai 10 richieste provenienti da 5 VRS, sono 50 le richieste nella suite di rapporti a livello di base. In questo modo, si può raggiungere molto rapidamente la capacità. |
| **[!UICONTROL Usage Capacity]** | In percentuale, quanta capacità di reporting della suite di rapporti viene utilizzata in tempo reale. |
| **[!UICONTROL Status]** | Quattro possibili indicatori di stato: <ul><li>**Rosso -[!UICONTROL At Capacity]**: La suite di rapporti è composta in termini di capacità di reporting. (100%) </li><li>**Giallo -[!UICONTROL Nearing capacity]**: Questa suite di rapporti rischia di raggiungere la sua massima capacità. (90% - 99%)</li><li>**Verde -[!UICONTROL All good]**: La capacità di segnalazione è abbondante. (0% - 89%)</li><li>**Grigio -[!UICONTROL Status pending/Not enabled]**: Capacità del rapporto non disponibile.</li></ul> |

{style=&quot;table-layout:auto&quot;}

### Altre azioni dell’attività di reporting

* Fai clic su **[!UICONTROL Refresh]** in alto a destra per aggiornare i risultati.
* Fai clic sulla stella a sinistra del nome della suite di rapporti per preferire questa suite di rapporti.
* Controlla **[!UICONTROL Favorites]** in alto a sinistra per mostrare i tuoi preferiti.
* Cerca le suite di rapporti per nome o per ID nella barra di ricerca.
* Filtrare le suite di rapporti in base al loro stato.

## Visualizzare l’attività di reporting per le singole suite di rapporti

Fai clic sul collegamento del titolo di una suite di rapporti per la quale vuoi visualizzare i dettagli.

![suite per report](assets/indiv-report-ste.png)

### Grafico a linee

Il grafico a linee mostra l’attività di reporting per la suite di rapporti selezionata nelle ultime 2 ore.

* L’asse x mostra i dati della capacità di reporting nelle ultime 2 ore.
* L’asse y mostra il tempo medio di attesa di una query, in secondi.
* Puoi passare il cursore del mouse sul grafico a linee per visualizzare i punti nel tempo e nel tempo medio di attesa per quell’istante.

   ![dettaglio](assets/detail.png)

### Filtro

È possibile filtrare la tabella per applicazione (vedere l’elenco nella tabella seguente), per utente e per progetto.

![filter](assets/filter.png)

### Numeri di riepilogo

![filter](assets/summary_numbers.png)

I numeri di riepilogo mostrano le seguenti informazioni:

| Numero di riepilogo | Descrizione |
| --- | --- |
| [!UICONTROL Users] | Il numero di utenti che attualmente inviano richieste di reporting a questa suite di rapporti. |
| [!UICONTROL Projects] | Progetti Workspace, cartelle di lavoro di Report Builder, ecc. |
| [!UICONTROL Queries] | Numero di query attualmente in esecuzione. |
| [!UICONTROL Average Wait Time] | Tempo medio di attesa per tutte le query in esecuzione. |
| [!UICONTROL Usage Capacity] | La capacità di utilizzo corrente per questa suite di rapporti. |

{style=&quot;table-layout:auto&quot;}

### Tabella

La tabella dettagliata seguente mostra i dettagli sulla suite di rapporti.

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL Query ID] | Può essere utilizzato per la risoluzione dei problemi. |
| [!UICONTROL Running Time] | Per quanto tempo la query è in esecuzione. |
| [!UICONTROL Wait Time] | Tempo di attesa della query prima dell’elaborazione. Generalmente a &quot;0&quot; quando c&#39;è abbastanza capacità. |
| [!UICONTROL Start Time] | Quando la query ha iniziato l’elaborazione (ora locale dell’amministratore). |
| [!UICONTROL Application] | Le applicazioni supportate dalla [!UICONTROL Reporting Activity Manager] sono: <ul><li>Interfaccia utente di Analysis Workspace</li><li>Progetti pianificati in Workspace</li><li>Report Builder</li><li>Interfaccia utente di Builder: Segmento, metriche calcolate, annotazioni, pubblico, ecc.</li><li>Chiamate API da 1.4 o 2.0 API</li><li>Avvisi intelligenti</li></ul> |
| [!UICONTROL User] | Utente che ha avviato la query. |
| [!UICONTROL Project] | Nomi di progetto Workspace salvati, ID di report API e così via (I metadati possono variare tra le varie applicazioni). |
| [!UICONTROL Month Boundaries] | Quanti confini mensili attraversa una richiesta. Questo aggiunge la complessità della richiesta. |
| [!UICONTROL Columns] | Il numero di metriche e suddivisioni in Workspace per misurare la complessità della richiesta. |
| [!UICONTROL Segments] | Quanti segmenti vengono applicati a questa richiesta. Questo aggiunge la complessità della richiesta. |
| [!UICONTROL Status] | Indicatori di stato: <ul><li>**In esecuzione**: La richiesta è in fase di elaborazione.</li><li>**In sospeso**: Richiesta in attesa di elaborazione.</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Annullare le richieste di reporting

Per annullare una richiesta

1. Seleziona la casella a sinistra di uno o più **[!UICONTROL Query ID]** nella tabella e fai clic su **[!UICONTROL Cancel requests]** in basso.

   Puoi anche annullare le richieste in blocco visualizzando i dettagli per: [!UICONTROL User], [!UICONTROL Project]oppure [!UICONTROL Application]. Le richieste successive per un progetto, un utente o un&#39;applicazione che non erano in coda o in esecuzione al momento dell&#39;annullamento possono ancora essere visualizzate quando l&#39;attività viene aggiornata.

1. In **[!UICONTROL Cancel x query]** Se necessario, puoi modificare il messaggio di cancellazione.
1. Fai clic su **[!UICONTROL Continue]**.

   ![cancel-query](assets/cancel-query.png)

Gli utenti di applicazioni in Workspace, ad esempio, vedranno il seguente avviso comparire nei loro progetti:

![avviso-cancellazione](assets/cancel-user-facing.png)

## Domande frequenti

| Domanda | Risposta |
| --- | --- |
| Posso acquistare una capacità di reporting aggiuntiva? | Questa funzionalità sarà disponibile a breve. |

{style=&quot;table-layout:auto&quot;}
