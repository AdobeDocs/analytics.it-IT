---
description: 'null'
title: Attribuzione algoritmica
uuid: bb345642-4f45-4fb8-82d0-803248dd52ea
translation-type: tm+mt
source-git-commit: b5418e6321b09ddbab36e0052f75f36067086e3e

---


# Attribuzione algoritmica

![Algoritmo](assets/algorithmic.png)

Il modello [di](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html#attribution-models) attribuzione algoritmica in Analysis Workspace è diverso da altri modelli all’interno di Attribution IQ, in quanto utilizza tecniche statistiche per allocare il credito tra i valori delle dimensioni nel report o nella tabella freeform. Come tutti gli altri modelli di attribuzione in Analysis Workspace, può essere utilizzato su qualsiasi dimensione o metrica e supporta segmentazione e suddivisioni illimitate e distribuisce il 100% delle conversioni alle dimensioni nella tabella (detta anche attribuzione &quot;frazionaria&quot;).

L&#39;algoritmo utilizzato per l&#39;attribuzione è basato sul Dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione di valore Shapley (dal nome di Lloyd Shapley, un economista premio Nobel) per la distribuzione del credito tra i giocatori in un gioco con contributi disuguali al risultato.

Ad un livello elevato, il calcolo dell&#39;attribuzione del credito di conversione per ogni punto di contatto considera ogni punto di contatto di marketing all&#39;interno di una finestra di lookback come una coalizione di giocatori a cui un surplus deve essere equamente distribuito. La distribuzione delle eccedenze di ciascuna coalizione è determinata in base all&#39;eccedenza creata in precedenza da ogni subcoalizione (o dai valori di dimensione partecipanti in precedenza) in modo ricorsivo. Per maggiori dettagli si rimanda ai documenti originali di John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. &quot;Un valore per i giochi di persona.&quot; Contributi alla Teoria dei Giochi 2.28 (1953): 307-317.

* Harsanyi, John C. &quot;Un modello di negoziazione semplificato per il gioco cooperativo n-persona.&quot; Revisione economica internazionale 4.2 (1963): 194-220.

*Nota: Il risultato dell&#39;attribuzione algoritmica differisce solo dagli altri modelli quando nella finestra di lookback sono presenti più punti di contatto. Ad esempio, con un solo punto di contatto, il 100% del credito verrà assegnato a tale valore indipendentemente dal modello di attribuzione selezionato.*