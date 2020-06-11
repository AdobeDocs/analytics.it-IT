---
title: Best practice e risoluzione dei problemi di reporting
description: Procedure ottimali e suggerimenti per la risoluzione dei problemi durante la generazione dei rapporti.
keywords: best practices;failure;timeout;troubleshooting;slow
translation-type: tm+mt
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---


# Best practice e risoluzione dei problemi di reporting

*Questa pagina di aiuto fa riferimento alle best practice di Reporting e analisi. Per Analysis Workspace, consulta[Ottimizzazione delle prestazioni](../analysis-workspace/workspace-faq/optimizing-performance.md)di Analysis Workspace. Per Data Warehouse, consulta[Best practice](/help/export/data-warehouse/data-warehouse-bp.md)per Data Warehouse.*

Adobe Analytics offre un&#39;interfaccia di reporting flessibile che consente di generare diversi report complessi. Anche se la maggior parte dei report vengono generati molto rapidamente, è possibile che si verifichino dei report con timeout o che non vengano generati. In questa pagina vengono illustrati i fattori che influiscono sulla velocità di generazione dei report. Comprendere queste informazioni può essere utile per strutturare i rapporti in modo che siano più propensi a generare con successo.

## Timeout report e coda richieste

* **Timeout**: Un singolo rapporto è suddiviso in più richieste (una per suddivisione) e ogni richiesta è soggetta a un timeout individuale. Ai rapporti pianificati vengono concessi periodi di timeout più lunghi e hanno maggiori probabilità di successo rispetto ai rapporti generati direttamente in un&#39;interfaccia utente.
* **Coda** suite di rapporti: Ogni suite di rapporti mantiene una coda separata di richieste. Se vengono richiesti più rapporti contemporaneamente, anche da utenti separati, viene generato un numero limitato di rapporti contemporaneamente. Al termine dei rapporti, i rapporti rimanenti vengono generati nell&#39;ordine in cui sono stati ricevuti. Di conseguenza, se un numero elevato di report complessi si trova già nella coda della suite di rapporti, potrebbe verificarsi un timeout per un report che generalmente genera rapidamente.

## Fattori che influiscono sulla velocità del report

I seguenti fattori contribuiscono a prolungare i tempi di generazione dei report. L&#39;aumento di uno di questi fattori generalmente non influisce sulle prestazioni, ma potrebbe ritardare altri report nella coda della suite di rapporti e causare il timeout di un report successivo.

* **Intervallo** di tempo rapporto: Il fattore più importante che influisce sul tempo di generazione del report è il numero di mesi richiesti. La riduzione del numero di mesi da tre a uno riduce notevolmente il tempo di generazione, ma la riduzione dell&#39;intervallo di tempo da un mese a una settimana non ha un forte impatto sul tempo di generazione dei report.
* **Numero di metriche**: Con l&#39;aumentare del numero di metriche, il tempo di esecuzione del report aumenta. La rimozione delle metriche spesso migliora il tempo di generazione dei report.
* **Numero di suddivisioni**: All&#39;interno di un rapporto, ogni suddivisione rappresenta una richiesta separata. Anche se le singole richieste possono essere completate rapidamente, l&#39;esecuzione di migliaia di analisi in un singolo rapporto può rallentare notevolmente il tempo di generazione del rapporto e influenzare la coda della suite di rapporti.
* **Complessità** del segmento: I segmenti che considerano più dimensioni o con più regole (24+) aumentano l&#39;impatto dell&#39;elaborazione e aumentano il tempo di generazione dei report.
* **Numero di valori** univoci: I report contenenti centinaia di migliaia di valori univoci si generano più lentamente rispetto ai report contenenti meno valori univoci, anche se il segmento o il filtro riduce il numero di valori che appaiono in fondo in un report. Ad esempio, un rapporto che mostra i termini di ricerca genera più lentamente rispetto ad altri rapporti, anche se viene applicato un filtro per mostrare solo i termini di ricerca contenenti un valore specifico.

## Altre opzioni di reporting

Le seguenti linee guida contribuiscono a migliorare l&#39;affidabilità della distribuzione dei report:

* Utilizzare Data Warehouse per richiedere rapporti contenenti numerose analisi approfondite o metriche. Data Warehouse è progettato per generare questi tipi di report.
* Pianificare l&#39;esecuzione dei report nelle ore non di picco. Ciò aumenta la probabilità che venga restituito un report perché la coda di richieste per una suite di rapporti è più probabile che sia vuota durante tali periodi.
* Generatore di report può essere utilizzato per suddividere i report in intervalli di tempo più piccoli e per le richieste che contengono meno metriche. Potete quindi utilizzare la funzionalità Excel nativa per unire i dati di varie richieste in un unico rapporto.
