---
title: Visitatori con Experience Cloud ID
description: Il numero di visitatori univoci che utilizzano il servizio Adobe Experience Cloud ID.
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 4%

---

# Visitatori con Experience Cloud ID

Il &#39;Visitatori con ID Experience Cloud&#39; [metrica](overview.md) mostra il numero di visitatori univoci identificati da Adobe tramite il [servizio ID Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). Questa metrica è utile da confrontare con la metrica [Visitatori univoci](unique-visitors.md) per assicurarsi che la maggior parte dei visitatori del sito utilizzi il servizio ID. Se una grande parte dei visitatori non utilizza i cookie del servizio ID, può indicare un problema all&#39;interno dell&#39;implementazione.

>[!NOTE]
>
>Questa metrica è particolarmente importante per il debug se utilizzi più servizi Experience Cloud, come Adobe Target o Adobe Audience Manager. I segmenti condivisi tra i prodotti Experience Cloud non includono i visitatori senza un ID Experience Cloud.

## Come è calcolata questa metrica

Questa metrica si basa sulla metrica [Visitatori univoci](unique-visitors.md), tranne per il fatto che include solo gli individui identificati utilizzando la stringa di query `mid` (basata sul cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it)).

## Debug della configurazione dell’ID Experience Cloud

La metrica &quot;Visitatori con ID Experience Cloud&quot; può essere utile per risolvere problemi relativi alle integrazioni Experience Cloud o per identificare aree del sito in cui non è implementato il servizio ID.

Trascina &quot;Visitatori con ID Experience Cloud&quot; accanto a Visitatori univoci per confrontarli:

![Confronto visitatore univoco](assets/metric-mcvid1.png)

In questo esempio, tieni presente che ogni pagina ha lo stesso numero di &quot;Visitatori univoci&quot; di &quot;Visitatori con un ID Experience Cloud&quot;. Tuttavia, il numero totale di Visitatori univoci è maggiore del numero totale di Visitatori con ID Experience Cloud. Puoi creare una [metrica calcolata](../c-calcmetrics/cm-overview.md) per individuare le pagine che non impostano il servizio ID. Puoi utilizzare la seguente definizione:

![Definizione metrica calcolata](assets/metric-mcvid2.png)

Aggiungendo la metrica calcolata al rapporto, puoi ordinare il rapporto Pagine in modo da visualizzare le pagine con il maggior numero di visitatori senza un MCID:

![Pagine senza servizio ID](assets/metric-mcvid3.png)

L’elemento dimensione &quot;Visualizzazioni rapide del prodotto&quot; non è implementato correttamente con il servizio Identity. Puoi lavorare con i team appropriati all’interno della tua organizzazione per aggiornare queste pagine il prima possibile. È possibile creare un report simile con qualsiasi tipo di dimensione, ad esempio [Tipo browser](../dimensions/browser-type.md), [Sezione sito](../dimensions/site-section.md) o [eVar](../dimensions/evar.md).
