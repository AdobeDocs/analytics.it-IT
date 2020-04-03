---
description: Adobe Analytics offre un'interfaccia di reporting flessibile che consente di generare diversi report complessi. Anche se la maggior parte dei report vengono generati molto rapidamente, è possibile che si verifichino dei report con timeout o che non vengano generati correttamente. Per evitare errori di generazione dei report, questa sezione spiega molti fattori che influiscono sulla velocità di generazione dei report. Comprendere queste informazioni può aiutarti a strutturare i rapporti in modo che siano più propensi a generare con successo.
keywords: best practices;failure;timeout;troubleshooting;slow
title: Tecniche consigliate e risoluzione dei problemi per i rapporti
topic: Reports
uuid: d4eef0a3-1d26-4460-8a2b-962001c9f846
translation-type: tm+mt
source-git-commit: 025ac334f9191b6455eea0530a2a21c01199000a

---


# Tecniche consigliate e risoluzione dei problemi per i rapporti

Adobe Analytics offre un&#39;interfaccia di reporting flessibile che consente di generare diversi report complessi. Anche se la maggior parte dei report vengono generati molto rapidamente, è possibile che si verifichino dei report con timeout o che non vengano generati correttamente. Per evitare errori di generazione dei report, questa sezione spiega molti fattori che influiscono sulla velocità di generazione dei report. Comprendere queste informazioni può aiutarti a strutturare i rapporti in modo che siano più propensi a generare con successo.

>[!Note]
>Queste raccomandazioni si applicano a Reporting e analisi, Analisi ad hoc e Generatore di report.
>Non sono applicabili ad Analysis Workspace, che dispone di un proprio set di [best practice](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). Inoltre, non si applicano alle [best practice](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse_bp.html)di Data Warehouse. Un altro set di
>[le best practice](https://marketing.adobe.com/developer/en_US/get-started/best-practices/c-best-practices) sono disponibili per l&#39;API di reporting di Adobe Analytics.

## Timeout report e coda richieste {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**Timeout**

Un singolo rapporto è suddiviso in più richieste (una per suddivisione) e ogni richiesta è soggetta a un timeout individuale. Ai rapporti pianificati vengono concessi periodi di timeout più lunghi e hanno maggiori probabilità di successo rispetto ai rapporti generati direttamente in un&#39;interfaccia utente.

**Coda suite di rapporti**

Ogni suite di rapporti mantiene una coda separata di richieste. Se vengono richiesti più rapporti contemporaneamente, anche da utenti separati, viene generato un numero limitato di rapporti contemporaneamente. Al termine dei rapporti, i rapporti rimanenti vengono generati nell&#39;ordine in cui sono stati ricevuti. Di conseguenza, se un numero elevato di report complessi si trova già nella coda della suite di rapporti, potrebbe verificarsi un timeout per un report che generalmente genera rapidamente.

## Fattori che influiscono sulla velocità del report {#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

I seguenti fattori contribuiscono a prolungare i tempi di generazione dei report. L&#39;aumento di uno di questi fattori potrebbe non determinare un timeout per il report, ma potrebbe ritardare altri report nella coda della suite di rapporti e causare il timeout di un report successivo.

**Intervallo di tempo rapporto**

Il fattore più importante che influisce sul tempo di generazione del report è il numero di mesi richiesti. La riduzione del numero di mesi da tre a uno riduce notevolmente il tempo di generazione, ma la riduzione dell&#39;intervallo di tempo da un mese a una settimana non ha un forte impatto sul tempo di generazione dei report.

**Numero di metriche**

Con l&#39;aumentare del numero di metriche, il tempo di esecuzione del report aumenta. La rimozione delle metriche spesso migliora il tempo di generazione dei report.

**Numero di analisi approfondite**

All&#39;interno di un rapporto, ogni suddivisione rappresenta una richiesta separata. Anche se le singole richieste possono essere completate rapidamente, l&#39;esecuzione di migliaia di analisi in un singolo rapporto può rallentare notevolmente il tempo di generazione del rapporto e influenzare la coda della suite di rapporti.

**Complessità del segmento**

I segmenti che considerano più dimensioni o con più regole (24+) aumentano l&#39;impatto dell&#39;elaborazione e aumentano il tempo di generazione dei report.

**Numero di valori univoci**

I report contenenti centinaia di migliaia di valori univoci si generano più lentamente rispetto ai report contenenti meno valori univoci, anche se il segmento o il filtro riduce il numero di valori che appaiono in fondo in un report. Ad esempio, un rapporto che mostra i termini di ricerca genera più lentamente rispetto ad altri rapporti, anche se viene applicato un filtro per mostrare solo i termini di ricerca contenenti un valore specifico.

## Altre opzioni di reporting {#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

Oltre a ridurre l&#39;intervallo di tempo, il numero di metriche e il numero di suddivisioni in un rapporto, le seguenti linee guida contribuiscono ad aumentare l&#39;affidabilità della distribuzione dei report:

* Utilizzare Data Warehouse per richiedere rapporti contenenti numerose analisi approfondite o metriche. Data Warehouse è progettato per generare questi tipi di report.
* Pianificare l&#39;esecuzione dei report nelle ore non di picco. Ciò aumenta la probabilità che venga restituito un report perché la coda di richieste per una suite di rapporti è più probabile che sia vuota durante tali periodi.
* Generatore di report può essere utilizzato per suddividere i report in intervalli di tempo più piccoli e per le richieste che contengono meno metriche. Potete quindi utilizzare la funzionalità Excel nativa per unire i dati di varie richieste in un unico rapporto.

