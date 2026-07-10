---
title: Visitatori con Experience Cloud ID
description: Il numero di visitatori univoci che utilizzano un ECID.
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
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 355
ht-degree: 6%

---

# Visitatori con Experience Cloud ID

La [metrica](overview.md) &#39;[!UICONTROL Visitors with Experience Cloud ID]&#39; mostra il numero di visitatori univoci identificati da Adobe con un ECID (utilizzando il [Servizio ID visitatori](https://experienceleague.adobe.com/en/docs/id-service/using/home) o il [Servizio Experience Platform Identity](https://experienceleague.adobe.com/it/docs/experience-platform/identity/home)). Questa metrica è utile da confrontare con la metrica [Visitatori univoci](unique-visitors.md) per assicurarsi che la maggior parte dei visitatori del sito utilizzi un ECID. Se un’ampia porzione di visitatori non utilizza questo identificatore, può indicare un problema all’interno dell’implementazione.

>[!NOTE]
>
>Questa metrica è particolarmente importante per il debug se si utilizzano più servizi CX Enterprise, come Adobe Target o Adobe Audience Manager. I segmenti condivisi tra i prodotti aziendali CX non includono i visitatori senza un ECID.

## Come è calcolata questa metrica

Questa metrica si basa sulla metrica [Visitatori univoci](unique-visitors.md), tranne per il fatto che include solo gli individui identificati utilizzando la stringa di query `mid` (basata sul cookie [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)).

## Eseguire il debug della configurazione ECID

La metrica &#39;[!UICONTROL Visitors with Experience Cloud ID]&#39; può essere utile per la risoluzione dei problemi relativi alle integrazioni CX Enterprise o per l&#39;identificazione di aree del sito in cui non è implementato il servizio ID visitatori o il servizio Experience Platform Identity.

Trascina &#39;[!UICONTROL Visitors with Experience Cloud ID]&#39; affiancato a Visitatori univoci per confrontarli:

![Confronto visitatore univoco](assets/metric-mcvid1.png)

In questo esempio, si noti che ogni pagina ha lo stesso numero di &#39;[!UICONTROL Unique Visitors]&#39; di &#39;[!UICONTROL Visitors with Experience Cloud ID]&#39;. Tuttavia, il numero totale di &#39;[!UICONTROL Unique Visitors]&#39; è maggiore del numero totale di &#39;[!UICONTROL Visitors with Experience Cloud ID]&#39;. Puoi creare una [metrica calcolata](../calculated-metrics/cm-overview.md) per individuare le pagine che non utilizzano un ECID utilizzando la seguente definizione:

![Definizione metrica calcolata](assets/metric-mcvid2.png)

Aggiungendo la metrica calcolata al rapporto, puoi ordinare il rapporto Pagine in modo da visualizzare le pagine con il maggior numero di visitatori senza un ECID:

![Pagine senza ECID](assets/metric-mcvid3.png)

L’elemento dimensionale &quot;Visualizzazioni rapide del prodotto&quot; non è implementato correttamente con un ECID. Puoi lavorare con i team appropriati all’interno della tua organizzazione per aggiornare queste pagine il prima possibile. È possibile creare un report simile con qualsiasi tipo di dimensione, ad esempio [Tipo browser](../dimensions/browser-type.md), [Sezione sito](../dimensions/site-section.md) o qualsiasi [eVar](../dimensions/evar.md).
