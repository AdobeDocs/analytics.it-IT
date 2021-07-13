---
title: Best practice e risoluzione dei problemi di reporting
description: Procedure consigliate e suggerimenti per la risoluzione dei problemi durante la generazione dei rapporti.
keywords: best practice;errore;timeout;risoluzione dei problemi;lento
role: User, Admin
exl-id: 1c09f514-42ab-4698-bdee-d1b509da3f11
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 0%

---

# Best practice e risoluzione dei problemi di reporting

*Questa pagina di aiuto fa riferimento alle best practice di Reports &amp; Analytics. Per Analysis Workspace, consulta [Ottimizzare le prestazioni di Analysis Workspace](../analysis-workspace/workspace-faq/optimizing-performance.md). Per Data Warehouse, consulta [Data Warehouse best practice](/help/export/data-warehouse/data-warehouse-bp.md).*

Adobe Analytics offre un’interfaccia di reporting flessibile che consente di generare una varietà di rapporti complessi. Anche se la maggior parte dei rapporti viene generata molto rapidamente, puoi incontrare rapporti che si interrompono o non generano. Questa pagina spiega i fattori che influiscono sulla velocità di generazione dei rapporti. Informazioni su queste informazioni possono essere utili per strutturare i rapporti in modo che abbiano maggiori probabilità di generare con successo.

## Timeout del rapporto e coda richieste

* **Timeout**: Un singolo rapporto viene suddiviso in più richieste (una per suddivisione) e ogni richiesta è soggetta a un timeout individuale. Ai rapporti pianificati vengono concessi periodi di timeout più lunghi e hanno più probabilità di successo dei rapporti generati direttamente in un’interfaccia utente.
* **Coda** suite di rapporti: Ogni suite di rapporti mantiene una coda separata di richieste. Se vengono richiesti più rapporti contemporaneamente, anche da utenti diversi, viene generato un numero limitato di rapporti simultaneamente. Al termine dei rapporti, i rapporti rimanenti vengono generati nell’ordine in cui sono stati ricevuti. Di conseguenza, se un numero elevato di rapporti complessi si trovano già nella coda della suite di rapporti, potrebbe verificarsi un timeout di un rapporto generato in genere rapidamente.

## Fattori che influiscono sulla velocità del report

I seguenti fattori contribuiscono a tempi di generazione dei rapporti più lunghi. L’aumento di uno di questi fattori in genere non influisce sulle prestazioni, ma potrebbe ritardare altri rapporti nella coda della suite di rapporti e causare il timeout di un rapporto successivo.

* **Intervallo** di tempo del rapporto: Il fattore più importante che influisce sul tempo di generazione del rapporto è il numero di mesi richiesti. La riduzione del numero di mesi da tre a uno riduce notevolmente il tempo di generazione, ma la riduzione dell&#39;intervallo di tempo da un mese a una settimana non ha un impatto significativo sui tempi di generazione dei rapporti.
* **Numero di metriche**: Con l’aumento del numero di metriche, il tempo di esecuzione del rapporto aumenta. La rimozione delle metriche spesso migliora il tempo di generazione dei rapporti.
* **Numero di suddivisioni**: All’interno di un rapporto, ogni suddivisione rappresenta una richiesta separata. Anche se le singole richieste possono essere completate rapidamente, l’esecuzione di migliaia di raggruppamenti in un singolo rapporto può rallentare notevolmente il tempo di generazione del rapporto e influenzare la coda della suite di rapporti.
* **Complessità** del segmento: I segmenti che considerano più dimensioni o con più regole (24+) aumentano l’impatto dell’elaborazione e aumentano il tempo di generazione del rapporto.
* **Numero di valori** univoci: I rapporti che contengono centinaia di migliaia di valori univoci generano più lentamente rispetto ai rapporti che contengono meno valori univoci, anche se il segmento o il filtro riduce il numero di valori che vengono infine visualizzati in un rapporto. Ad esempio, un rapporto che visualizza i termini di ricerca genera più lentamente rispetto ad altri rapporti, anche se viene applicato un filtro per mostrare solo i termini di ricerca contenenti un valore specifico.

## Altre opzioni di reporting

Le seguenti linee guida contribuiscono ad aumentare l’affidabilità della distribuzione dei report:

* Utilizza Data Warehouse per richiedere rapporti contenenti numerose suddivisioni o metriche. Data Warehouse è progettato per generare questi tipi di report.
* Pianifica l&#39;esecuzione dei report nelle ore non di picco. Questo aumenta la probabilità che un report venga restituito perché è più probabile che la coda di richiesta per una suite di rapporti sia vuota in questi momenti.
* Puoi utilizzare il Report Builder per suddividere i rapporti in intervalli di tempo più piccoli e in richieste che contengono meno metriche. È quindi possibile utilizzare la funzionalità nativa di Excel per unire i dati provenienti da varie richieste in un unico rapporto.
