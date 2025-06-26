---
title: Attribuzione algoritmica
description: Dettagli sul modello di attribuzione algoritmica.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 45%

---

# Attribuzione algoritmica

Il [modello di attribuzione](models.md) algoritmica in Analysis Workspace è diverso da altri modelli in quanto utilizza tecniche statistiche per allocare credito tra gli elementi dimensionali nel rapporto o nella tabella a forma libera. Come tutti gli altri modelli di attribuzione in Analysis Workspace, l’attribuzione algoritmica può essere utilizzata su qualsiasi dimensione o metrica. L’attribuzione algoritmica supporta segmentazione e raggruppamenti illimitati e distribuisce il 100% delle conversioni a una o più dimensioni nella tabella (nota anche come attribuzione &quot;frazionaria&quot;).


>[!BEGINSHADEBOX]

Per un video demo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribuzione algoritmica](https://video.tv.adobe.com/v/40053?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]


L’algoritmo utilizzato per l’attribuzione è basato sul dividendo Harsanyi dalla teoria del gioco cooperativo. Il dividendo Harsanyi è una generalizzazione della soluzione del valore di Shapley (dal nome di Lloyd Shapley, un economista premio Nobel) per distribuire credito tra i giocatori in un gioco con contributi disuguali al risultato.

Ad alto livello, il calcolo dell’attribuzione del credito di conversione per ogni punto di contatto considera ogni punto di contatto di marketing all’interno di un intervallo di lookback come una coalizione di giocatori. A questa coalizione di giocatori, un surplus deve essere equamente distribuito. La distribuzione del surplus di ogni coalizione è determinata dal surplus creato in precedenza ricorsivamente da ogni subcoalizione.

Per maggiori dettagli, consulta gli articoli originali di John Harsanyi e Lloyd Shapley:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Il risultato dell’attribuzione algoritmica differisce dagli altri modelli solo quando nell’intervallo di lookback sono presenti più punti di contatto. Le conversioni con un singolo punto di contatto ricevono un credito del 100% indipendentemente dal modello di attribuzione.
