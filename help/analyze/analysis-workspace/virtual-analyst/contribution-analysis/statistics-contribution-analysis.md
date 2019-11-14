---
description: L’analisi dei contributi è un potente processo di machine learning progettato per individuare i fattori che contribuiscono a un’anomalia osservata in Adobe Analytics. Questa funzione è utile per individuare aree di interesse o opportunità per ulteriore analisi, in modo molto più rapido di quanto sarebbe altrimenti possibile.
title: Tecniche di statistica utilizzate nell’analisi dei contributi
uuid: f77eb4e4-4fd6-4397-b8a8-a063f199b676
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Tecniche di statistica utilizzate nell’analisi dei contributi

L’analisi dei contributi è un potente processo di machine learning progettato per individuare i fattori che contribuiscono a un’anomalia osservata in Adobe Analytics. Questa funzione è utile per individuare aree di interesse o opportunità per ulteriore analisi, in modo molto più rapido di quanto sarebbe altrimenti possibile.

A tal fine, l’analisi dei contributi esegue un algoritmo in due parti per ogni elemento dimensione disponibile per il rapporto Analisi contributi dell’utente. L’algoritmo opera in questo ordine:

1. Per ogni dimensione, calcola la statistica del test V di Cramer. Nell’esempio di seguito, considera una tabella di contingenza con visualizzazioni di pagina per paese per periodi di due anni:

   ![](assets/contingency_table.png)

   Nella tabella 1, il V di Cramer può essere utilizzato per misurare l'associazione tra le visualizzazioni di pagina per paese per il periodo 1 (storico) e il periodo 2 (ad esempio il giorno in cui si è verificata l'anomalia). Un valore basso per il V di Cramer implica un basso livello di associazione. Il V di Cramer va da 0 (nessuna associazione) a 1 (associazione completa). La statistica V di Cramer può essere calcolata:

   ![](assets/cramers-v.png)

1. Per ogni elemento di dimensione, il residuo di Persona (PR) viene utilizzato per misurare l'associazione tra la metrica anomala e ogni elemento di dimensione. Il PR segue una distribuzione normale standard, che consente all’algoritmo di confrontare i PR di due variabili casuali anche se le deviazioni non sono paragonabili. In pratica, l’errore non è noto ed è stimato con correzione a campione finita.

   Nell’esempio della tabella 1, il PR con correzione a campione finita per il paese 1 e il periodo di tempo 2 è dato da

   ![](assets/persons-residual.png)

   Qui,

   ![](assets/pr-example.png)

   (È possibile ottenere una formula simile per il periodo di tempo 1.)

   Per i risultati finali, il punteggio di ogni elemento dimensione viene quindi ponderato dalla misura V di Cramer e ridimensionato a un numero compreso tra 0 e 1 per fornire il punteggio di contributo.

