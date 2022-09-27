---
title: Mappatura delle variabili di Analytics in Adobe Experience Edge
description: Visualizza quali campi XDM mappati automaticamente da Edge alle variabili di Analytics.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
source-git-commit: 47a5f891f2769a97936a3809c3615374b0045bd4
workflow-type: tm+mt
source-wordcount: '1441'
ht-degree: 100%

---

# Mappatura delle variabili di Analytics in Adobe Experience Edge

La tabella seguente mostra le variabili mappate automaticamente da Adobe Experience Platform Edge Network in Adobe Analytics. Se utilizzi questi percorsi dei campi XDM, non è necessaria alcuna configurazione aggiuntiva per inviare dati ad Adobe Analytics.

| Percorso campo XDM | Dimensione e descrizione di Analytics |
| --- | --- |
| `application.isClose` | Consente di definire la metrica mobile [Arresti anomali](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=it#metrics). |
| `application.isInstall` | Consente di determinare quando aumentare la metrica mobile [Primi avvii](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | Consente di determinare quando aumentare la metrica mobile [Primi avvii](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.closeType` | Determina se un evento di chiusura è un arresto anomalo o meno. I valori validi includono `close` (una sessione del ciclo di vita termina ed è stato ricevuto un evento di pausa per la sessione precedente) e `unknown` (una sessione del ciclo di vita termina senza un evento di pausa). Aiuta a impostare la metrica [Arresti anomali](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isInstall` | La metrica mobile [Installazioni](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | La metrica mobile [Avvii](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.name` | Consente di impostare la dimensione mobile [ID app](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=it#dimensions). |
| `application.isUpgrade` | La metrica mobile [Aggiornamenti](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.version` | Consente di impostare la dimensione mobile [ID app](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.sessionLength` | La metrica mobile [Lunghezza della sessione precedente](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `commerce.checkouts.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Casse](../../components/metrics/checkouts.md). |
| `commerce.checkouts.value` | Incrementa la metrica [Casse](../../components/metrics/checkouts.md) della quantità desiderata. |
| `commerce.order.currencyCode` | Imposta variabile di configurazione [currencyCode](../vars/config-vars/currencycode.md). |
| `commerce.order.purchaseID` | Imposta la variabile di pagina [purchaseID](../vars/page-vars/purchaseid.md). |
| `commerce.order.transactionID` | Imposta la variabile di pagina [transactionID](../vars/page-vars/transactionid.md). |
| `commerce.productListAdds.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Aggiunte al carrello](../../components/metrics/cart-additions.md). |
| `commerce.productListAdds.value` | Incrementa la metrica [Aggiunte al carrello](../../components/metrics/cart-additions.md). |
| `commerce.productListOpens.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Carrelli](../../components/metrics/carts.md). |
| `commerce.productListOpens.value` | Incrementa la metrica [Carrelli](../../components/metrics/carts.md). |
| `commerce.productListRemovals.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Rimozioni dal carrello](../../components/metrics/cart-removals.md). |
| `commerce.productListRemovals.value` | Incrementa la metrica [Rimozioni dal carrello](../../components/metrics/cart-removals.md). |
| `commerce.productListViews.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Visualizzazioni carrello](../../components/metrics/cart-views.md). |
| `commerce.productListViews.value` | Incrementa la metrica [Visualizzazioni carrello](../../components/metrics/cart-views.md). |
| `commerce.productViews.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla metrica [Visualizzazioni prodotto](../../components/metrics/product-views.md). |
| `commerce.productViews.value` | Incrementa la metrica [Visualizzazioni prodotto](../../components/metrics/product-views.md). |
| `commerce.purchases.value` | Incrementa la metrica [Ordini](../../components/metrics/orders.md). |
| `device.model` | La dimensione mobile [Nome del dispositivo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `device.colorDepth` | Aiuta a impostare la dimensione [Profondità colore](../../components/dimensions/color-depth.md). |
| `device.screenHeight` | Aiuta a impostare la dimensione [Risoluzione monitor.](../../components/dimensions/monitor-resolution.md) |
| `device.screenWidth` | Aiuta a impostare la dimensione [Risoluzione monitor](../../components/dimensions/monitor-resolution.md). |
| `device.type` | Il tipo di dispositivo mobile. |
| `environment.browserDetails.acceptLanguage` | Aiuta a impostare la dimensione [Lingua](../../components/dimensions/language.md). |
| `environment.browserDetails.cookiesEnabled` | Imposta la dimensione [Supporto per cookie](../../components/dimensions/cookie-support.md). I valori validi includono `Y` (il browser accetta i cookie) e `N` (il browser rifiuta i cookie). |
| `environment.browserDetails.javaEnabled` | Imposta la dimensione [Java abilitato](../../components/dimensions/java-enabled.md). I valori validi includono `Y` (Java è abilitato) e `N` (Java è disabilitato). |
| `environment.browserDetails.userAgent` | Utilizzato come metodo di identificazione di riserva per[ visitatore univoco](../../components/metrics/unique-visitors.md). Generalmente popolato utilizzando `User-Agent` Intestazione della richiesta HTTP. Puoi mappare questo campo su un eVar se desideri utilizzarlo nei rapporti. |
| `environment.browserDetails.viewportHeight` | Imposta la dimensione [Altezza browser](../../components/dimensions/browser-height.md). |
| `environment.browserDetails.viewportWidth` | Imposta la dimensione [Larghezza browser](../../components/dimensions/browser-width.md). |
| `environment.carrier` | La dimensione mobile [Nome gestore](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.connectionType` | Aiuta a impostare la dimensione [Tipo di connessione](../../components/dimensions/connection-type.md). |
| `environment.ipV4` | Utilizzato come metodo di identificazione di riserva per [visitatore univoco](../../components/metrics/unique-visitors.md). Generalmente popolato utilizzando `X-Forwarded-For` Intestazione HTTP. |
| `environment.language` | La dimensione mobile Locale. |
| `environment.operatingSystem` | La dimensione mobile [Sistema operativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.operatingSystemVersion` | Consente di impostare la dimensione [Versione sistema operativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `_experience.analytics.customDimensions.`<br/>`eVars.eVar1` -<br/>`_experience.analytics.customDimensions.`<br/>`eVars.eVar250` | Imposta la dimensione delle rispettive [eVar](../../components/dimensions/evar.md). |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.delimiter` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.delimiter` | Sovrascrittura delimitatore Prop elenco. L’utilizzo di questo campo non è consigliato, in quanto il delimitatore viene recuperato automaticamente dall’[Amministratore variabile di traffico](/help/admin/admin/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti. L’utilizzo di questo campo può creare una mancata corrispondenza tra il delimitatore utilizzato e quello previsto da Analytics. |
| `_experience.analytics.customDimensions.`<br/>`listProps.prop1.values` -<br/>`_experience.analytics.customDimensions.`<br/>`listProps.prop75.values` | Matrice di stringhe contenente i rispettivi valori [Prop elenco](../vars/page-vars/prop.md#list-props). |
| `_experience.analytics.customDimensions.`<br/>`lists.list1.list[].value` -<br/>`_experience.analytics.customDimensions.`<br/>`lists.list3.list[].value` | Concatena tutte le stringhe `value` in ciascuna matrice `list[]` alla rispettiva [variabile elenco](../vars/page-vars/list.md). Il delimitatore viene scelto automaticamente in base al valore impostato in [Impostazioni delle suite di rapporti](/help/admin/admin/conversion-var-admin/list-var-admin.md). |
| `_experience.analytics.customDimensions.`<br/>`props.prop1` -<br/>`_experience.analytics.customDimensions.`<br/>`props.prop75` | Imposta la rispettiva dimensione [Prop](../../components/dimensions/prop.md). |
| `_experience.analytics.event1to100.`<br/>`event1.id` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.id` | Applica la [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) alla rispettiva metrica [Eventi personalizzati](../../components/metrics/custom-events.md). |
| `_experience.analytics.event1to100.`<br/>`event1.value` -<br/>`_experience.analytics.event901to1000.`<br/>`event1000.value` | Incrementa la rispettiva metrica [Eventi personalizzati](../../components/metrics/custom-events.md) della quantità desiderata. |
| `identityMap.ECID[0].id` | L’[ID del servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). |
| `marketing.trackingCode` | Imposta la dimensione [Codice di tracciamento](../../components/dimensions/tracking-code.md). |
| `media.mediaTimed.completes.value` | La metrica di Media Analytics [Contenuto completato](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-complete). |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `media.mediaTimed.federated.value` | La metrica di Media Analytics [Dati federati](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#federated-data). |
| `media.mediaTimed.firstQuartiles.value` | La metrica di Media Analytics [Marcatore progresso 25 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#twenty-five-progress-marker). |
| `media.mediaTimed.mediaSegmentView.value` | La metrica di Media Analytics [Visualizzazioni dei segmenti di contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-segment-views). |
| `media.mediaTimed.midpoints.value` | La metrica di Media Analytics [Marcatore progresso 50 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#fifty-progress-marker). |
| `media.mediaTimed.pauseTime.value` | La metrica di Media Analytics [Durata totale pausa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#total-pause-duration). |
| `media.mediaTimed.pauses.value` | La metrica di Media Analytics [Pausa eventi](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#pause-events). |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | La dimensione di Media Analytics [ID risorsa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#asset-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | La dimensione di Media Analytics [Nome video](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#video-name). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | La dimensione di Media Analytics [Originatore](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#originator). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | La dimensione di Media Analytics [Episodio](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#episode). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | La dimensione di Media Analytics [Genere](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#genre). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | La dimensione di Media Analytics [Valutazione dei contenuti](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-rating). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | La dimensione di Media Analytics [Stagione](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#season). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | La dimensione di Media Analytics [ID contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | La dimensione di Media Analytics [Mostra](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#show). |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | La dimensione di Media Analytics [Mostra tipo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#show-type). |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | La dimensione di Media Analytics [Lunghezza video](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#video-length). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | La dimensione di Media Analytics [ID sessione multimediale](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#media-session-id). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | La dimensione di Media Analytics [Canale del contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-channel). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | La dimensione di Media Analytics [Tipo di contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | La dimensione di Media Analytics [Rete](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#network). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | La dimensione di Media Analytics [Segmento di contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-segment). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | La dimensione di Media Analytics [Nome del lettore di contenuti](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-player-name). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | La dimensione di Media Analytics [Versione SDK](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#sdk-version). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | La dimensione di Media Analytics [Tipo di feed multimediale](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#media-feed-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | La dimensione di Media Analytics [Formato flusso](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#stream-format). |
| `media.mediaTimed.progress10.value` | La metrica di Media Analytics [Marcatore progresso 10 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#ten-progress-marker). |
| `media.mediaTimed.progress95.value` | La metrica di Media Analytics [Marcatore progresso 95 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#ninety-five-progress-marker). |
| `media.mediaTimed.resumes.value` | La metrica di Media Analytics [Riprende il contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-resumes). |
| `media.mediaTimed.starts.value` | La metrica di Media Analytics [Media Starts](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#media-starts). |
| `media.mediaTimed.thirdQuartiles.value` | La metrica di Media Analytics [Marcatore progresso 75 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#seventy-five-progress-marker). |
| `media.mediaTimed.timePlayed.value` | La metrica di Media Analytics [Tempo contenuto trascorso](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#content-time-spent). |
| `media.mediaTimed.totalTimePlayed.value` | La metrica di Media Analytics [Tempo trascorso per contenuti multimediali](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html?lang=it#media-time-spent). |
| `placeContext.geo.latitude` | La dimensione Mobile Latitudine. |
| `placeContext.geo.longitude` | La dimensione Mobile Longitudine. |
| `placeContext.geo.postalCode` | La dimensione [Codice postale](../../components/dimensions/zip-code.md). |
| `placeContext.geo.stateProvince` | La dimensione [Stati Uniti](../../components/dimensions/us-states.md). |
| `placeContext.localTime` | Aiuta a popolare i [Fusi orari](/help/analyze/reports-analytics/reports.md) in Report and Analytics. Viene visualizzato come `t_time_info` in [Feed dati](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md). |
| `productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar1` -<br/>`productListItems[]._experience.analytics.`<br/>`customDimensions.eVars.eVar250` | Applica la [sintassi del prodotto](../vars/page-vars/products.md) merchandising alle eVar. |
| `productListItems[]._experience.analytics.`<br/>`event1to100.event1.value` -<br/>`productListItems[]._experience.analytics.`<br/>`event901-1000.event1000.value` | Applica la [sintassi del prodotto](../vars/page-vars/products.md) merchandising agli eventi. |
| `productListItems[].lineItemId` | La dimensione [Categoria](../../components/dimensions/category.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). |
| `productListItems[].name` | La dimensione [Prodotto](../../components/dimensions/product.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). Se `productListItems[].SKU` e `productListItems[].name` contengono entrambi dati, il valore in `productListItems[].SKU` viene utilizzato. |
| `productListItems[].priceTotal` | Aiuta a determinare la metrica [Entrate](../../components/metrics/revenue.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). |
| `productListItems[].quantity` | Aiuta a determinare la metrica [Unità](../../components/metrics/units.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). |
| `productListItems[].SKU` | La dimensione [Prodotto](../../components/dimensions/product.md). Vedi anche la variabile di pagina [prodotti](../vars/page-vars/products.md). Se `productListItems[].SKU` e `productListItems[].name` contengono entrambi dati, il valore in `productListItems[].SKU` viene utilizzato. |
| `web.webInteraction.URL` | La variabile di implementazione [linkURL](../vars/config-vars/linkurl.md). |
| `web.webInteraction.name` | La dimensione [Collegamento personalizzato](../../components/dimensions/custom-link.md), [Collegamento di download](../../components/dimensions/download-link.md) oppure [Collegamento di uscita](../../components/dimensions/exit-link.md) a seconda del valore in `web.webInteraction.type` |
| `web.webInteraction.type` | Determina il tipo di collegamento su cui è stato fatto clic. I valori validi includono `other` (Collegamenti personalizzati), `download` (Collegamenti di download) e `exit` (Collegamenti di uscita). |
| `web.webPageDetails.URL` | La dimensione [URL della pagina](../../components/dimensions/page-url.md). |
| `web.webPageDetails.errorPage` | Flag che consente di determinare la [dimensione](../../components/dimensions/pages-not-found.md) e [metrica](../../components/metrics/pages-not-found.md) “Pagine non trovate”. |
| `web.webPageDetails.name` | La dimensione [Pagina](../../components/dimensions/page.md). |
| `web.webPageDetails.server` | La dimensione [Server](../../components/dimensions/server.md). |
| `web.webPageDetails.siteSection` | La dimensione [Sezione del sito](../../components/dimensions/site-section.md). |
| `web.webReferrer.URL` | La dimensione [Referrer](../../components/dimensions/referrer.md). |

{style=&quot;table-layout:auto&quot;}

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
