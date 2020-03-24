---
keywords: Analysis Workspace
title: Cos’è un’analisi per coorte?
topic: Reports and analytics
uuid: 39a83f3a-15d1-41d7-bcdd-50c22aed8f1c
translation-type: tm+mt
source-git-commit: 99232c5bce94cfc55b9f01080555cb8e545442e9

---


# Cos’è un’analisi per coorte?

Un *`cohort`* è un gruppo di persone che condividono le stesse caratteristiche per un determinato periodo di tempo. Lo strumento di analisi per coorte è utile, ad esempio, quando si vuole comprendere in che modo una coorte si relaziona con un marchio. Permette di individuare facilmente cambiamenti nelle tendenze e reagire di conseguenza. (Puoi trovare informazioni sull’analisi per coorte in diversi riferimenti su Internet, ad esempio [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis)).

Dopo aver generato un rapporto sulla coorte, puoi curarne i componenti (dimensioni, metriche e segmenti specifici) e condividerlo con chiunque. Vedi [Cura e condivisione](/help/analyze/analysis-workspace/curate-share/curate.md).

Esempi di cosa è possibile fare con un’analisi per coorte:

* Lanciare campagne progettate per stimolare un’azione desiderata.
* Spostare il budget marketing al momento giusto nel ciclo di vita del cliente.
* Riconoscere quando terminare una versione di prova o un&#39;offerta per massimizzare il valore.
* Idee per test A/B in aree quali prezzi, percorso di aggiornamento e così via.
* Visualizzare un rapporto Analisi per coorte all’interno di un rapporto Analisi guidata.

L’analisi per coorte è disponibile per tutti i clienti Analytics che dispongono dei diritti di accesso ad Analysis Workspace.

[Analisi per coorte su YouTube](https://www.youtube.com/watch?v=kqOIYrvV-co&index=45&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>L’analisi per coorte non supporta le metriche calcolate.

## Capacità dell’analisi per coorte

A gennaio 2019, Adobe ha rilasciato una nuova versione significativamente migliorata dell’analisi per coorte. Consente un controllo molto più preciso sulle coorti che si stanno costruendo. Di seguito sono riportati i miglioramenti introdotti:

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

Misura il tempo trascorso prima e dopo l&#39;evento di inclusione. Questo è uno strumento eccellente per l&#39;analisi pre/post. La colonna &quot;Incluso&quot; si trova al centro della tabella e i periodi di tempo prima e dopo che l&#39;evento di inclusione viene visualizzato su entrambi i lati.

![](assets/cohort-latency.png)

### Coorte con dimensione personalizzata

Crea coorti in base a una dimensione selezionata e non a coorti basati sul tempo, che sono le impostazioni predefinite. Puoi usare dimensioni quali canale di marketing, campagna, prodotto, pagina, regione, o qualsiasi altra dimensione in Adobe Analytics per mostrare in che modo la fidelizzazione cambia, in base a valori diversi di tali dimensioni.

![](assets/cohort-customizable-cohort-row.png)

Per informazioni su come impostare ed eseguire un rapporto per coorte, consulta  [Configurare un rapporto di analisi per coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

