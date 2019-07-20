---
description: L'analisi delle pagine in tempo reale (Modalità Dal vivo) consente di ottenere risultati con granularità minuti in tempo reale.
seo-description: L'analisi delle pagine in tempo reale (Modalità Dal vivo) consente di ottenere risultati con granularità minuti in tempo reale.
seo-title: Analisi delle pagine in tempo reale (Live)
solution: Analytics
title: Analisi delle pagine in tempo reale (Live)
topic: Activity map
uuid: a 3 faa 9 bd -73 d 8-48 b 3-be 2 b-f 818 ed 7456 fb
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Analisi delle pagine in tempo reale (Live)

L'analisi delle pagine in tempo reale (Modalità Dal vivo) consente di ottenere risultati con granularità minuti in tempo reale.

Activity Map ora visualizza dati analitici in incrementi da 1 a 15 minuti per monitorare la popolarità dei collegamenti in base alla micro-tendenza per le pagine selezionate. Questo è particolarmente importante per la pubblicazione delle aziende nel tracciamento e la risposta all'interesse o alla diminuzione dell'interesse dei racconti e per monitorare il flusso di traffico in tempo reale.

Come proprietario del contenuto di un sito, parte del lavoro è capire quando promuovere e rimuovere i contenuti e mantenere la nostra esperienza costantemente rilevante. I dati in tempo reale sono il bagnamento di questa responsabilità. Se al momento è possibile capire quali collegamenti e contenuti stanno tendenze, potete agire in modo rapido e decisivo per mantenere i lettori e i clienti coinvolti nel marchio.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

## Data latency as a result of A4T configuration {#section_806CE36354FC4C539A0DED9266A5C704}

Dopo che l'integrazione con T 4 T è abilitata in Adobe Target, si possono verificare ulteriori 5-10 minuti di latenza in Adobe Analytics. Questo aumento della latenza consente la memorizzazione dei dati da Analytics e Target nello stesso hit, con conseguente possibilità di suddividere i test per pagina e sezione del sito.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per lo streaming live, i rapporti in tempo reale e le richieste API e per i dati correnti per le variabili di traffico, vengono ritardati solo gli insiemi con ID di dati supplementari.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

Be aware that the latency increase starts after you implement the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), even if you have not fully implemented this integration.
