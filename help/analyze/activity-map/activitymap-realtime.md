---
description: L’analisi delle pagine in tempo reale (modalità Live) consente di ottenere risultati con granularità al minuto in tempo reale.
title: Analisi delle pagine in tempo reale (Live)
feature: Activity Map
role: User, Admin
exl-id: 29ccd89e-d82b-41d4-a940-addc6656b5ec
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 31%

---

# Analisi delle pagine in tempo reale (modalità Live)

L’analisi delle pagine in tempo reale (modalità Live) consente di ottenere risultati con granularità al minuto in tempo reale.

Activity Map ora visualizza i dati analitici con incrementi da 1 minuto a 15 minuti per monitorare la popolarità dei collegamenti in base alle micro-tendenze per le pagine selezionate. Questo è particolarmente importante per le aziende editoriali che devono tenere traccia delle notizie e rispondere a un interesse crescente o decrescente e monitorare il flusso di traffico in tempo reale.

In qualità di proprietario di contenuti del sito, parte del tuo lavoro consiste nel capire quando promuovere e rimuovere contenuti e mantenere la nostra esperienza sempre pertinente. I dati in tempo reale sono la linfa vitale di questa responsabilità. Se sei in grado di capire quali collegamenti e contenuti hanno tendenza in questo momento, puoi agire in modo rapido e deciso per mantenere i lettori e i clienti coinvolti con il tuo marchio.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

Se desideri verificare quale elemento viene fatto clic principalmente in modalità Live:

1. Selezionare il periodo di tempo sulla barra degli strumenti **[!UICONTROL Live Mode]** linea di tendenza da analizzare.
1. Fai clic sull’icona &quot;Occhio&quot; nella barra degli strumenti per accedere alla tabella dei rapporti sui collegamenti.
1. Ordina la tabella in base al collegamento.

## Latenza dei dati come risultato della configurazione A4T

Dopo il [Integrazione di A4T](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=it) è abilitato in Adobe Target, si verifica una latenza aggiuntiva di 5-10 minuti in Adobe Analytics. Questo aumento della latenza consente la memorizzazione dei dati da Analytics e Target nello stesso hit, con conseguente possibilità di suddividere i test per pagina e sezione del sito.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per lo streaming live, i rapporti in tempo reale e le richieste API e per i dati correnti per le variabili di traffico, vengono ritardati solo gli insiemi con ID di dati supplementari.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

Tieni presente che l&#39;aumento della latenza inizia dopo l&#39;implementazione di [Servizio identità](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it), anche se non hai implementato completamente questa integrazione.

Ulteriori informazioni [qui](/help/analyze/activity-map/activitymap-standard-live.md).
