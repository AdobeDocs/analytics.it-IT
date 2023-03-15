---
title: Best practice per il reporting e la risoluzione dei problemi
description: Best practice e suggerimenti per la risoluzione dei problemi durante la generazione dei rapporti.
keywords: best practice;errore;timeout;risoluzione dei problemi;lento
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 1c09f514-42ab-4698-bdee-d1b509da3f11
source-git-commit: 4ddc2640aa8b3a22411c86ff8bfe0ecf345a3d63
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 100%

---

# Best practice per il reporting e la risoluzione dei problemi

{{ra-eol}}

*Questa pagina della guida fa riferimento alle best practice di Reports &amp; Analytics. Per Analysis Workspace, consulta [Ottimizzare le prestazioni di Analysis Workspace](../analysis-workspace/workspace-faq/optimizing-performance.md). Per Data Warehouse, consulta [Best practice per Data Warehouse](/help/export/data-warehouse/data-warehouse-bp.md).*

Adobe Analytics offre un’interfaccia di reporting flessibile che consente di generare una varietà di rapporti complessi. Anche se la maggior parte dei rapporti viene generata molto rapidamente, è possibile trovare rapporti in cui si verifica un timeout oppure che non vengono generati. Questa pagina spiega i fattori che influiscono sulla velocità della generazione dei rapporti. Comprendere queste informazioni può essere utile per strutturare i rapporti in modo che abbiano maggiori probabilità di essere generati correttamente.

## Timeout dei rapporti e coda delle richieste

* **Timeout**: un singolo rapporto viene suddiviso in più richieste (una per raggruppamento) e ogni richiesta è soggetta a un singolo timeout. Ai rapporti pianificati vengono concessi periodi di timeout più lunghi e hanno più probabilità di essere corretti rispetto ai rapporti generati direttamente in un’interfaccia utente.
* **Coda della suite di rapporti**: ogni suite di rapporti mantiene una coda separata di richieste. Se vengono richiesti più rapporti contemporaneamente, anche da utenti diversi, viene generato simultaneamente un numero limitato di rapporti. Quando i rapporti vengono completati, i rapporti rimanenti vengono generati nell’ordine in cui sono stati ricevuti. Di conseguenza, se un numero elevato di rapporti complessi si trova già nella coda della suite di rapporti, potrebbe verificarsi il timeout di un rapporto che solitamente viene generato rapidamente.

## Fattori che influiscono sulla velocità del rapporto

I seguenti fattori contribuiscono a creare tempi di generazione dei rapporti più lunghi. L’aumento di uno di questi fattori in genere non influisce sulle prestazioni, ma potrebbe ritardare altri rapporti nella coda della suite di rapporti e causare il timeout di un rapporto successivo.

* **Intervallo di tempo del rapporto**: il fattore più importante che influisce sul tempo di generazione del rapporto è il numero di mesi richiesti. La riduzione del numero di mesi da tre a uno riduce notevolmente il tempo di generazione, ma la riduzione dell’intervallo di tempo da un mese a una settimana non ha un impatto significativo sui tempi di generazione dei rapporti.
* **Numero di metriche**: con l’aumento del numero di metriche, aumenta anche il tempo di esecuzione del rapporto. La rimozione delle metriche spesso migliora il tempo di generazione dei rapporti.
* **Numero di raggruppamenti**: all’interno di un rapporto, ogni raggruppamento rappresenta una richiesta separata. Anche se le singole richieste possono essere completate rapidamente, l’esecuzione di migliaia di raggruppamenti in un singolo rapporto può rallentare notevolmente il tempo di generazione del rapporto e influenzare la coda della suite di rapporti.
* **Complessità del segmento**: i segmenti che considerano più dimensioni o che dispongono di molte regole (più di 24) aumentano l’impatto dell’elaborazione e il tempo di generazione del rapporto.
* **Numero di valori univoci**: i rapporti che contengono centinaia di migliaia di valori univoci vengono generati più lentamente rispetto ai rapporti che ne contengono meno, anche se il segmento o il filtro riduce il numero di valori che vengono infine visualizzati in un rapporto. Ad esempio, un rapporto che visualizza i termini di ricerca solitamente viene generato più lentamente rispetto ad altri rapporti, anche se viene applicato un filtro per mostrare solo i termini di ricerca contenenti un valore specifico.

## Altre opzioni per il reporting

Le seguenti linee guida contribuiscono ad aumentare l’affidabilità della consegna dei rapporti:

* Utilizza Data Warehouse per richiedere rapporti contenenti numerosi raggruppamenti o metriche. Data Warehouse è progettato per generare questi tipi di rapporti.
* Pianifica l’esecuzione dei rapporti nelle ore di minimo utilizzo. Questo aumenta la probabilità che un rapporto venga restituito perché è più probabile che la coda di richiesta per una suite di rapporti sia vuota in tali momenti.
* Puoi utilizzare Report Builder per suddividere i rapporti in intervalli di tempo più piccoli e in richieste che contengono meno metriche. È quindi possibile utilizzare la funzionalità nativa di Excel per unire i dati provenienti da varie richieste in un unico rapporto.
