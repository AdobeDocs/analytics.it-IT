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
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Tuning s.maxDelay{#tuning-s-maxdelay}

L'implementazione di un DFA riuscito implica l'ottimizzazione di s. maxdelay per il sito specifico.

In general, the decision to raise or lower *`s.maxDelay`* involves a tradeoff between obtaining more DFA visitor data and endangering collecting Adobe visitor data. Increasing *`s.maxDelay`* obtains more DFA visitor data, but (placed excessively high) could endanger the collection of Adobe visitor data. Decreasing s. maxdelay assicura la raccolta dei dati dei visitatori di Adobe, ma potrebbe perdere i dati dei visitatori DFA.

*`s.maxDelay`* non racchiude più semplicemente il tempo nella comunicazione di rete per contattare DFA; Inoltre, rappresenta i ritardi del browser per attivare e valutare il javascript da cui si basano tali comunicazioni. This is because the Integrate module begins the *`s.maxDelay`* timer after it has inserted the HTML element in to the DOM which pulls the data from the DFA Floodlight server. Il tempo necessario affinché il browser inizi effettivamente la richiesta HTTP basata su questo nuovo elemento HTML varia in base ad altre immagini o file javascript che vengono caricati simultaneamente, velocità del computer dei visitatori e implementazioni del browser specifiche. Inoltre, quando vengono recuperati i dati JSON dal server DFA Floodlight, il browser deve valutare javascript. Questa situazione viene nuovamente controllata dal browser e può essere ritardata se ci sono grandi quantità di codice javascript in esecuzione contemporaneamente o molte richieste javascript asincrone.

With this in mind, *`s.maxDelay`* needs to be set dependent up on the complexity of the landing page plus the amount of network delay with DFA. In alcuni siti, un possibile modo per ridurre la complessità consiste nell'attivare il codice di raccolta Adobe prima del caricamento della pagina, in modo che nel browser sia presente meno tempo nel momento in cui viene richiesto il server Floodlight.

The Timeout variable is absolutely required when tuning *`s.maxDelay`*, because it is incremented every time the s.maxDelay timeout is reached. When deciding whether to increase or decrease *`s.maxDelay`* we recommend following this process:

1. Collect several days of data with *`s.maxDelay`* set to a particular value.
1. Run a [!DNL Daily Unique Visitors Report] for the time range.
1. Run the [!DNL Timeout Event Report] to check the number of timeouts that are coming through. Ricorda che un timeout viene raccolto solo una volta per visitatore.

Sono disponibili le cifre a mano,

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

Tieni presente che la percentuale Timeout sta considerando tutti i visitatori del sito. Alcuni di questi visitatori non sarebbero stati legati a DFA, pertanto il timeout è fuorviante. To improve this computation, another analysis could consider only unique visitors to pages with the `clickThroughParam` set (for example, `?CID=1`). con una maggiore precisione.

If the Timeout Percentage is very low, consider decreasing *`s.maxDelay`*. If it is very high, increase *`s.maxDelay`*. When decreasing *`s.maxDelay`*, you will want to rerun the [!DNL Timeout Report] to ensure that timeouts have not dramatically increased. When increasing *`s.maxDelay`*, you will want to run a [!DNL Page Views Report] to make sure page views aren’t falling out due to lost data. Each time *`s.maxDelay`* is changed observe the data for several days in order to ensure that the data represents a trend, and not just a day-to-day fluctuation.

The optimal setting for *`s.maxDelay`* is the point at which the timeout percentage is minimized while Page Views do not drop off.

I timeout dovrebbero diminuire quando passate alla versione 2.0 dell'integrazione, a causa delle eliminazioni di 302 reindirizzamenti. I risultati iniziali con i client beta hanno visualizzato una riduzione coerente nei timeout e quindi più dati DFA raccolti
