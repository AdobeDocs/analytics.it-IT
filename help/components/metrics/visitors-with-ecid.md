---
title: Visitatori con Experience Cloud ID
description: Il numero di visitatori unici che utilizzano il servizio Adobe Experience Cloud ID.
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 2%

---

# Visitatori con Experience Cloud ID

La metrica &quot;Visitatori con ID Experience Cloud&quot; mostra il numero di visitatori unici identificati per Adobe utilizzando il [servizio ID Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html). Questa dimensione è utile da confrontare con la metrica [Visitatori unici](unique-visitors.md) per essere certi che la maggior parte dei visitatori del sito utilizzi il servizio ID. Se una grande parte dei visitatori non usa i cookie del servizio ID, può indicare un problema all&#39;interno dell&#39;implementazione.

>[!NOTE]
>
>Questa metrica è particolarmente importante per il debug se utilizzi più servizi Experience Cloud, come Adobe Target o Adobe Audience Manager. I segmenti condivisi tra i prodotti Experience Cloud non includono i visitatori senza un ID Experience Cloud.

## Calcolo di questa metrica

Questa metrica è basata sulla metrica [Visitatori unici](unique-visitors.md), tranne per i soli individui identificati utilizzando la stringa di query `mid` (basata sul cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html)).

## Debug della configurazione dell&#39;ID Experience Cloud

La metrica &quot;Visitatori con ID Experience Cloud&quot; può essere utile per risolvere eventuali integrazioni di Experience Cloud o per identificare le aree del sito in cui non è stato implementato il servizio ID.

Trascina &quot;Visitatori con ID Experience Cloud&quot; affiancati a Visitatori univoci per confrontarli:

![Confronto di visitatori univoci](assets/metric-mcvid1.png)

In questo esempio, noterai che ogni pagina ha lo stesso numero di &quot;Visitatori unici&quot; di &quot;Visitatori con un ID Experience Cloud&quot;. Tuttavia, il numero totale di Visitatori unici è maggiore del numero totale di Visitatori con ID Experience Cloud. Puoi creare una [metrica calcolata](../c-calcmetrics/cm-overview.md) per scoprire quali pagine non impostano il servizio ID. È possibile utilizzare la seguente definizione:

![Definizione della metrica calcolata](assets/metric-mcvid2.png)

Aggiungendo la metrica calcolata al rapporto, puoi ordinare il rapporto Pagine in modo che vengano visualizzate le pagine con il numero più elevato di visitatori senza un MCID:

![Pagine senza servizio ID](assets/metric-mcvid3.png)

L’elemento di dimensione &quot;Visualizzazioni rapide del prodotto&quot; non è implementato correttamente con il servizio Identity. Puoi lavorare con i team appropriati all’interno della tua organizzazione per aggiornare queste pagine il prima possibile. Puoi creare un rapporto simile con qualsiasi tipo di dimensione, ad esempio [Tipo di browser](../dimensions/browser-type.md), [Sezione sito](../dimensions/site-section.md) o qualsiasi [eVar](../dimensions/evar.md).
