---
description: Le suite di rapporti di rollup aggregano i dati da più suite di rapporti figlio e li visualizzano in un set di dati riepilogato.
solution: Analytics
title: Suite di rapporti rollup e globali
topic: Admin tools
uuid: c90b8e38-2c95-4318-8165-a362106b6142
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Suite di rapporti rollup e globali

Le suite di rapporti di rollup aggregano i dati da più suite di rapporti figlio e li visualizzano in un set di dati riepilogato.

Per non sbagliarsi con le suite di rapporti globali, i rollup forniscono una posizione utile per visualizzare i totali sommati come visualizzazioni pagina, ricavi o metriche Tecnologia. I rollup vengono utilizzati di frequente perché non richiedono un'implementazione aggiuntiva.

## Definizioni dei tipi di suite di rapporti {#section_E51E03E3917040278600A7E9638A91C7}

**Suite** di rapporti globale: L’implementazione viene modificata per inviare richieste di immagini tra domini diversi in una singola suite di rapporti globale, oltre alle singole suite di rapporti.

**Suite** di rapporti rollup: Creato in Strumenti di amministrazione. Prende la somma di ogni metrica alla fine di ogni giorno.

* I rollup sono liberi di utilizzare e non incrementano le chiamate server.
* I rollup forniscono dati totali, ma non segnalano valori singoli nei report. Ad esempio, i valori eVar1 non sono inclusi, ma il totale aggregato può essere incluso.
* I dati non vengono deduplicati quando si combinano dati tra suite per report. Un singolo utente può toccare tre diverse suite di rapporti in un solo giorno e visualizzare nel rollup tre visitatori unici al giorno.
* L'aggregazione del rollup avviene su base notturna.
* Quando aggiungete una suite di rapporti a un rollup esistente, i dati della cronologia non vengono inclusi nel rollup.
* Le suite di rapporti rollup dispongono di funzionalità di reporting limitate. Ad esempio, i conteggi dei visitatori univoci vengono aggiunti tra le suite di rapporti. Se la stessa persona visita due suite di rapporti separate, un rollup elenca la persona come due visitatori, mentre una suite di rapporti globale standard mostra un visitatore.
* Tutte le suite di rapporti figlio devono contenere dei dati per poter eseguire il rollup. Se in un rollup sono incluse nuove suite di rapporti, accertatevi di inviare almeno una visualizzazione di pagina a tali suite.
* Le suite di rapporti rollup sono limitate a un massimo di 40 suite di rapporti figlio.
* Le suite di rapporti rollup sono limitate a un massimo di 100 eventi.
* I dati contenuti nelle suite di rapporti rollup non supportano le sottorelazioni, i segmenti o le metriche introdotte nei rapporti di marketing.
* Il rapporto Pagine non è disponibile nelle suite per report di rollup. Viene sostituito dal rapporto Siti più popolari, che riporta le metriche a livello di suite figlia.

## Rollup vs. Global Report Suites {#section_7B3703DC7ABF4B9EA9DF02A54592CAD0}

**Chiamate** server: Le suite di rapporti globali incrementano le chiamate al server secondario, mentre i rollup non effettuano chiamate al server di alcun tipo.

**Modifiche** di implementazione: I rollup non richiedono alcuna modifica di implementazione, mentre le suite di rapporti globali richiedono un ID suite di rapporti aggiuntivo nel file s_code.js.

**Duplicazione**: Le suite di rapporti globali deduplicano i visitatori univoci, mentre i rollup no. Ad esempio, se un utente visita tre dei tuoi domini nello stesso giorno, i rollup contano tre visitatori unici al giorno. Le suite di rapporti globali registrerebbero un visitatore unico.

**Intervallo** di tempo: I rollup vengono elaborati solo a mezzanotte ogni notte, mentre le suite per report globali riportano i dati con latenza standard.

**Larghezza**: Le suite per report globali possono attribuire credito alle variabili di conversione tra suite per report, nonché fornire percorsi tra suite per report. I rollup non possono comunicare tra le suite di rapporti.

**Dati** storici: I rollup possono aggregare i dati storici, mentre le suite di rapporti globali riportano solo i dati dal momento in cui sono stati implementati.

**Rapporti**: Le suite di rapporti globali forniscono informazioni aggiuntive su TUTTI i rapporti implementati; i rollup forniscono dati aggregati solo per report di alto livello.

**Prodotti** supportati: I rollup non sono supportati in data warehouse o nelle analisi ad hoc. I rapporti di marketing sono limitati a 40 suite di rapporti per bambini. Le suite di rapporti globali possono essere utilizzate in tutti i prodotti e possono avere un numero illimitato di suite di rapporti figlio.

## Quale tipo di suite di rapporti si desidera implementare? {#section_868066B9604B49BABBF84074BA5E9C71}

Quando scegli se utilizzare i rollup o le suite di rapporti globali, prendi in considerazione quanto segue:

* Il numero di chiamate server è critico per la mia organizzazione? Se è importante mantenere limitate le chiamate server, è consigliabile utilizzare i rollup. Suite di rapporti globali quasi il doppio del numero di chiamate server effettuate.
* È sufficiente riportare un traffico di alto livello tra tutte le suite? Se i visitatori deduplicati sono un requisito, prendete in considerazione l'implementazione di una suite di rapporti globale.
* Sono importanti eventi di percorso e conversione/successo tra domini diversi? Se le campagne intersito vengono utilizzate in modo intensivo, è consigliabile implementare una suite di rapporti globale.
* La visualizzazione dei dati totali del sito è sensibile all'ora? Le singole suite di rapporti riferiscono ancora in tempo reale. Se la visualizzazione dei totali della suite di rapporti il giorno successivo è adeguata, si consiglia di eseguire dei rollup.
* Esiste una grande quantità di dati storici fruibili? Le suite di rapporti globali non possono generare rapporti retroattivi; i rollup sono consigliati se i dati storici sono importanti.
* Data warehouse e analisi ad hoc sono essenziali per completare la generazione di rapporti? In tal caso, è consigliabile una suite di rapporti globale.

Nessuna delle due scelte influisce sulle singole suite di rapporti. Considerate attentamente i pro e i contro prima di determinare quali preferite.
