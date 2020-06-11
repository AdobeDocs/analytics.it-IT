---
title: Visitatori con Experience Cloud ID
description: Il numero di visitatori unici che utilizzano il servizio Adobe Experience Cloud ID.
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 7%

---


# Visitatori con Experience Cloud ID

La metrica &quot;Visitatori con Experience Cloud ID&quot; mostra il numero di visitatori unici identificati da Adobe tramite il servizio [](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html)Experience Cloud ID. Questa dimensione è utile per confrontare con la metrica Visitatori [](unique-visitors.md) univoci per essere certi che la maggior parte dei visitatori del sito utilizzi il servizio ID. Se una grande parte dei visitatori non utilizza i cookie del servizio ID, può indicare un problema all’interno dell’implementazione.

>[!NOTE] Questa metrica è particolarmente importante per il debug se utilizzi più servizi Experience Cloud, come Adobe Target o Adobe Audience Manager. I segmenti condivisi tra i prodotti Experience Cloud non includono i visitatori senza un Experience Cloud ID.

## Modalità di calcolo di questa metrica

Questa metrica è basata sulla metrica Visitatori [](unique-visitors.md) unici, ma include solo gli individui identificati utilizzando la stringa di `mid` query (basata sul [`s_ecid`](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-analytics.html) cookie).

## Esegui il debug della configurazione Experience Cloud ID

La metrica &quot;Visitatori con Experience Cloud ID&quot; può essere utile per risolvere eventuali integrazioni Experience Cloud o per identificare le aree del sito in cui non è stato implementato il servizio ID.

Trascina i &#39;Visitatori con Experience Cloud ID&#39; affiancati da Visitatori univoci per confrontarli:

![Confronto dei visitatori univoci](assets/metric-mcvid1.png)

In questo esempio, nota che ogni pagina ha lo stesso numero di &quot;Visitatori unici&quot; di &quot;Visitatori con un Experience Cloud ID&quot;. Tuttavia, il numero totale di Visitatori unici è maggiore del numero totale di Visitatori con Experience Cloud ID. Puoi creare una metrica [](../c-calcmetrics/cm-overview.md) calcolata per scoprire quali pagine non configurano il servizio ID. È possibile utilizzare la seguente definizione:

![Definizione della metrica calcolata](assets/metric-mcvid2.png)

Aggiungendo la metrica calcolata al rapporto, puoi ordinare il rapporto Pagine in modo che vengano visualizzate le pagine con il numero più elevato di visitatori senza un MCID:

![Pagine senza servizio ID](assets/metric-mcvid3.png)

Il valore della dimensione &quot;Visualizzazioni rapide del prodotto&quot; non è correttamente implementato con il servizio identità. Potete collaborare con i team appropriati all’interno dell’organizzazione per aggiornare queste pagine il prima possibile. È possibile creare un rapporto simile con qualsiasi tipo di dimensione, ad esempio tipo [di](../dimensions/browser-type.md)browser, sezione [](../dimensions/site-section.md)Sito o qualsiasi [eVar](../dimensions/evar.md).
