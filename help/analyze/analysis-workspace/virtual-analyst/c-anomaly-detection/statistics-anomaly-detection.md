---
description: Il rilevamento delle anomalie in Analysis Workspace utilizza una serie di tecniche di statistica avanzate per determinare se un’osservazione debba essere considerata come anomalia o meno.
seo-description: Il rilevamento delle anomalie in Analysis Workspace utilizza una serie di tecniche di statistica avanzate per determinare se un’osservazione debba essere considerata come anomalia o meno.
seo-title: Tecniche di statistica utilizzate nel rilevamento delle anomalie
title: Tecniche di statistica utilizzate nel rilevamento delle anomalie
uuid: b6ef6a2e-0836-4c9a-bf7e-01910199bb92
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Tecniche di statistica utilizzate nel rilevamento delle anomalie

Il rilevamento delle anomalie in Analysis Workspace utilizza una serie di tecniche di statistica avanzate per determinare se un’osservazione debba essere considerata come anomalia o meno.

A seconda della granularità data utilizzata nel rapporto, vengono utilizzate 3 diverse tecniche statistiche, in particolare per il rilevamento orario, giornaliero, settimanale/mensile delle anomalie. Tali tecniche sono descritte di seguito.

## Anomaly detection for daily granularity {#section_758ACA3C0A6B4D399563ECABFB8316FA}

Per i report con granularità giornaliera, l’algoritmo considera diversi fattori importanti per fornire risultati quanto più precisi possibile. Innanzitutto, l'algoritmo determina quale tipo di modello applicare in base ai dati disponibili di cui selezioniamo una delle due classi: un modello basato su serie temporale o un modello di rilevamento di dati aberranti (filtro funzionale).

Il primo si basa sulle seguenti combinazioni per tipo di errore, tendenza e stagionalità (ETS) come descritto da [Hyndman et al. (2008)](https://www.springer.com/us/book/9783540719168). Nello specifico, l’algoritmo prova le seguenti combinazioni:

1. ANA (errore additivo, nessuna tendenza, stagionalità additiva)
1. AAA (errore additivo, tendenza additiva, stagionalità additiva)
1. MNM (errore moltiplicativo, nessuna tendenza, stagionalità moltiplicativa)
1. MNA (errore moltiplicativo, nessuna tendenza, stagionalità additiva)
1. AAN (errore additivo, tendenza additiva, nessuna stagionalità)

L’algoritmo verifica quale di queste combinazioni è la più adatta selezionando quella con il miglior valore di errore medio assoluto percentuale (MAPE, Mean Absolute Percentage Error). Tuttavia, se il valore MAPE del modello per serie temporale migliore è maggiore del 15%, viene applicato il filtro funzionale. Solitamente, per i dati altamente ripetitivi (ad esempio, di settimana in settima o di mese in mese) risulta più adatto il modello di serie temporale.

Dopo la selezione del modello, l’algoritmo regola i risultati in base a festività e stagionalità anno su anno. Per le festività, l’algoritmo verifica la presenza delle seguenti festività nell’intervallo di date del rapporto:

* Memorial Day
* 4 luglio
* Giorno del Ringraziamento
* Black Friday
* Cyber Monday
* 24-26 dicembre
* 1 gennaio
* 31 dicembre

Queste festività sono state selezionate sulla base di un'ampia analisi statistica su molti punti di dati dei clienti, per identificare le festività più importanti per il maggior numero di tendenze dei clienti. Anche se l'elenco non è certo esaustivo per tutti i clienti o cicli di business, abbiamo scoperto che l'applicazione di queste festività ha notevolmente migliorato le prestazioni complessive dell'algoritmo per quasi tutti i set di dati dei clienti.

Dopo aver selezionato il modello e individuato le festività nell’intervallo di date del rapporto, l’algoritmo procede come descritto di seguito:

1. Crea il periodo di riferimento per le anomalie, che include fino a 35 giorni prima dell'intervallo di date del rapporto, e un intervallo di date corrispondente di 1 anno prima (tenendo conto dei giorni bisestili quando richiesto e delle eventuali festività applicabili che possono essersi verificate in un giorno di calendario diverso rispetto all'anno precedente).
1. Verifica se le festività nel periodo corrente (escludendo l’anno precedente) sono anomale in base ai dati più recenti.
1. Se la festività nell'intervallo di date corrente è anomala, regola il valore previsto e l'intervallo di confidenza della festività corrente data la festività dell'anno precedente (considerando 2 giorni prima e dopo). La correzione per la festività corrente si basa sul valore MAPE più basso di:

   1. Effetti additivi
   1. Effetti moltiplicativi
   1. Differenza anno su anno

Notate il notevole miglioramento delle prestazioni nel giorno di Natale e Capodanno nel seguente esempio:

![](assets/anomaly_statistics.png)

## Anomaly detection for hourly granularity {#section_014C9E9209AF43F8A03D5D46E3B3AEE7}

I dati orari si basano sullo stesso approccio algoritmico utilizzato per la granularità giornaliera. Tuttavia, contano su due pattern di tendenze: il ciclo di 24 ore e il ciclo weekend/feriale. Per acquisire questi due effetti stagionali, l’algoritmo orario crea due modelli distinti per weekend e giorno feriale utilizzando lo stesso approccio già descritto.

Le finestre di formazione per le tendenze orarie si basano su una finestra di lookback di 336 ore.

## Anomaly detection for weekly and monthly granularities {#section_5D421576BFBC4B24A58DFCC0A6407545}

Le tendenze settimanali e mensili non presentano le stesse tendenze settimanali o giornaliere riscontrate con granularità giornaliera o oraria; per questo motivo viene utilizzato un algoritmo distinto. Per la granularità settimanale e mensile, viene usato un approccio di rilevamento dati aberranti in due fasi: il test Generalized Extreme Studentized Deviate (GESD). Questo test considera il numero massimo di anomalie previste combinato con l’approccio di tipo diagramma a scatola regolato (metodo non parametrico per il rilevamento di dati aberranti) per determinare il numero massimo di dati aberranti. Le due fasi sono:

1. Funzione box-plot ponderata: determina il numero massimo di anomalie per i dati di input.
1. Funzione GESD: applicata ai dati di input con il risultato della prima fase.

La fase di rilevamento delle anomalie stagionali per festività e anno su anno quindi sottrae i dati dello scorso anno dai dati di quest'anno e quindi ripete i dati utilizzando nuovamente il processo in due fasi descritto sopra per verificare che le anomalie siano appropriate in base alla stagionalità. Ognuna di queste granularità di date usa un periodo di lookback di 15 mesi o settimane che comprende l’intervallo di date selezionato per il rapporto e un intervallo di date corrispondente di un anno prima, a scopo di formazione.
