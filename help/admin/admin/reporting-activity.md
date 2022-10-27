---
description: Scopri come utilizzare Reporting Activity Manager per diagnosticare e risolvere i problemi di capacità durante i picchi di reporting.
title: Reporting Activity Manager
feature: Admin Tools
mini-toc-levels: 3
hide: true
hidefromtoc: true
source-git-commit: 123a2131be1a3cb23246e2ba591be645c7025b26
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 4%

---


# Reporting Activity Manager

>[!NOTE]
>
>Questa funzionalità è attualmente in fase di beta testing.

Reporting Activity Manager consente di visualizzare la capacità di reporting per ogni suite di rapporti dell&#39;organizzazione. In qualità di Amministratore, offre una visibilità dettagliata sul consumo dei rapporti e ti aiuta a diagnosticare e risolvere facilmente i problemi di capacità durante i periodi di picco dei rapporti. Quando la tua organizzazione raggiunge la capacità di richiesta di reporting e si verifica un peggioramento delle prestazioni di reporting, ora puoi diagnosticare autonomamente i problemi di reporting senza l’intervento dell’assistenza clienti o dell’ingegneria Adobe. Puoi gestire facilmente le code di reporting all’interno di un’unica interfaccia e agire immediatamente &#x200B; &#x200B; per migliorare l’esperienza degli utenti. Questo strumento:

* Informazioni sulla capacità di reporting corrente nelle suite di rapporti.
* Fornisce informazioni dettagliate sulle query dei report sulle richieste di reporting correnti, sia in coda che in corso.
* Consente di ottimizzare la coda dei rapporti dando priorità ad alcune richieste di reporting e annullandone altre per liberare la capacità. In altre parole, potete chiedere in tempo reale: la relazione è necessaria in questo momento o posso cancellarla a favore di relazioni più urgenti?

## Accedere a Reporting Activity Manager

In Adobe Analytics, gli amministratori accedono a **[!UICONTROL Admin]** > **[!UICONTROL Reporting Activity Manager]**.

## Visualizza la coda dei report

Quando si apre la pagina di panoramica di Reporting Activity Manager, viene visualizzato un elenco delle suite di rapporti di base abilitate.

![coda dei report](assets/reporting-activity1.png)

| Elemento nell’interfaccia utente | Descrizione |
| --- | --- |
| **[!UICONTROL Report Suite]** | La suite di rapporti di base di cui stai monitorando l’attività di reporting. |
| **[!UICONTROL Virtual Report Suite]** | Mostra tutte le suite di rapporti virtuali che si inseriscono in questa suite di rapporti di base. Le suite di rapporti virtuali aggiungono complessità alle richieste di reporting a causa di ulteriori livelli di filtro e segmentazione applicati. Tutte le richieste provenienti dalle suite di rapporti virtuali vengono combinate e vengono ridotte alla suite di rapporti di base.<p>Ad esempio, se hai 10 richieste provenienti da 5 VRS, sono 50 le richieste nella suite di rapporti a livello di base. In questo modo, si può raggiungere molto rapidamente la capacità. |
| **[!UICONTROL Usage Capacity]** | In percentuale, quanta capacità di reporting della suite di rapporti viene utilizzata in tempo reale. |
| **[!UICONTROL Status]** | Quattro possibili indicatori di stato: <ul><li>**Rosso -[!UICONTROL At Capacity]**: La suite di rapporti è composta in termini di capacità di reporting.</li><li>**Giallo -[!UICONTROL Nearing capacity]**: Questa suite di rapporti rischia di raggiungere la sua massima capacità.</li><li>**Verde -[!UICONTROL All good]**: La capacità di segnalazione è abbondante.</li><li>**[!UICONTROL Status pending]**: ?</li><li>**Grigio - Non disponibile**: La suite di rapporti non è configurata per la capacità di reporting.</li></ul> |

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
| Utenti | Quanti utenti stanno attualmente inviando richieste di reporting a questa suite di rapporti. |
| Progetti |  |
| Query |  |
| Tempo medio di attesa |  |
| Capacità di utilizzo | La capacità di utilizzo corrente per questa suite di rapporti. |

{style=&quot;table-layout:auto&quot;}

### Tabella

La tabella dettagliata seguente mostra

| Colonna | Descrizione |
| --- | --- |
| ID query |  |
| Tempo di esecuzione |  |
| Tempo di attesa |  |
| Ora di inizio |  |
| Applicazione | Le applicazioni supportate da Reporting Activity Manager sono: <ul><li>Interfaccia utente di Analysis Workspace</li><li>Progetti pianificati in Workspace</li><li>Report Builder</li><li>Interfaccia utente di Builder: Segmento, metriche calcolate, annotazioni, pubblico, ecc.</li></ul> |
| Utente |  |
| Progetto |  |
| Limiti del mese |
| Colonne |  |
| Segmenti  |  |
| Stato |  |

{style=&quot;table-layout:auto&quot;}


