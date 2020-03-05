---
title: Attribuzione algoritmica
description: Dettagli sul modello di attribuzione algoritmica in Adobe Analytics.
translation-type: tm+mt
source-git-commit: 143cbed5f2159b7faab387e10896af836d0780f7

---


# Attribuzione algoritmica

Il modello [di](attribution.md) attribuzione algoritmica in Analysis Workspace è diverso dagli altri modelli in quanto utilizza tecniche statistiche per allocare crediti nei valori delle dimensioni del rapporto o della tabella a forma libera. Come tutti gli altri modelli di attribuzione in Analysis Workspace, può essere utilizzato su qualsiasi dimensione o metrica e supporta segmentazione e suddivisioni illimitate e distribuisce il 100% delle conversioni alle dimensioni nella tabella (detta anche attribuzione &quot;frazionaria&quot;).

L&#39;algoritmo utilizzato per l&#39;attribuzione è basato sul Dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione di valore Shapley (dal nome di Lloyd Shapley, un economista premio Nobel) per la distribuzione del credito tra i giocatori in un gioco con contributi disuguali al risultato.

Ad un livello elevato, il calcolo dell&#39;attribuzione del credito di conversione per ogni punto di contatto considera ogni punto di contatto di marketing all&#39;interno di una finestra di lookback come una coalizione di giocatori a cui un surplus deve essere equamente distribuito. La distribuzione delle eccedenze di ciascuna coalizione è determinata in base all&#39;eccedenza creata in precedenza da ogni subcoalizione (o dai valori di dimensione partecipanti in precedenza) in modo ricorsivo. Per maggiori dettagli, consultare i documenti originali di John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. &quot;Un valore per i giochi di persona.&quot; *Contributi alla Teoria dei Giochi 2.28*, 1953, pp. 307-317.
* Harsanyi, John C. &quot;Un modello di negoziazione semplificato per il gioco cooperativo n-persona.&quot; *International Economic Review 4.2*, 1963, pagg. 194-220.

> [!NOTE] Il risultato dell&#39;attribuzione algoritmica differisce solo dagli altri modelli quando nella finestra di lookback sono presenti più punti di contatto. Le conversioni con un singolo punto di contatto ricevono un credito del 100% indipendentemente dal modello di attribuzione.
