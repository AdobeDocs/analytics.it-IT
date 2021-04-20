---
description: L’analisi delle pagine in tempo reale (modalità Live) consente di ottenere risultati con granularità al minuto in tempo reale.
title: Analisi delle pagine in tempo reale (Live)
feature: Activity Map
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 32%

---


# Analisi delle pagine in tempo reale (modalità Live)

L’analisi delle pagine in tempo reale (modalità Live) consente di ottenere risultati con granularità al minuto in tempo reale.

Activity Map ora visualizza i dati analitici in incrementi di 1 minuto-15 minuti per monitorare la popolarità dei collegamenti in base alle micro-tendenze per le pagine selezionate. Questo è particolarmente importante per le aziende editoriali nel tracciamento e nel rispondere all&#39;interesse crescente o decrescente per le storie e per monitorare il flusso di traffico in tempo reale.

In qualità di proprietario dei contenuti del sito, parte del tuo lavoro consiste nel capire quando promuovere e rimuovere contenuti e mantenere la nostra esperienza costantemente rilevante. I dati in tempo reale sono la linfa vitale di questa responsabilità. Se riesci a capire quali collegamenti e contenuti sono tendenze in questo momento, puoi agire in modo rapido e deciso per mantenere i lettori e i clienti coinvolti nel tuo marchio.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

Se desideri verificare quale elemento viene selezionato principalmente in modalità Live:

1. Seleziona il periodo di tempo sulla linea di tendenza della barra degli strumenti **[!UICONTROL Live Mode]** da analizzare.
1. Fai clic sull’icona &quot;Occhio&quot; nella barra degli strumenti per accedere alla tabella dei rapporti Collegamenti .
1. Ordina la tabella in base al collegamento.

## Latenza dei dati a seguito della configurazione di A4T

Una volta abilitato l’ [Integrazione A4T](https://docs.adobe.com/content/help/it-IT/target/using/integrate/a4t/a4t.html) in Adobe Target, si verifica una latenza aggiuntiva di 5-10 minuti in Adobe Analytics. Questo aumento della latenza consente la memorizzazione dei dati da Analytics e Target nello stesso hit, con conseguente possibilità di suddividere i test per pagina e sezione del sito.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per lo streaming live, i rapporti in tempo reale e le richieste API e per i dati correnti per le variabili di traffico, vengono ritardati solo gli insiemi con ID di dati supplementari.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

L’aumento della latenza inizia dopo l’implementazione del [servizio Identity](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html), anche se questa integrazione non è stata completamente implementata.

Maggiori informazioni [qui](/help/analyze/activity-map/activitymap-standard-live.md).