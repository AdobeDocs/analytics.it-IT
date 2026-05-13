---
description: Scopri quali tecniche statistiche vengono utilizzate per identificare le anomalie.
title: Tecniche Di Statistica Utilizzate Nel Rilevamento Delle Anomalie
feature: Anomaly Detection
role: User, Admin
exl-id: e9868296-e453-45ec-b874-b2aa1b37a1bf
TQID: https://experienceleague.adobe.com/4DIICc89-1ppuJWmUpJBrDrOU7MH78dYBTCHTqkBE2E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1101
ht-degree: 40%

---

# Tecniche statistiche

Il rilevamento delle anomalie in Analysis Workspace utilizza una serie di tecniche di statistica avanzate per determinare se un’osservazione debba essere considerata come anomalia o meno.

A seconda della granularità della data applicata al rapporto, vengono usate 3 diverse tecniche statistiche per il rilevamento di anomalie su base oraria, giornaliera e settimanale/mensile. Tali tecniche sono descritte di seguito.

## Rilevamento delle anomalie con granularità giornaliera

Per i report con granularità giornaliera, l’algoritmo considera diversi fattori importanti per fornire risultati quanto più precisi possibile. In primo luogo, l’algoritmo determina il tipo di modello da applicare in base ai dati disponibili di cui seleziona una delle due classi: un modello basato su serie temporali o un modello di rilevamento di dati aberranti (filtro funzionale).

La selezione del modello della serie temporale si basa sulle seguenti combinazioni per tipo di errore, tendenza e stagionalità (ETS), come descritto da [Hyndman et al. (2008)](https://link.springer.com/book/10.1007/978-3-540-71918-2). In particolare, l’algoritmo prova le seguenti combinazioni:

1. ANA (errore additivo, nessuna tendenza, stagionalità additiva)
1. AAA (errore additivo, tendenza additiva, stagionalità additiva)
1. MNM (errore moltiplicativo, nessuna tendenza, stagionalità moltiplicativa)
1. MNA (errore moltiplicativo, nessuna tendenza, stagionalità additiva)
1. AN (errore additivo, tendenza additiva, nessuna stagionalità)

L’algoritmo verifica l’idoneità di ciascuna delle combinazioni selezionando quella con il miglior errore percentuale assoluto medio (MAPE). Tuttavia, se il MAPE del modello di serie temporali migliore è superiore al 15%, viene applicato un filtro funzionale. In genere, i dati con un elevato grado di ripetizione (ad esempio, settimana su settimana o mese su mese) sono i più adatti a un modello di serie temporali.

Dopo la selezione del modello, l’algoritmo regola quindi i risultati in base alle festività e alla stagionalità su base annua. Per le festività, l’algoritmo controlla se nell’intervallo di date del rapporto sono presenti le seguenti festività:

* Giorno della memoria
* 4 luglio
* Ringraziamento
* Black Friday
* Cyber Monday
* 24-26 dicembre
* Gennaio 1
* Dicembre 31

Queste festività sono state scelte da un’estesa analisi statistica su numerosi punti di dati di clienti, per individuare le ricorrenze più significative per la maggior parte delle tendenze relative ai clienti. Anche se l’elenco non è certamente esaustivo per tutti i clienti o cicli di business, l’applicazione di queste festività migliora in modo significativo le prestazioni complessive dell’algoritmo per quasi tutti i set di dati dei clienti.

Dopo aver selezionato il modello e individuato le festività nell’intervallo di date del rapporto, l’algoritmo procede come descritto di seguito:

1. Costruire il periodo di riferimento delle anomalie. Questo periodo include fino a 35 giorni prima dell’intervallo di date del rapporto e un intervallo corrispondente di 1 anno prima. e tiene conto dei giorni bisestili quando necessario e di tutte le festività applicabili che possono essersi verificate in un giorno di calendario diverso nell’anno precedente.
1. Verifica se le festività nel periodo corrente (escludendo l’anno precedente) sono anomale in base ai dati più recenti.
1. Se la festività nell’intervallo di date corrente è anomala, regola il valore previsto e l’intervallo di affidabilità della festività corrente data la festività corrispondente dell’anno prima (considerando 2 giorni prima e dopo). La correzione per la festività corrente si basa sull’errore percentuale assoluto medio più basso di:

   1. Effetti additivi
   1. Effetti moltiplicativi
   1. Differenza YoY

Osserva il notevole miglioramento delle prestazioni per i giorni di Natale e Capodanno nell’esempio seguente:

![](assets/anomaly_statistics.png)

## Rilevamento delle anomalie con granularità oraria

I dati orari si basano sullo stesso approccio utilizzato dall’algoritmo di granularità giornaliera per le serie temporali. Tuttavia, contano su due pattern di tendenze: il ciclo di 24 ore e il ciclo weekend/feriale. Per cogliere questi due effetti stagionali, l’algoritmo orario costruisce due modelli distinti per un fine settimana e un giorno feriale, utilizzando lo stesso approccio descritto sopra.

Le finestre di formazione per le tendenze orarie si basano su un intervallo di lookback di 336 ore.

## Rilevamento delle anomalie con granularità settimanale e mensile

Le tendenze settimanali e mensili non presentano le stesse tendenze settimanali o giornaliere rilevate con granularità giornaliera o oraria, pertanto viene utilizzato un algoritmo separato. Ogni settimana e ogni mese, un approccio di rilevamento dei valori anomali in due fasi è noto come test GESD (Generalized Extreme Studentized Deviate). Questo test considera il numero massimo di anomalie previste combinate con l’approccio box-plot adeguato (un metodo non parametrico per la scoperta di valori aberranti) per determinare il numero massimo di valori aberranti. Le due fasi sono:

1. Funzione box-plot ponderata: determina il numero massimo di anomalie per i dati di input.
1. Funzione GESD: applicata ai dati di input con il risultato della prima fase.

La fase di rilevamento delle anomalie stagionali per festività e anno su anno quindi sottrae i dati dell’anno scorso da quelli di quest’anno. Quindi esegue di nuovo l’iterazione dei dati utilizzando il processo in due fasi descritto sopra per verificare che le anomalie siano appropriate in base alla stagionalità. Ognuna di queste granularità di date usa un periodo di lookback di 15 mesi o settimane che comprende l’intervallo di date selezionato per il rapporto e un intervallo di date corrispondente di un anno prima, a scopo di formazione.

## Tecniche di statistica utilizzate nell’analisi dei contributi

L’analisi dei contributi è un processo di apprendimento automatico intensivo progettato per individuare i contributori a un’anomalia osservata in Adobe Analytics. Questa funzione è utile per individuare aree di interesse o opportunità per ulteriore analisi, in modo molto più rapido di quanto sarebbe altrimenti possibile.

L’analisi dei contributi esegue un algoritmo in due parti per ogni singolo elemento dimensionale disponibile nel rapporto Analisi dei contributi dell’utente. L’algoritmo opera in questo ordine:

1. Per ogni dimensione, elabora il test V di Cramer. Nell’esempio di seguito, considera una tabella di contingenza con visualizzazioni di pagina per paese per periodi di due anni:

   ![](assets/contingency_table.png)

   Nella Tabella 1, il test V di Cramer può essere utilizzato per misurare l’associazione tra le visualizzazioni di pagina per paese per il periodo 1 (ad esempio, storico) e il periodo 2 (ad esempio, il giorno in cui si verifica l’anomalia). Un indice V di Cramer basso implica un basso livello di associazione. L’indice V di Cramer va da 0 (nessuna associazione) a 1 (associazione completa). La statistica V di Cramer può essere calcolata:

   ![](assets/cramers-v.png)

1. Per ogni elemento dimensione, il residuo di Pearson (PR) viene utilizzato per misurare l’associazione tra la metrica anomala e ogni elemento dimensione. PR segue una distribuzione normale standard, che consente all&#39;algoritmo di confrontare le PR di due variabili casuali anche se le deviazioni non sono confrontabili. In pratica, l’errore non è noto e viene stimato utilizzando una correzione del campione finita.

   Nell’esempio precedente della tabella 1, la PR, con correzione del campione finita per il paese i e il periodo di tempo 2, è data da

   ![](assets/persons-residual.png)

   dove

   ![](assets/pr-example.png)

   (Una formula simile può essere ottenuta per il periodo di tempo 1).

   Per i risultati finali, il punteggio di ogni elemento dimensione viene quindi ponderato dall’indice del V di Cramer e riportato in scala a un numero compreso tra 0 e 1 per ottenere il punteggio di contributo.
