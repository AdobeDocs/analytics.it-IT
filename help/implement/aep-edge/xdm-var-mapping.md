---
title: Mappatura della variabile oggetto XDM su Adobe Analytics
description: Visualizza quali campi XDM mappati automaticamente da Edge alle variabili di Analytics.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 4c472d9a99f15ed253b68124aa31bdc88554d9a5
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 68%

---

# Mappatura della variabile oggetto XDM su Adobe Analytics

La tabella seguente mostra le variabili XDM mappate automaticamente da Adobe Experience Platform Edge Network in Adobe Analytics. Se utilizzi questi percorsi di campo XDM, non è necessaria alcuna configurazione aggiuntiva per inviare dati ad Adobe Analytics. Questi campi sono inclusi nel **[!UICONTROL Adobe Analytics ExperienceEvent Template]** gruppo di campi. L’utilizzo di questi campi è consigliato se intendi inviare dati sia ad Adobe Analytics che a Adobe Experience Platform.

Se la tua organizzazione prevede di passare al Customer Journey Analytics, l’Adobe consiglia invece di utilizzare `data` oggetto per inviare dati direttamente ad Adobe Analytics senza essere conforme a uno schema. Questa strategia consente all’organizzazione di utilizzare il proprio schema, anziché il [!UICONTROL Adobe Analytics ExperienceEvent Template] (meno applicabile al Customer Journey Analytics). Consulta [Mappatura della variabile dell’oggetto dati su Adobe Analytics](data-var-mapping.md) per una tabella di mappatura simile.

## Priorità di valore

La maggior parte dei campi oggetto XDM in questa tabella coincidono con un [campo oggetto dati](data-var-mapping.md). Se imposti sia un determinato campo oggetto XDM che il relativo campo oggetto dati, il campo oggetto dati ha la priorità. Se utilizzi sia il campo oggetto XDM che il campo oggetto dati, l’Adobe consiglia di impostare eventi personalizzati utilizzando il campo oggetto dati. Se il campo `data.__adobe.analytics.events` sovrascrive tutti i campi oggetto XDM relativi agli eventi di e-commerce e personalizzati.

## Mappatura campo oggetto XDM

Gli aggiornamenti precedenti a questa tabella si trovano nella [cronologia dei commit su GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/xdm-var-mapping.md) di questa pagina.

| Percorso campo XDM | Variabile e descrizione di Analytics |
| --- | --- |
| `xdm.application.isClose` | Consente di definire la metrica del ciclo di vita mobile [Arresti anomali](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isInstall` | Consente di determinare quando aumentare la metrica del ciclo di vita mobile [Primi avvii](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isLaunch` | Consente di determinare quando aumentare la metrica del ciclo di vita mobile [Primi avvii](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.closeType` | Determina se un evento di chiusura è un arresto anomalo o meno. I valori validi includono `close` (una sessione del ciclo di vita termina ed è stato ricevuto un evento di pausa per la sessione precedente) e `unknown` (una sessione del ciclo di vita termina senza un evento di pausa). Aiuta a impostare la metrica del ciclo di vita mobile [Arresti anomali](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) metrica. |
| `xdm.application.isInstall` | La metrica del ciclo di vita mobile [Installazioni](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isLaunch` | La metrica del ciclo di vita mobile [Lanci](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.name` | Aiuta a impostare la dimensione del ciclo di vita mobile [ID app](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.isUpgrade` | La metrica del ciclo di vita mobile [Aggiornamenti](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.version` | Aiuta a impostare la dimensione del ciclo di vita mobile [ID app](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.application.sessionLength` | La metrica del ciclo di vita mobile [Durata sessione precedente](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.commerce.checkouts.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Casse](../../components/metrics/checkouts.md). |
| `xdm.commerce.checkouts.value` | Incrementa la metrica [Casse](../../components/metrics/checkouts.md) della quantità desiderata. |
| `xdm.commerce.order.currencyCode` | Imposta variabile di configurazione [currencyCode](../vars/config-vars/currencycode.md). |
| `xdm.commerce.order.purchaseID` | Imposta la variabile di pagina [purchaseID](../vars/page-vars/purchaseid.md). |
| `xdm.commerce.order.payments[0].transactionID` | Imposta la variabile di pagina [transactionID](../vars/page-vars/transactionid.md). |
| `xdm.commerce.productListAdds.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Aggiunte al carrello](../../components/metrics/cart-additions.md). |
| `xdm.commerce.productListAdds.value` | Incrementa la metrica [Aggiunte al carrello](../../components/metrics/cart-additions.md). |
| `xdm.commerce.productListOpens.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Carrelli](../../components/metrics/carts.md). |
| `xdm.commerce.productListOpens.value` | Incrementa la metrica [Carrelli](../../components/metrics/carts.md). |
| `xdm.commerce.productListRemovals.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Rimozioni dal carrello](../../components/metrics/cart-removals.md). |
| `xdm.commerce.productListRemovals.value` | Incrementa la metrica [Rimozioni dal carrello](../../components/metrics/cart-removals.md). |
| `xdm.commerce.productListViews.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Visualizzazioni carrello](../../components/metrics/cart-views.md). |
| `xdm.commerce.productListViews.value` | Incrementa la metrica [Visualizzazioni carrello](../../components/metrics/cart-views.md). |
| `xdm.commerce.productViews.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Visualizzazioni prodotto](../../components/metrics/product-views.md). |
| `xdm.commerce.productViews.value` | Incrementa la metrica [Visualizzazioni prodotto](../../components/metrics/product-views.md). |
| `xdm.commerce.purchases.value` | Incrementa la metrica [Ordini](../../components/metrics/orders.md). |
| `xdm.device.model` | La dimensione del ciclo di vita mobile [Nome dispositivo](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.device.colorDepth` | Aiuta a impostare la dimensione [Profondità colore](../../components/dimensions/color-depth.md). |
| `xdm.device.screenHeight` | Aiuta a impostare la dimensione [Risoluzione monitor.](../../components/dimensions/monitor-resolution.md) |
| `xdm.device.screenWidth` | Aiuta a impostare la dimensione [Risoluzione monitor](../../components/dimensions/monitor-resolution.md). |
| `xdm.device.type` | Il tipo di dispositivo mobile. |
| `xdm.environment.browserDetails.acceptLanguage` | Aiuta a impostare la dimensione [Lingua](../../components/dimensions/language.md). |
| `xdm.environment.browserDetails.cookiesEnabled` | Imposta la dimensione [Supporto per cookie](../../components/dimensions/cookie-support.md). I valori validi includono `Y` (il browser accetta i cookie) e `N` (il browser rifiuta i cookie). |
| `xdm.environment.browserDetails.javaEnabled` | Imposta la dimensione [Java abilitato](../../components/dimensions/java-enabled.md). I valori validi includono `Y` (Java è abilitato) e `N` (Java è disabilitato). |
| `xdm.environment.browserDetails.userAgent` | Utilizzato come metodo di identificazione di riserva per[ visitatore univoco](../../components/metrics/unique-visitors.md). Generalmente popolato utilizzando `User-Agent` Intestazione della richiesta HTTP. Puoi mappare questo campo su un eVar se desideri utilizzarlo nei rapporti. |
| `xdm.environment.browserDetails.viewportHeight` | Imposta la dimensione [Altezza browser](../../components/dimensions/browser-height.md). |
| `xdm.environment.browserDetails.viewportWidth` | Imposta la dimensione [Larghezza browser](../../components/dimensions/browser-width.md). |
| `xdm.environment.carrier` | La dimensione del ciclo di vita mobile [Nome gestore](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.environment.connectionType` | Aiuta a impostare la dimensione [Tipo di connessione](../../components/dimensions/connection-type.md). |
| `xdm.environment.ipV4` | Utilizzato come metodo di identificazione di riserva per [visitatore univoco](../../components/metrics/unique-visitors.md). Generalmente popolato utilizzando `X-Forwarded-For` Intestazione HTTP. |
| `xdm.environment.language` | La dimensione mobile Locale. |
| `xdm.environment.operatingSystem` | La dimensione del ciclo di vita mobile [Sistema operativo](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm.environment.operatingSystemVersion` | Aiuta a impostare la dimensione del ciclo di vita mobile [Versione sistema operativo](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/). |
| `xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Imposta la dimensione delle rispettive [eVar](../../components/dimensions/evar.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`hierarchies.hier1`<br/>`[...]`<br/>`xdm._experience.analytics.customDImensions.`<br/>`hierarchies.hier5` | Imposta la rispettiva dimensione [Gerarchia](/help/components/dimensions/hierarchy.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | Sovrascrittura delimitatore Prop elenco. L’utilizzo di questo campo non è consigliato, in quanto il delimitatore viene recuperato automaticamente dall’[Amministratore variabile di traffico](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti. L’utilizzo di questo campo può creare una mancata corrispondenza tra il delimitatore utilizzato e quello previsto da Analytics. |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.values`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | Matrice di stringhe contenente i rispettivi valori [Prop elenco](../vars/page-vars/prop.md#list-props). |
| `xdm._experience.analytics.customDimensions.`<br/>`lists.list1.list[].value`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatena tutte le stringhe `value` in ciascuna matrice `list[]` alla rispettiva [variabile elenco](../vars/page-vars/list.md). Il delimitatore viene scelto automaticamente in base al valore impostato in [Impostazioni delle suite di rapporti](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`props.prop1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`props.prop75` | Imposta la rispettiva dimensione [Prop](../../components/dimensions/prop.md). |
| `xdm._experience.analytics.event1to100.`<br/>`event1.id`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.id` | Applicabile [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) al rispettivo [Eventi personalizzati](../../components/metrics/custom-events.md) metrica. Ogni ID evento risiede nel relativo elemento padre di 100 gruppi. Ad esempio, per applicare la serializzazione a `event678`, utilizza `xdm._experience.analytics.event601to700.event678.id`. |
| `xdm._experience.analytics.event1to100.`<br/>`event1.value`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.value` | Incrementa il rispettivo [Eventi personalizzati](../../components/metrics/custom-events.md) metrica per la quantità desiderata. Ogni evento risiede nel relativo elemento padre di 100 gruppi. Ad esempio, il campo per `event567` è `xdm._experience.analytics.event501to600.event567.value`. |
| `xdm.identityMap.ECID[0].id` | L’[ID del servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). |
| `xdm.marketing.trackingCode` | Imposta la dimensione [Codice di tracciamento](../../components/dimensions/tracking-code.md). |
| `xdm.media.mediaTimed.completes.value` | La metrica di Media Analytics [Contenuto completato](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-complete). |
| `xdm.media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `xdm.media.mediaTimed.federated.value` | La metrica di Media Analytics [Dati federati](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#federated-data). |
| `xdm.media.mediaTimed.firstQuartiles.value` | La metrica di Media Analytics [Marcatore progresso 25 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#twenty-five-progress-marker). |
| `xdm.media.mediaTimed.mediaSegmentView.value` | La metrica di Media Analytics [Visualizzazioni dei segmenti di contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-segment-views). |
| `xdm.media.mediaTimed.midpoints.value` | La metrica di Media Analytics [Marcatore progresso 50 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#fifty-progress-marker). |
| `xdm.media.mediaTimed.pauseTime.value` | La metrica di Media Analytics [Durata totale pausa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#total-pause-duration). |
| `xdm.media.mediaTimed.pauses.value` | La metrica di Media Analytics [Pausa eventi](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#pause-events). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`@id` | La dimensione di Media Analytics [ID risorsa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#asset-id). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | La dimensione di Media Analytics [Nome video](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#video-name). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | La dimensione di Media Analytics [Originatore](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#originator). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | La dimensione di Media Analytics [Episodio](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#episode). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | La dimensione di Media Analytics [Genere](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#genre). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | La dimensione di Media Analytics [Valutazione dei contenuti](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-rating). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | La dimensione di Media Analytics [Stagione](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#season). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | La dimensione di Media Analytics [ID contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-id). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | La dimensione di Media Analytics [Mostra](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#show). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`showType` | La dimensione di Media Analytics [Mostra tipo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#show-type). |
| `xdm.media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | La dimensione di Media Analytics [Lunghezza video](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#video-length). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | La dimensione di Media Analytics [ID sessione multimediale](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#media-session-id). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | La dimensione di Media Analytics [Canale del contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-channel). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | La dimensione di Media Analytics [Tipo di contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-type). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | La dimensione di Media Analytics [Rete](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#network). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | La dimensione di Media Analytics [Segmento di contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-segment). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | La dimensione di Media Analytics [Nome del lettore di contenuti](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-player-name). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | La dimensione di Media Analytics [Versione SDK](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#sdk-version). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | La dimensione di Media Analytics [Tipo di feed multimediale](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#media-feed-type). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | La dimensione di Media Analytics [Formato flusso](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#stream-format). |
| `xdm.media.mediaTimed.progress10.value` | La metrica di Media Analytics [Marcatore progresso 10 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#ten-progress-marker). |
| `xdm.media.mediaTimed.progress95.value` | La metrica di Media Analytics [Marcatore progresso 95 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#ninety-five-progress-marker). |
| `xdm.media.mediaTimed.resumes.value` | La metrica di Media Analytics [Riprende il contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-resumes). |
| `xdm.media.mediaTimed.starts.value` | La metrica di Media Analytics [Media Starts](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#media-starts). |
| `xdm.media.mediaTimed.thirdQuartiles.value` | La metrica di Media Analytics [Marcatore progresso 75 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#seventy-five-progress-marker). |
| `xdm.media.mediaTimed.timePlayed.value` | La metrica di Media Analytics [Tempo contenuto trascorso](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-time-spent). |
| `xdm.media.mediaTimed.totalTimePlayed.value` | La metrica di Media Analytics [Tempo trascorso per contenuti multimediali](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#media-time-spent). |
| `xdm.placeContext.geo._schema.latitude` | La posizione di latitudine del visitatore. Aiuta a impostare [Percorso del ciclo di vita mobile](/help/components/dimensions/lifecycle-dimensions.md) dimensioni. |
| `xdm.placeContext.geo._schema.longitude` | La posizione della longitudine del visitatore. Aiuta a impostare [Percorso del ciclo di vita mobile](/help/components/dimensions/lifecycle-dimensions.md) dimensioni. |
| `xdm.placeContext.geo.postalCode` | La dimensione [Codice postale](../../components/dimensions/zip-code.md). |
| `xdm.placeContext.geo.stateProvince` | La dimensione [Stati Uniti](../../components/dimensions/us-states.md). |
| `xdm.placeContext.localTime` | Viene visualizzato come `t_time_info` in [Feed dati](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Applica la [sintassi del prodotto](../vars/page-vars/products.md) merchandising alle eVar. |
| `xdm.productListItems[]._experience.analytics.`<br/>`event1to100.event1.value`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Applica la [sintassi del prodotto](../vars/page-vars/products.md) merchandising agli eventi. |
| `xdm.productListItems[].productCategories[].categoryID` | La dimensione [Categoria](../../components/dimensions/category.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). |
| `xdm.productListItems[].name` | La dimensione [Prodotto](../../components/dimensions/product.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). Se `xdm.productListItems[].SKU` e `xdm.productListItems[].name` contengono entrambi dati, il valore in `xdm.productListItems[].SKU` viene utilizzato. |
| `xdm.productListItems[].priceTotal` | Aiuta a determinare la metrica [Entrate](../../components/metrics/revenue.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). |
| `xdm.productListItems[].quantity` | Aiuta a determinare la metrica [Unità](../../components/metrics/units.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). |
| `xdm.productListItems[].SKU` | La dimensione [Prodotto](../../components/dimensions/product.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). Se `xdm.productListItems[].SKU` e `xdm.productListItems[].name` contengono entrambi dati, il valore in `xdm.productListItems[].SKU` viene utilizzato. |
| `xdm.web.webInteraction.URL` | La variabile di implementazione [linkURL](../vars/config-vars/linkurl.md). |
| `xdm.web.webInteraction.name` | La dimensione [Collegamento personalizzato](../../components/dimensions/custom-link.md), [Collegamento di download](../../components/dimensions/download-link.md) oppure [Collegamento di uscita](../../components/dimensions/exit-link.md) a seconda del valore in `xdm.web.webInteraction.type` |
| `xdm.web.webInteraction.type` | Determina il tipo di collegamento su cui è stato fatto clic. I valori validi includono `other` (Collegamenti personalizzati), `download` (Collegamenti di download) e `exit` (Collegamenti di uscita). |
| `xdm.web.webPageDetails.URL` | La dimensione [URL della pagina](../../components/dimensions/page-url.md). |
| `xdm.web.webPageDetails.isErrorPage` | Flag che consente di determinare la [dimensione](../../components/dimensions/pages-not-found.md) e [metrica](../../components/metrics/pages-not-found.md) “Pagine non trovate”. |
| `xdm.web.webPageDetails.name` | La dimensione [Pagina](../../components/dimensions/page.md). |
| `xdm.web.webPageDetails.server` | La dimensione [Server](../../components/dimensions/server.md). |
| `xdm.web.webPageDetails.siteSection` | La dimensione [Sezione del sito](../../components/dimensions/site-section.md). |
| `xdm.web.webReferrer.URL` | La dimensione [Referrer](../../components/dimensions/referrer.md). |

{style="table-layout:auto"}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mappatura di altri campi XDM su variabili Analytics

Se esistono dimensioni o metriche da aggiungere ad Adobe Analytics, puoi farlo tramite [Variabili di dati di contesto](../vars/page-vars/contextdata.md). Tutti gli elementi di campo XDM che non sono mappati automaticamente vengono inviati ad Adobe Analytics come dati contestuali con il prefisso a.x. Puoi quindi mappare questa variabile di dati di contesto alla variabile di Analytics desiderata utilizzando le [Regole di elaborazione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=it). Ad esempio, se invii il seguente evento:

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "search":{
                "term":"Example search term"
            }
        }
    }
})
```

L’SDK per web invia tali dati ad Adobe Analytics come variabile di dati di contesto `a.x._atag.search.term`. Puoi quindi utilizzare una regola di elaborazione per assegnare il valore della variabile di dati di contesto alla variabile di Analytics desiderata, ad esempio un eVar:

![Regola di elaborazione dei termini di ricerca](assets/examplerule.png)
