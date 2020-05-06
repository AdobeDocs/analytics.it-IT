---
keywords: Analysis Workspace
title: Cos’è un’analisi per coorte?
topic: Reports and analytics
uuid: 39a83f3a-15d1-41d7-bcdd-50c22aed8f1c
translation-type: tm+mt
source-git-commit: 5d4c0ae58dfb7c54b00f801aebe898f790432903
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 92%

---


# Cos’è un’analisi per coorte?

Un *`cohort`* è un gruppo di persone che condividono le stesse caratteristiche per un determinato periodo di tempo. Lo strumento di analisi per coorte è utile, ad esempio, quando si vuole comprendere in che modo una coorte si relaziona con un marchio. Permette di individuare facilmente cambiamenti nelle tendenze e reagire di conseguenza. (Puoi trovare informazioni sull’analisi per coorte in diversi riferimenti su Internet, ad esempio [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis)).

Dopo aver generato un rapporto sulla coorte, puoi curarne i componenti (dimensioni, metriche e segmenti specifici) e condividerlo con chiunque. Vedi [Cura e condivisione](/help/analyze/analysis-workspace/curate-share/curate.md).

Esempi di cosa è possibile fare con un’analisi per coorte:

* Lanciare campagne sviluppate per promuovere un’azione desiderata.
* Spostare il budget marketing nel momento giusto del ciclo di vita di un cliente.
* Riconoscere quando interrompere una versione di prova o un’offerta per massimizzare il valore.
* Sviluppare idee per il test A/B in aree come prezzo, percorso di upgrade ecc.
* Visualizzare un’analisi per coorte all’interno di un rapporto di analisi guidata.

La funzione di analisi per coorte è disponibile per tutti i clienti di Analytics che dispongono dei diretti di accesso ad Analysis Workspace.

[Analisi per coorte su YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>L&#39;analisi per coorte non supporta metriche non segmentabili, come metriche calcolate, non-integer o [!UICONTROL Occurrences]. Solo le metriche che possono essere utilizzate nei segmenti possono essere utilizzate in Cohort Analysis e possono essere incrementate solo di 1 alla volta.

## Capacità dell’analisi per coorte

A gennaio 2019, Adobe ha rilasciato una nuova versione significativamente migliorata dell’analisi per coorte. Consente di controllare in modo più dettagliato le coorti create. I miglioramenti comprendono:

### Tabella “Retention” (Fidelizzazione)

Un report sulla coorte di fidelizzazione evidenzia i visitatori ripetuti: ogni cella di dati mostra il numero e la percentuale di visitatori nella coorte che hanno eseguito un’azione in quel determinato periodo di tempo. Può contenere fino a 3 metriche e 10 segmenti.

![](assets/retention-report.png)

### Tabella “Churn” (Abbandono)

Una coorte Churn (Abbandono) è l’inverso di una tabella Retention (Fidelizzazione) e mostra i visitatori che non rientrano più, o non sono mai rientrati, nei criteri della coorte nel tempo. Può contenere fino a 3 metriche e 10 segmenti.

![](assets/churn-report.png)

### Rolling Calculation (Calcolo continuo)

Consente di calcolare il livello di fidelizzazione o abbandono dei visitatori in base alla colonna precedente, non alla colonna Included (Incluso).

![](assets/cohort-rolling-calculation.png)

### Tabella “Latency” (Latenza)

Misura il tempo trascorso prima e dopo il verificarsi dell’evento di inclusione. È un ottimo strumento di analisi pre/post. La colonna Included (Incluso) è al centro della tabella ed è preceduta e seguita dai periodi di tempo prima e dopo l’evento di inclusione.

![](assets/cohort-latency.png)

### Coorte con dimensione personalizzata

Puoi creare le coorti in base a una dimensione selezionata, anziché in base al tempo come avviene per impostazione predefinita. Puoi usare dimensioni quali canale di marketing, campagna, prodotto, pagina, regione, o qualsiasi altra dimensione in Adobe Analytics per mostrare in che modo la fidelizzazione cambia, in base a valori diversi di tali dimensioni.

![](assets/cohort-customizable-cohort-row.png)

Per informazioni su come impostare ed eseguire un rapporto per coorte, consulta  [Configurare un rapporto di analisi per coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

