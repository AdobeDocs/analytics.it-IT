---
title: Mappatura del campo oggetto XDM su Adobe Analytics
description: Visualizza quali campi XDM mappati automaticamente da Edge alle variabili di Analytics.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
feature: Implementation Basics
role: Admin, Developer
source-git-commit: b3546e67cccc37cbdb89db2e80b3b34b2dbe417b
workflow-type: tm+mt
source-wordcount: '1462'
ht-degree: 48%

---

# Mappatura del campo oggetto XDM su Adobe Analytics

La tabella seguente mostra le variabili XDM mappate automaticamente da Adobe Experience Platform Edge Network in Adobe Analytics. Se utilizzi questi percorsi di campo XDM, non è necessaria alcuna configurazione aggiuntiva per inviare dati ad Adobe Analytics. Questi campi sono inclusi nel gruppo di campi **[!UICONTROL Adobe Analytics ExperienceEvent Template]**. L’utilizzo di questi campi è consigliato se intendi inviare dati sia ad Adobe Analytics che a Adobe Experience Platform.

Se la tua organizzazione prevede di passare a Customer Journey Analytics, Adobe consiglia invece di utilizzare l&#39;oggetto `data` per inviare dati direttamente ad Adobe Analytics senza essere conforme a uno schema. Questa strategia consente all&#39;organizzazione di utilizzare il proprio schema anziché [!UICONTROL Adobe Analytics ExperienceEvent Template] (meno applicabile a Customer Journey Analytics). Per una tabella di mapping simile, vedere [Mappatura variabile oggetto dati su Adobe Analytics](data-var-mapping.md).

## Priorità di valore

La maggior parte dei campi oggetto XDM in questa tabella corrisponde a un [campo oggetto dati mappato](data-var-mapping.md). Durante l’acquisizione di Adobe Analytics, i valori vengono prima mappati da XDM alle variabili Analytics. I campi degli oggetti dati riconosciuti vengono quindi mappati e sovrascrivono eventuali valori impostati in precedenza quando vengono mappati sulla stessa variabile di Analytics. Ad esempio, se `data.__adobe.analytics.events` è presente, sostituisce l&#39;intero set di eventi che sarebbero altrimenti derivati da XDM; gli eventi non vengono combinati tra le due origini.

## Mappatura campo oggetto XDM

Gli aggiornamenti precedenti a questa tabella si trovano nella [cronologia dei commit su GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/implement/aep-edge/xdm-var-mapping.md) di questa pagina.

| Percorso campo XDM | Variabile e descrizione di Analytics |
| --- | --- |
| `xdm.application.isClose` | Consente di definire la metrica del ciclo di vita mobile [Arresti anomali](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isInstall` | Consente di determinare quando aumentare la metrica del ciclo di vita mobile [Primi avvii](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.closeType` | Determina se un evento di chiusura è un arresto anomalo o meno. I valori validi includono `close` (una sessione del ciclo di vita termina ed è stato ricevuto un evento di pausa per la sessione precedente) e `unknown` (una sessione del ciclo di vita termina senza un evento di pausa). Consente di impostare la metrica del ciclo di vita mobile [Arresti anomali](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isInstall` | La metrica del ciclo di vita mobile [Installazioni](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isLaunch` | La metrica del ciclo di vita mobile [Avvii](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.name` | Aiuta a impostare la dimensione del ciclo di vita mobile [ID app](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.isUpgrade` | La metrica del ciclo di vita mobile [Aggiornamenti](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.version` | Aiuta a impostare la dimensione del ciclo di vita mobile [ID app](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.application.sessionLength` | La metrica del ciclo di vita mobile [Lunghezza della sessione precedente](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.commerce.checkouts.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Pagamenti](/help/components/metrics/checkouts.md). |
| `xdm.commerce.checkouts.value` | Incrementa la metrica [Pagamenti](/help/components/metrics/checkouts.md) della quantità desiderata. |
| `xdm.commerce.order.currencyCode` | Imposta variabile di configurazione [currencyCode](../vars/config-vars/currencycode.md). |
| `xdm.commerce.order.purchaseID` | Imposta la variabile di pagina [purchaseID](../vars/page-vars/purchaseid.md). |
| `xdm.commerce.order.payments[0].transactionID` | Imposta la variabile di pagina [transactionID](../vars/page-vars/transactionid.md). |
| `xdm.commerce.productListAdds.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Aggiunte al carrello](/help/components/metrics/cart-additions.md). |
| `xdm.commerce.productListAdds.value` | Incrementa la metrica [Aggiunte al carrello](/help/components/metrics/cart-additions.md). |
| `xdm.commerce.productListOpens.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Carrelli](/help/components/metrics/carts.md). |
| `xdm.commerce.productListOpens.value` | Incrementa la metrica [Carrelli](/help/components/metrics/carts.md). |
| `xdm.commerce.productListRemovals.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Rimozioni dal carrello](/help/components/metrics/cart-removals.md). |
| `xdm.commerce.productListRemovals.value` | Incrementa la metrica [Rimozioni dal carrello](/help/components/metrics/cart-removals.md). |
| `xdm.commerce.productListViews.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Visualizzazioni carrello](/help/components/metrics/cart-views.md). |
| `xdm.commerce.productListViews.value` | Incrementa la metrica [Visualizzazioni carrello](/help/components/metrics/cart-views.md). |
| `xdm.commerce.productViews.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Visualizzazioni prodotto](/help/components/metrics/product-views.md). |
| `xdm.commerce.productViews.value` | Incrementa la metrica [Visualizzazioni prodotto](/help/components/metrics/product-views.md). |
| `xdm.commerce.purchases.value` | Incrementa la metrica [Ordini](/help/components/metrics/orders.md). |
| `xdm.device.model` | La dimensione del ciclo di vita mobile [Nome del dispositivo](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.device.colorDepth` | Aiuta a impostare la dimensione [Profondità colore](/help/components/dimensions/color-depth.md). |
| `xdm.device.screenHeight` | Aiuta a impostare la dimensione [Risoluzione monitor.](/help/components/dimensions/monitor-resolution.md) |
| `xdm.device.screenWidth` | Aiuta a impostare la dimensione [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md). |
| `xdm.device.type` | Il tipo di dispositivo mobile. |
| `xdm.environment.browserDetails.acceptLanguage` | Aiuta a impostare la dimensione [Lingua](/help/components/dimensions/language.md). |
| `xdm.environment.browserDetails.cookiesEnabled` | Imposta la dimensione [Supporto per cookie](/help/components/dimensions/cookie-support.md). I valori validi includono `Y` (il browser accetta i cookie) e `N` (il browser rifiuta i cookie). |
| `xdm.environment.browserDetails.javaEnabled` | Imposta la dimensione [Java abilitato](/help/components/dimensions/java-enabled.md). I valori validi includono `Y` (Java è abilitato) e `N` (Java è disabilitato). |
| `xdm.environment.browserDetails.userAgent` | Utilizzato come metodo di identificazione di riserva per[&#x200B; visitatore univoco](/help/components/metrics/unique-visitors.md). Generalmente popolato utilizzando `User-Agent` Intestazione della richiesta HTTP. Puoi mappare questo campo su un eVar se desideri utilizzarlo nei rapporti. |
| `xdm.environment.browserDetails.viewportHeight` | Imposta la dimensione [Altezza browser](/help/components/dimensions/browser-height.md). |
| `xdm.environment.browserDetails.viewportWidth` | Imposta la dimensione [Larghezza browser](/help/components/dimensions/browser-width.md). |
| `xdm.environment.carrier` | La dimensione del ciclo di vita mobile [Nome del gestore](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.environment.connectionType` | Aiuta a impostare la dimensione [Tipo di connessione](/help/components/dimensions/connection-type.md). |
| `xdm.environment._dc.language` | Imposta la variabile di dati di contesto `a.locale`. Utilizzato solo se `xdm.environment.language` non è impostato. Adobe consiglia di utilizzare questo campo oltre `xdm.environment.language`. |
| `xdm.environment.ipV4` | Utilizzato come metodo di identificazione di riserva per [visitatore univoco](/help/components/metrics/unique-visitors.md). Generalmente popolato utilizzando `X-Forwarded-For` Intestazione HTTP. |
| `xdm.environment.language` | Imposta la variabile di dati di contesto `a.locale`. Adobe consiglia di utilizzare `xdm.environment._dc.language`. |
| `xdm.environment.operatingSystem` | La dimensione del ciclo di vita mobile [Sistema operativo](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm.environment.operatingSystemVersion` | Aiuta a impostare la dimensione del ciclo di vita mobile [Versione sistema operativo](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/metrics/). |
| `xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Imposta la dimensione delle rispettive [eVar](/help/components/dimensions/evar.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`hierarchies.hier1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`hierarchies.hier5` | Imposta la rispettiva dimensione [Gerarchia](/help/components/dimensions/hierarchy.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | Sovrascrittura delimitatore Prop elenco. L’utilizzo di questo campo non è consigliato, in quanto il delimitatore viene recuperato automaticamente dall’[Amministratore variabile di traffico](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti. L’utilizzo di questo campo può creare una mancata corrispondenza tra il delimitatore utilizzato e quello previsto da Analytics. |
| `xdm._experience.analytics.customDimensions.`<br/>`listProps.prop1.values`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | Array di stringhe contenente i rispettivi valori [Prop elenco](../vars/page-vars/prop.md#list-props). |
| `xdm._experience.analytics.customDimensions.`<br/>`lists.list1.list[].value`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatena tutte le stringhe `value` in ciascun array `list[]` alla rispettiva [variabile elenco](../vars/page-vars/list.md). Il delimitatore viene scelto automaticamente in base al valore impostato in [Impostazioni suite di rapporti](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md). |
| `xdm._experience.analytics.customDimensions.`<br/>`props.prop1`<br/>`[...]`<br/>`xdm._experience.analytics.customDimensions.`<br/>`props.prop75` | Imposta la rispettiva dimensione [Prop](/help/components/dimensions/prop.md). |
| `xdm._experience.analytics.event1to100.`<br/>`event1.id`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla rispettiva metrica [Eventi personalizzati](/help/components/metrics/custom-events.md). Ogni ID evento risiede nel relativo elemento principale di 100 gruppi. Ad esempio, per applicare la serializzazione a `event678`, utilizza `xdm._experience.analytics.event601to700.event678.id`. |
| `xdm._experience.analytics.event1to100.`<br/>`event1.value`<br/>`[...]`<br/>`xdm._experience.analytics.event901to1000.`<br/>`event1000.value` | Incrementa la rispettiva metrica [Eventi personalizzati](/help/components/metrics/custom-events.md) della quantità desiderata. Ogni evento risiede nel relativo elemento principale di 100 gruppi. Ad esempio, il campo per `event567` è `xdm._experience.analytics.event501to600.event567.value`. |
| `xdm.identityMap.ECID[0].id` | L’[ID del servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/en/docs/id-service/using/home). |
| `xdm.marketing.trackingCode` | Imposta la dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md). |
| `xdm.media.mediaTimed.completes.value` | La metrica dei servizi multimediali in streaming [Contenuto completato](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-complete). |
| `xdm.media.mediaTimed.dropBeforeStart.value` | `a.media.view`, `a.media.timePlayed`, `a.media.play` |
| `xdm.media.mediaTimed.federated.value` | La metrica dei servizi multimediali in streaming [Dati federati](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#federated-data). |
| `xdm.media.mediaTimed.firstQuartiles.value` | La metrica di Streaming Media Services [Marcatore avanzamento 25 %](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#twenty-five--progress-marker). |
| `xdm.media.mediaTimed.mediaSegmentView.value` | La metrica dei servizi multimediali in streaming [Visualizzazioni dei segmenti di contenuto](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-segment-views). |
| `xdm.media.mediaTimed.midpoints.value` | La metrica di Streaming Media Services [Marcatore avanzamento 50 %](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#progress-marker). |
| `xdm.media.mediaTimed.pauseTime.value` | La metrica dei servizi multimediali in streaming [Durata totale pausa](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#total-pause-duration). |
| `xdm.media.mediaTimed.pauses.value` | La metrica dei servizi multimediali in streaming [Pausa eventi](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#pause-events). |
| `xdm.mediaCollection.sessionDetails.assetID` | La dimensione dei servizi multimediali in streaming [ID risorsa](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#asset-id). |
| `xdm.mediaCollection.sessionDetails.friendlyName` | La dimensione dei servizi multimediali di streaming [Nome video](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#video-name). |
| `xdm.mediaCollection.sessionDetails.originator` | La dimensione dei servizi multimediali in streaming [Iniziatore](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#originator). |
| `xdm.mediaCollection.sessionDetails.episode` | La dimensione dei servizi multimediali in streaming [Episodio](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#episode). |
| `xdm.mediaCollection.sessionDetails.genre` | La dimensione dei servizi multimediali in streaming [Genere](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#genre). |
| `xdm.mediaCollection.sessionDetails.rating` | La dimensione dei servizi multimediali in streaming [Valutazione contenuto](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-rating). |
| `xdm.mediaCollection.sessionDetails.season` | La dimensione dei servizi multimediali in streaming [Stagione](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#season). |
| `xdm.mediaCollection.sessionDetails.name` | La dimensione dei servizi multimediali in streaming [ID contenuto](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-id). |
| `xdm.mediaCollection.sessionDetails.show` | La dimensione dei servizi multimediali in streaming [Mostra](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#show). |
| `xdm.mediaCollection.sessionDetails.showType` | La dimensione dei servizi multimediali in streaming [Tipo di spettacolo](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#show-type). |
| `xdm.mediaCollection.sessionDetails.length` | La dimensione dei servizi multimediali di streaming [Lunghezza video](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#video-length). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.@id` | La dimensione dei servizi multimediali in streaming [ID sessione multimediale](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-session-id). |
| `xdm.mediaCollection.sessionDetails.channel` | La dimensione dei servizi multimediali in streaming [Canale contenuto](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-channel). |
| `xdm.mediaCollection.sessionDetails.contentType` | La dimensione dei servizi multimediali in streaming [Tipo di contenuto](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-type). |
| `xdm.mediaCollection.sessionDetails.network` | La dimensione dei servizi multimediali in streaming [Rete](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#network). |
| `xdm.media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | La dimensione dei servizi multimediali in streaming [Segmento di contenuto](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-segment). |
| `xdm.mediaCollection.sessionDetails.playerName` | La dimensione dei servizi multimediali in streaming [Nome del lettore di contenuti](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-player-name). |
| `xdm.mediaCollection.sessionDetails.appVersion` | La dimensione dei servizi multimediali in streaming [SDK versione](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#sdk-version). |
| `xdm.mediaCollection.sessionDetails.feed` | La dimensione dei servizi multimediali in streaming [Tipo di feed multimediale](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-feed-type). |
| `xdm.mediaCollection.sessionDetails.streamFormat` | La dimensione dei servizi multimediali in streaming [Formato flusso](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#stream-format). |
| `xdm.media.mediaTimed.progress10.value` | La metrica di Streaming Media Services [Marcatore avanzamento 10%](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#ten--progress-marker). |
| `xdm.media.mediaTimed.progress95.value` | La metrica di Streaming Media Services [Marcatore avanzamento 95 %](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#ninety-five--progress-marker). |
| `xdm.mediaCollection.sessionDetails.hasResume` | La metrica dei servizi multimediali in streaming [Il contenuto riprende](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-resumes). |
| `xdm.media.mediaTimed.starts.value` | La metrica dei servizi multimediali in streaming [Avvio file multimediale](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-starts). |
| `xdm.media.mediaTimed.thirdQuartiles.value` | La metrica di Streaming Media Services [Marcatore avanzamento 75 %](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#seventy-five--progress-marker). |
| `xdm.media.mediaTimed.timePlayed.value` | La metrica dei servizi multimediali in streaming [Tempo contenuto trascorso](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#content-time-spent). |
| `xdm.media.mediaTimed.totalTimePlayed.value` | La metrica dei servizi multimediali in streaming [Tempo trascorso file multimediale](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/variables/audio-video-parameters#media-time-spent). |
| `xdm.placeContext.geo._schema.latitude` | La posizione di latitudine del visitatore. Consente di impostare le dimensioni [Percorso del ciclo di vita mobile](/help/components/dimensions/lifecycle-dimensions.md). |
| `xdm.placeContext.geo._schema.longitude` | La posizione della longitudine del visitatore. Consente di impostare le dimensioni [Percorso del ciclo di vita mobile](/help/components/dimensions/lifecycle-dimensions.md). |
| `xdm.placeContext.geo.postalCode` | La dimensione [Codice postale](/help/components/dimensions/zip-code.md). |
| `xdm.placeContext.geo.stateProvince` | La dimensione [Stati Uniti](/help/components/dimensions/us-states.md). |
| `xdm.placeContext.localTime` | Viene visualizzato come `t_time_info` in [Feed dati](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Applica la [sintassi del prodotto](../vars/page-vars/products.md) merchandising alle eVar. |
| `xdm.productListItems[]._experience.analytics.`<br/>`event1to100.event1.value`<br/>`[...]`<br/>`xdm.productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Applica la [sintassi del prodotto](../vars/page-vars/products.md) merchandising agli eventi. |
| `xdm.productListItems[].productCategories[].categoryID` | La dimensione [Categoria](/help/components/dimensions/category.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). |
| `xdm.productListItems[].name` | La dimensione [Prodotto](/help/components/dimensions/product.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). Se `xdm.productListItems[].SKU` e `xdm.productListItems[].name` contengono entrambi dati, il valore in `xdm.productListItems[].SKU` viene utilizzato. |
| `xdm.productListItems[].priceTotal` | Aiuta a determinare la metrica [Entrate](/help/components/metrics/revenue.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). |
| `xdm.productListItems[].quantity` | Aiuta a determinare la metrica [Unità](/help/components/metrics/units.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). |
| `xdm.productListItems[].SKU` | La dimensione [Prodotto](/help/components/dimensions/product.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). Se `xdm.productListItems[].SKU` e `xdm.productListItems[].name` contengono entrambi dati, il valore in `xdm.productListItems[].SKU` viene utilizzato. |
| `xdm.web.webInteraction.URL` | La variabile di implementazione [linkURL](../vars/config-vars/linkurl.md). |
| `xdm.web.webInteraction.name` | La dimensione [Collegamento personalizzato](/help/components/dimensions/custom-link.md), [Collegamento di download](/help/components/dimensions/download-link.md) oppure [Collegamento di uscita](/help/components/dimensions/exit-link.md) a seconda del valore in `xdm.web.webInteraction.type` |
| `xdm.web.webInteraction.type` | Determina il tipo di collegamento su cui è stato fatto clic. I valori validi includono `other` (Collegamenti personalizzati), `download` (Collegamenti di download) e `exit` (Collegamenti di uscita). |
| `xdm.web.webPageDetails.URL` | La dimensione [URL della pagina](/help/components/dimensions/page-url.md). |
| `xdm.web.webPageDetails.isErrorPage` | Flag che consente di determinare la [dimensione](/help/components/dimensions/pages-not-found.md) e [metrica](/help/components/metrics/pages-not-found.md) “Pagine non trovate”. |
| `xdm.web.webPageDetails.name` | La dimensione [Pagina](/help/components/dimensions/page.md). |
| `xdm.web.webPageDetails.server` | La dimensione [Server](/help/components/dimensions/server.md). |
| `xdm.web.webPageDetails.siteSection` | La dimensione [Sezione del sito](/help/components/dimensions/site-section.md). |
| `xdm.web.webReferrer.URL` | La dimensione [Referrer](/help/components/dimensions/referrer.md). |

{style="table-layout:auto"}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mappatura di altri campi XDM su variabili Analytics

Se esistono dimensioni o metriche da aggiungere ad Adobe Analytics, puoi farlo tramite [Variabili di dati di contesto](../vars/page-vars/contextdata.md).

### Mappatura implicita

Tutti gli elementi di campo XDM che non sono mappati automaticamente vengono inviati ad Adobe Analytics come dati contestuali con il prefisso `a.x.`. Puoi quindi mappare questa variabile di dati di contesto alla variabile di Analytics desiderata utilizzando [regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md). Ad esempio, se invii il seguente evento:

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

L’SDK per web invia tali dati ad Adobe Analytics come variabile di dati di contesto `a.x._atag.search.term`. È quindi possibile utilizzare una regola di elaborazione per assegnare il valore della variabile di dati di contesto alla variabile di Analytics desiderata, ad esempio `eVar`:

![Regola di elaborazione dei termini di ricerca](assets/examplerule.png)

## Mappatura esplicita

Puoi anche mappare esplicitamente gli elementi del campo XDM come dati contestuali. Qualsiasi elemento campo XDM mappato in modo esplicito, utilizzando l&#39;elemento `contextData`, viene inviato ad Adobe Analytics come dati contestuali senza prefisso. Puoi quindi mappare questa variabile di dati di contesto alla variabile di Analytics desiderata utilizzando [regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md). Ad esempio, se invii il seguente evento:

```js
alloy("event",{
    "xdm":{
        "_atag":{
            "analytics": {
                "contextData" : {
                    "someValue" : "1"
                }
            }
        }
    }
})
```

Il Web SDK invia tali dati ad Adobe Analytics come variabile di dati di contesto `somevalue` con valore `1`.  È quindi possibile utilizzare una regola di elaborazione per assegnare il valore della variabile di dati di contesto alla variabile di Analytics desiderata, ad esempio `eVar`:

![Regola di elaborazione dei termini di ricerca](assets/examplerule-explicit.png)
