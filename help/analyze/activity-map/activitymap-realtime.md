---
description: L'analisi delle pagine in tempo reale (modalità Live) consente di ottenere risultati con granularità minima in tempo reale.
seo-description: L'analisi delle pagine in tempo reale (modalità Live) consente di ottenere risultati con granularità minima in tempo reale.
seo-title: Analisi delle pagine in tempo reale (Live)
solution: Analytics
title: Analisi delle pagine in tempo reale (Live)
topic: Activity Map
uuid: a3faa9bd-73d8-48b3-be2b-f818ed7456fb
translation-type: tm+mt
source-git-commit: 38eb2298a2fc351591542bdfac9016ce4497c484

---


# Analisi delle pagine in tempo reale (Live)

L'analisi delle pagine in tempo reale (modalità Live) consente di ottenere risultati con granularità minima in tempo reale.

Activity Map ora visualizza i dati analitici con incrementi di 1-15 minuti per monitorare la popolarità dei collegamenti in base alle micro-tendenze per le pagine selezionate. Ciò è particolarmente importante per le aziende di pubblicazione nel tracciamento e nella risposta all'interesse crescente o decrescente per le storie e per monitorare il flusso di traffico in tempo reale.

In qualità di proprietario dei contenuti del sito, parte del tuo lavoro consiste nel capire quando promuovere e rimuovere contenuti e mantenere la nostra esperienza costantemente rilevante. I dati in tempo reale sono la linfa vitale di questa responsabilità. Se puoi capire quali collegamenti e contenuti sono più importanti in questo momento, puoi agire in modo rapido e deciso per coinvolgere lettori e clienti con il tuo marchio.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

## Latenza dei dati come risultato della configurazione A4T {#section_806CE36354FC4C539A0DED9266A5C704}

Dopo l'abilitazione dell'integrazione A4T in Adobe Target, si verificherà una latenza aggiuntiva di 5-10 minuti in Adobe Analytics. Questo aumento della latenza consente la memorizzazione dei dati da Analytics e Target nello stesso hit, con conseguente possibilità di suddividere i test per pagina e sezione del sito.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per lo streaming live, i rapporti in tempo reale e le richieste API e per i dati correnti per le variabili di traffico, vengono ritardati solo gli insiemi con ID di dati supplementari.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

Be aware that the latency increase starts after you implement the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), even if you have not fully implemented this integration.
