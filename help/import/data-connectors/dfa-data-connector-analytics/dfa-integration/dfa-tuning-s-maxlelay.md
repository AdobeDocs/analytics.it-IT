---
description: L'implementazione di un DFA riuscito implica l'ottimizzazione di s. maxdelay per il sito specifico.
keywords: DFA
seo-description: L'implementazione di un DFA riuscito implica l'ottimizzazione di s. maxdelay per il sito specifico.
seo-title: Ottimizzazione s. maxdelay
solution: Analytics
title: Ottimizzazione s. maxdelay
topic: Connettori dati
uuid: 7640 af 26-6 ac 6-427 e -9 cfc -932 c 86 ccf 5 ab
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Ottimizzazione s. maxdelay{#tuning-s-maxdelay}

L'implementazione di un DFA riuscito implica l'ottimizzazione di s. maxdelay per il sito specifico.

In generale, la decisione di alzare o abbassare *`s.maxDelay`* implica un compromesso tra ottenere ulteriori dati sui visitatori DFA e rischiare di raccogliere i dati dei visitatori Adobe. Aumentando *`s.maxDelay`* i dati dei visitatori DFA, ma (posizionati troppo alto) potrebbero compromettere la raccolta dei dati dei visitatori Adobe. Decreasing s. maxdelay assicura la raccolta dei dati dei visitatori di Adobe, ma potrebbe perdere i dati dei visitatori DFA.

*`s.maxDelay`* non racchiude più semplicemente il tempo nella comunicazione di rete per contattare DFA; Inoltre, rappresenta i ritardi del browser per attivare e valutare il javascript da cui si basano tali comunicazioni. poiché il modulo Integra inizia il *`s.maxDelay`* timer dopo aver inserito l'elemento HTML nel DOM che estrae i dati dal server DFA Floodlight. Il tempo necessario affinché il browser inizi effettivamente la richiesta HTTP basata su questo nuovo elemento HTML varia in base ad altre immagini o file javascript che vengono caricati simultaneamente, velocità del computer dei visitatori e implementazioni del browser specifiche. Inoltre, quando vengono recuperati i dati JSON dal server DFA Floodlight, il browser deve valutare javascript. Questa situazione viene nuovamente controllata dal browser e può essere ritardata se ci sono grandi quantità di codice javascript in esecuzione contemporaneamente o molte richieste javascript asincrone.

Tenendo presente questa situazione, *`s.maxDelay`* è necessario impostare in base alla complessità della pagina di destinazione più la quantità di ritardo di rete con DFA. In alcuni siti, un possibile modo per ridurre la complessità consiste nell'attivare il codice di raccolta Adobe prima del caricamento della pagina, in modo che nel browser sia presente meno tempo nel momento in cui viene richiesto il server Floodlight.

La variabile Timeout è assolutamente necessaria per l'ottimizzazione *`s.maxDelay`*, perché viene incrementata ogni volta che viene raggiunto il timeout s. maxdelay. Per decidere se aumentare o diminuire *`s.maxDelay`* la procedura consigliamo di seguire questo processo:

1. Raccogliere più giorni di dati impostati *`s.maxDelay`* su un valore specifico.
1. Eseguire un' [!DNL Daily Unique Visitors Report] operazione per l'intervallo di tempo.
1. Esegui l'operazione [!DNL Timeout Event Report] per controllare il numero di timeout che arrivano. Ricorda che un timeout viene raccolto solo una volta per visitatore.

Sono disponibili le cifre a mano,

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

Tieni presente che la percentuale Timeout sta considerando tutti i visitatori del sito. Alcuni di questi visitatori non sarebbero stati legati a DFA, pertanto il timeout è fuorviante. Per migliorare questo calcolo, un'altra analisi potrebbe considerare solo i visitatori univoci delle pagine insieme al `clickThroughParam` set (ad esempio `?CID=1`,). con una maggiore precisione.

Se la percentuale Timeout è molto bassa, diminuisci *`s.maxDelay`*. Se è molto alta, aumentate *`s.maxDelay`*. Quando si riduce *`s.maxDelay`*, si desidera ripetere l'operazione [!DNL Timeout Report] per garantire che i timeout non siano aumentati notevolmente. Quando si aumenta *`s.maxDelay`*, è necessario eseguire un'operazione [!DNL Page Views Report] per fare in modo che le visualizzazioni delle pagine non vengano ritirate a causa di dati persi. Ogni volta *`s.maxDelay`* viene modificato il rilevamento dei dati per più giorni, per fare in modo che i dati rappresentino una tendenza, non solo una fluttuazione giornaliera.

L'impostazione ottimale è *`s.maxDelay`* il punto in cui la percentuale di timeout viene ridotta a icona mentre le visualizzazioni di pagina non vengono rilasciate.

I timeout dovrebbero diminuire quando passate alla versione 2.0 dell'integrazione, a causa delle eliminazioni di 302 reindirizzamenti. I risultati iniziali con i client beta hanno visualizzato una riduzione coerente nei timeout e quindi più dati DFA raccolti
