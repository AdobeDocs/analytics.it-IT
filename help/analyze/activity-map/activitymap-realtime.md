---
description: L'analisi delle pagine in tempo reale (modalità Live) consente di ottenere risultati con granularità minima in tempo reale.
title: Analisi delle pagine in tempo reale (Live)
topic: Activity map
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Analisi delle pagine in tempo reale (modalità Live)

L&#39;analisi delle pagine in tempo reale (modalità Live) consente di ottenere risultati con granularità minima in tempo reale.

Activity Map ora visualizza i dati analitici in incrementi di 1/15 minuti per monitorare la popolarità dei collegamenti in base alle micro-tendenze per le pagine selezionate. Ciò è particolarmente importante per le aziende di pubblicazione nel tracciamento e nella risposta all&#39;interesse crescente o decrescente per le storie e per monitorare il flusso di traffico in tempo reale.

In qualità di proprietario dei contenuti del sito, parte del tuo lavoro consiste nel capire quando promuovere e rimuovere i contenuti e mantenere la nostra esperienza costantemente rilevante. I dati in tempo reale sono la linfa vitale di questa responsabilità. Se puoi capire quali collegamenti e contenuti sono più importanti in questo momento, puoi agire in modo rapido e deciso per coinvolgere lettori e clienti con il tuo marchio.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

Se desiderate verificare su quale elemento viene fatto clic principalmente in modalità Live:

1. Selezionare il periodo di tempo sulla linea di tendenza della barra degli strumenti **[!UICONTROL Live Mode]** da analizzare.
1. Fate clic sull’icona &quot;Occhio&quot; nella barra degli strumenti per accedere alla tabella dei rapporti Collegamenti.
1. Ordinare la tabella in base al collegamento.

## Latenza dei dati come risultato della configurazione A4T

Dopo l&#39;abilitazione dell&#39;integrazione [](https://docs.adobe.com/content/help/it-IT/target/using/integrate/a4t/a4t.translate.html) A4T in Adobe Target, si verificherà una latenza aggiuntiva di 5-10 minuti in Adobe Analytics. Questo aumento della latenza consente la memorizzazione dei dati da Analytics e Target nello stesso hit, con conseguente possibilità di suddividere i test per pagina e sezione del sito.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per lo streaming live, i rapporti in tempo reale e le richieste API e per i dati correnti per le variabili di traffico, vengono ritardati solo gli insiemi con ID di dati supplementari.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

Be aware that the latency increase starts after you implement the [Identity Service](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html), even if you have not fully implemented this integration.

Maggiori informazioni [qui](/help/analyze/activity-map/activitymap-standard-live.md).