---
description: Adobe Analytics offre un'interfaccia di reporting flessibile che consente di generare diversi rapporti complessi. La maggior parte dei rapporti genera molto rapidamente, ma potrebbe verificarsi un timeout o un errore di generazione. Per evitare errori di generazione dei rapporti, questa sezione descrive molti fattori che influiscono sulla velocità di generazione dei report. La comprensione di queste informazioni può facilitare la strutturazione dei report in modo che possano essere generati con successo.
keywords: best practice; errore; timeout; risoluzione dei problemi; slow
seo-description: Adobe Analytics offre un'interfaccia di reporting flessibile che consente di generare diversi rapporti complessi. La maggior parte dei rapporti genera molto rapidamente, ma potrebbe verificarsi un timeout o un errore di generazione. Per evitare errori di generazione dei rapporti, questa sezione descrive molti fattori che influiscono sulla velocità di generazione dei report. La comprensione di queste informazioni può facilitare la strutturazione dei report in modo che possano essere generati con successo.
seo-title: Best practice e risoluzione dei problemi per i rapporti
solution: Analytics
title: Best practice e risoluzione dei problemi per i rapporti
topic: Rapporti
uuid: d 4 eef 0 a 3-1 d 26-4460-8 a 2 b -962001 c 9 f 846
translation-type: tm+mt
source-git-commit: 0d4e5bfc0f45b7b3ed9b89df25bcef0730a011d9

---


# Best practice e risoluzione dei problemi per i rapporti

Adobe Analytics offre un'interfaccia di reporting flessibile che consente di generare diversi rapporti complessi. La maggior parte dei rapporti genera molto rapidamente, ma potrebbe verificarsi un timeout o un errore di generazione. Per evitare errori di generazione dei rapporti, questa sezione descrive molti fattori che influiscono sulla velocità di generazione dei report. La comprensione di queste informazioni può facilitare la strutturazione dei report in modo che possano essere generati con successo.

>[!Note]
>Queste raccomandazioni sono valide per Reporting e analisi, Analisi ad hoc e Generatore di report.
>They do not apply to Analysis Workspace, which has its own set of [best practices](/help/analyze/analysis-workspace/optimizing-performance.md). They also do not &gt;apply to Data Warehouse [best practices](https://marketing.adobe.com/resources/help/en_US/reference/?f=data_warehouse_bp). Un set aggiuntivo di
>[procedure](https://marketing.adobe.com/developer/en_US/get-started/best-practices/c-best-practices) ottimali sono disponibili per l'API di rapporti di Adobe Analytics.

## Report Timeouts and Request Queue {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**Timeout**

Un singolo rapporto è suddiviso in più richieste (uno per suddivisione) e ogni richiesta è soggetta a un singolo timeout. Ai rapporti pianificati sono assegnati periodi di timeout più lunghi e hanno più probabilità di avere successo rispetto a quelli generati direttamente in un'interfaccia utente.

**Queue suite di rapporti**

Ogni suite di rapporti conserva una coda separata di richieste. Se più rapporti vengono richiesti contemporaneamente, anche da utenti separati, un numero limitato di report viene generato contemporaneamente. Quando i rapporti sono completi, i rapporti rimanenti vengono generati nell'ordine in cui sono stati ricevuti. Di conseguenza, se un gran numero di rapporti complessi si trovano già nella coda di suite di rapporti, un report generato in genere potrebbe rimandare rapidamente.

## Factors that Affect Report Speed {#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

I fattori seguenti contribuiscono a prolungare i tempi di generazione dei rapporti. L'aumento di uno di questi fattori potrebbe non causare un timeout per il rapporto, ma ritardare altri rapporti nella coda di suite di rapporti e causare il timeout di un report successivo.

**Intervallo di tempo rapporto**

Il fattore più elevato che influisce sui tempi di generazione dei rapporti è il numero di mesi richiesti. Ridurre il numero di mesi da tre a uno diminuisce notevolmente il tempo di generazione, ma la riduzione dell'intervallo di tempo da un mese a una settimana non ha un impatto notevole sui tempi di generazione dei report.

**Numero di metriche**

Con un aumento del numero di metriche, il tempo di esecuzione del report aumenta. La rimozione delle metriche migliora spesso il tempo di generazione dei report.

**Numero di analisi approfondite**

All'interno di un rapporto, ogni suddivisione rappresenta una richiesta separata. Sebbene le singole richieste possano essere completate rapidamente, migliaia di analisi approfondite in un unico report possono rallentare notevolmente il tempo di generazione dei report e influenzare la coda della suite di rapporti.

**Complessità segmento**

I segmenti che considerano diverse dimensioni o hanno molte (24 +) regole aumentano l'impatto dell'elaborazione e aumentano il tempo di generazione dei report.

**Numero di valori univoci**

I report contenenti centinaia di migliaia di valori univoci generano più lentamente rispetto a quelli contenenti un numero minore di valori univoci, anche se il segmento o il filtro riducono il numero di valori che finiscono in un report. Ad esempio, un report che visualizza termini di ricerca genera in genere più lentamente rispetto ad altri rapporti, anche se viene applicato un filtro per mostrare solo termini di ricerca contenenti un valore specifico.

## Other Reporting Options {#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

Oltre a ridurre l'intervallo di tempo, il numero di metriche e il numero di suddivisioni in un rapporto, le seguenti linee guida contribuiscono a incrementare l'affidabilità della distribuzione dei report:

* Utilizza Data Warehouse per richiedere rapporti che contengono molti suddivisioni o metriche. Data Warehouse è progettato per generare questi tipi di rapporti.
* Pianifica i rapporti da eseguire durante le ore non di picco. Questo aumenta la probabilità che un report venga restituito perché la coda di richiesta per una suite di rapporti è più probabilmente vuota durante tali orari.
* Generatore di report può essere utilizzato per suddividere i rapporti in intervalli di tempo più piccoli e richieste che contengono meno metriche. È quindi possibile utilizzare la funzionalità Excel nativa per unire dati da diverse richieste a un singolo rapporto.

