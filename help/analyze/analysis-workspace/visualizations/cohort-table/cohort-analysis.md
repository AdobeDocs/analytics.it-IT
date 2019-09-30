---
keywords: Analysis Workspace
seo-title: L'analisi per coorte
solution: Analytics
title: L'analisi per coorte
topic: Reports and Analytics
uuid: 39a83f3a-15d1-41d7-bcdd-50c22aed8f1c
translation-type: tm+mt
source-git-commit: d2014912533b5dda5bd97401a6f3386a2d08a27e

---


# Cos’è un’analisi per coorte?

A *`cohort`* is a group of people sharing common characteristics over a specified period. Cohort Analysis is useful, for example, when you want to learn how a cohort engages with a brand. Permette di individuare facilmente cambiamenti nelle tendenze e reagire di conseguenza. (Explanations of Cohort Analysis are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

Dopo aver generato un rapporto sulla coorte, puoi curarne i componenti (dimensioni, metriche e segmenti specifici) e condividerlo con chiunque. See [Curate and Share](../../../../analyze/analysis-workspace/curate-share/curate.md#concept_4A9726927E7C44AFA260E2BB2721AFC6).

Examples of what you can do with Cohort Analysis:

* Lanciare campagne sviluppate per promuovere un’azione desiderata.
* Spostare il budget marketing nel momento giusto del ciclo di vita di un cliente.
* Riconoscere quando interrompere una versione di prova o un’offerta per massimizzare il valore.
* Sviluppare idee per il test A/B in aree come prezzo, percorso di upgrade ecc.
* Visualizzare un’analisi per coorte all’interno di un rapporto di analisi guidata.
* Riconoscere quando interrompere una versione di prova o un’offerta per massimizzare il valore.
* Sviluppare idee per il test A/B in aree come prezzo, percorso di upgrade ecc.

La funzione di analisi per coorte è disponibile per tutti i clienti di Analytics che dispongono dei diretti di accesso ad Analysis Workspace.

[Cohort Analysis on YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&index=45&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>Cohort Analysis does not support calculated metrics.

## Cohort Analysis capabilities

In January 2019, Adobe released a new and significantly enhanced version of Cohort Analysis. Consente di controllare in modo più dettagliato le coorti create. I miglioramenti comprendono:

### Tabella “Retention” (Fidelizzazione)

Un rapporto sulla coorte di mantenimento restituisce i visitatori: ogni cella di dati mostra il numero e la percentuale di visitatori nella coorte che ha eseguito l'azione durante tale periodo di tempo. Può contenere fino a 3 metriche e 10 segmenti.

![](assets/retention-report.png)

### Tabella “Churn” (Abbandono)

Una coorte di Churn è l'inverso di una tabella di conservazione e mostra i visitatori che non hanno soddisfatto o non hanno mai soddisfatto i criteri di restituzione per la coorte nel tempo. Può contenere fino a 3 metriche e 10 segmenti.

![](assets/churn-report.png)

### Rolling Calculation (Calcolo continuo)

Consente di calcolare il livello di fidelizzazione o abbandono dei visitatori in base alla colonna precedente, non alla colonna Included (Incluso).

![](assets/cohort-rolling-calculation.png)

### Tabella “Latency” (Latenza)

Misura il tempo trascorso prima e dopo il verificarsi dell’evento di inclusione. È un ottimo strumento di analisi pre/post. La colonna Included (Incluso) è al centro della tabella ed è preceduta e seguita dai periodi di tempo prima e dopo l’evento di inclusione.

![](assets/cohort-latency.png)

### Coorte con dimensione personalizzata

Puoi creare le coorti in base a una dimensione selezionata, anziché in base al tempo come avviene per impostazione predefinita. Puoi usare dimensioni quali canale di marketing, campagna, prodotto, pagina, regione, o qualsiasi altra dimensione in Adobe Analytics per mostrare in che modo la fidelizzazione cambia per valori diversi di tali dimensioni.

![](assets/cohort-customizable-cohort-row.png)

Per informazioni su come impostare ed eseguire un rapporto per coorte, consulta [Configurare un rapporto di analisi per coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

