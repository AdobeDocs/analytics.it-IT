---
title: Visitatori con Experience Cloud ID
description: Il numero di visitatori univoci che utilizzano il servizio Adobe Experience Cloud ID.
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
TQID: https://experienceleague.adobe.com/CCk7FDZhZ3mFYXtAggcxnAjvJoJp5zMf0NNk5w0tVY8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: e6c28e30-8689-4bf4-8fa8-561343d308a9
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 378
ht-degree: 8%

---

# Visitatori con Experience Cloud ID

La metrica &#39;Visitatori con ID Experience Cloud&#39; [metric](overview.md) mostra il numero di visitatori univoci identificati da Adobe tramite il servizio [Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). Questa metrica è utile da confrontare con la metrica [Visitatori univoci](unique-visitors.md) per assicurarsi che la maggior parte dei visitatori del sito utilizzi il servizio ID. Se una grande parte dei visitatori non utilizza i cookie del servizio ID, può indicare un problema all&#39;interno dell&#39;implementazione.

>[!NOTE]
>
>Questa metrica è particolarmente importante per il debug se si utilizzano più servizi CX Enterprise, come Adobe Target o Adobe Audience Manager. I segmenti condivisi tra i prodotti aziendali CX non includono i visitatori senza un Experience Cloud ID.

## Come è calcolata questa metrica

Questa metrica si basa sulla metrica [Visitatori univoci](unique-visitors.md), tranne per il fatto che include solo gli individui identificati utilizzando la stringa di query `mid` (basata sul cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it)).

## Debug della configurazione dell’Experience Cloud ID

La metrica &quot;Visitatori con Experience Cloud ID&quot; può essere utile per risolvere problemi relativi alle integrazioni CX Enterprise o per identificare aree del sito in cui non è stato implementato il servizio ID.

Trascina &quot;Visitatori con Experience Cloud ID&quot; accanto a Visitatori univoci per confrontarli:

![Confronto visitatore univoco](assets/metric-mcvid1.png)

In questo esempio, tieni presente che ogni pagina ha lo stesso numero di &quot;Visitatori univoci&quot; di &quot;Visitatori con un Experience Cloud ID&quot;. Tuttavia, il numero totale di Visitatori univoci è maggiore del numero totale di Visitatori con Experience Cloud ID. Puoi creare una [metrica calcolata](../calculated-metrics/cm-overview.md) per individuare le pagine che non impostano il servizio ID. Puoi utilizzare la seguente definizione:

![Definizione metrica calcolata](assets/metric-mcvid2.png)

Aggiungendo la metrica calcolata al rapporto, puoi ordinare il rapporto Pagine in modo da visualizzare le pagine con il maggior numero di visitatori senza un MCID:

![Pagine senza servizio ID](assets/metric-mcvid3.png)

L’elemento dimensione &quot;Visualizzazioni rapide del prodotto&quot; non è implementato correttamente con il servizio Identity. Puoi lavorare con i team appropriati all’interno della tua organizzazione per aggiornare queste pagine il prima possibile. È possibile creare un report simile con qualsiasi tipo di dimensione, ad esempio [Tipo browser](../dimensions/browser-type.md), [Sezione sito](../dimensions/site-section.md) o qualsiasi [eVar](../dimensions/evar.md).
