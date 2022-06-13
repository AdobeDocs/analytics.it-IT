---
title: Mappatura delle variabili di Analytics in Adobe Experience Edge
description: Visualizza quali campi XDM mappati automaticamente da Edge alle variabili di Analytics.
exl-id: fbff5c38-0f04-4780-b976-023e207023c6
source-git-commit: 8ff414efff302adfee42f192e781a8dec5c42902
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 0%

---

# Mappatura delle variabili di Analytics in Adobe Experience Edge

La tabella seguente mostra le variabili mappate automaticamente da Adobe Experience Platform Edge Network in Adobe Analytics. Se utilizzi questi percorsi dei campi XDM, non è necessaria alcuna configurazione aggiuntiva per inviare dati ad Adobe Analytics.

| Percorso campo XDM | Dimensione e descrizione di Analytics |
| --- | --- |
| `application.id` | La dimensione mobile [ID app](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.isClose` | Consente di definire la metrica mobile [Arresti anomali](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.closeType` | Determina se un evento di chiusura è un arresto anomalo o meno. I valori validi includono `close` (termina una sessione del ciclo di vita e viene ricevuto un evento di pausa per la sessione precedente) e `unknown` (Una sessione del ciclo di vita termina senza un evento di pausa). |
| `application.isInstall` | La metrica mobile [Installazioni](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isLaunch` | La metrica mobile [Lanci](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.name` | Consente di impostare la dimensione mobile [ID app](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.launches.value` | La metrica mobile [Lanci](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.isUpgrade` | La metrica mobile [Aggiornamenti](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `application.version` | Consente di impostare la dimensione mobile [ID app](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `application.sessionLength` | La metrica mobile [Lunghezza totale della sessione](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#metrics). |
| `commerce.checkouts.id` | Si applica [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) al [Pagamenti](../../components/metrics/checkouts.md) metrica. |
| `commerce.checkouts.value` | Incrementa la [Pagamenti](../../components/metrics/checkouts.md) metrica per la quantità desiderata. |
| `commerce.order.currencyCode` | Imposta la [currencyCode](../vars/config-vars/currencycode.md) variabile di configurazione. |
| `commerce.order.purchaseID` | Imposta la [purchaseID](../vars/page-vars/purchaseid.md) variabile di pagina. |
| `commerce.productListAdds.id` | Si applica [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) al [Aggiunte carrello](../../components/metrics/cart-additions.md) metrica. |
| `commerce.productListAdds.value` | Incrementa la [Aggiunte carrello](../../components/metrics/cart-additions.md) metrica per la quantità desiderata. |
| `commerce.productListOpens.id` | Si applica [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) al [Carrelli](../../components/metrics/carts.md) metrica. |
| `commerce.productListOpens.value` | Incrementa la [Carrelli](../../components/metrics/carts.md) metrica per la quantità desiderata. |
| `commerce.productListRemovals.id` | Si applica [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) al [Rimozioni carrello](../../components/metrics/cart-removals.md) metrica. |
| `commerce.productListRemovals.value` | Incrementa la [Rimozioni carrello](../../components/metrics/cart-removals.md) metrica per la quantità desiderata. |
| `commerce.productListViews.id` | Si applica [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) al [Visualizzazioni carrello](../../components/metrics/cart-views.md) metrica. |
| `commerce.productListViews.value` | Incrementa la [Visualizzazioni carrello](../../components/metrics/cart-views.md) metrica per la quantità desiderata. |
| `commerce.productViews.id` | Si applica [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) al [Visualizzazioni prodotto](../../components/metrics/product-views.md) metrica. |
| `commerce.productViews.value` | Incrementa la [Visualizzazioni prodotto](../../components/metrics/product-views.md) metrica per la quantità desiderata. |
| `commerce.purchases.value` | Incrementa la [Ordini](../../components/metrics/orders.md) metrica per la quantità desiderata. |
| `device.manufacturer` | Il produttore del dispositivo mobile. |
| `device.model` | La dimensione mobile [Nome del dispositivo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `device.modelNumber` | Numero del modello del dispositivo mobile. |
| `device.colorDepth` | Aiuta a impostare [Profondità colore](../../components/dimensions/color-depth.md) dimensione. |
| `device.screenHeight` | Aiuta a impostare [Risoluzione monitor](../../components/dimensions/monitor-resolution.md) dimensione. Assicurati anche di impostare il campo XDM `device.screenWidth`. |
| `device.screenWidth` | Aiuta a impostare [Risoluzione monitor](../../components/dimensions/monitor-resolution.md) dimensione. Assicurati anche di impostare il campo XDM `device.screenHeight`. |
| `device.type` | Il tipo di dispositivo mobile. |
| `environment.browserDetails.acceptLanguage` | Aiuta a impostare [Lingua](../../components/dimensions/language.md) dimensione. |
| `environment.browserDetails.cookiesEnabled` | Imposta la [Supporto per cookie](../../components/dimensions/cookie-support.md) dimensione. I valori validi includono `Y` (il browser accetta i cookie) e `N` (il browser rifiuta i cookie). |
| `environment.browserDetails.javaEnabled` | Imposta la [Java abilitato](../../components/dimensions/java-enabled.md) dimensione. I valori validi includono `Y` (Java è abilitato) e `N` (Java è disabilitato). |
| `environment.browserDetails.userAgent` | Utilizzato come fallback [visitatore univoco](../../components/metrics/unique-visitors.md) metodo di identificazione. Generalmente popolato utilizzando `User-Agent` Intestazione della richiesta HTTP. Puoi mappare questo campo su un eVar se desideri utilizzarlo nei rapporti. |
| `environment.browserDetails.viewportHeight` | Imposta la [Altezza browser](../../components/dimensions/browser-height.md) dimensione. |
| `environment.browserDetails.viewportWidth` | Imposta la [Larghezza browser](../../components/dimensions/browser-width.md) dimensione. |
| `environment.carrier` | La dimensione mobile [Nome gestore](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.connectionType` | Aiuta a impostare [Tipo di connessione](../../components/dimensions/connection-type.md) dimensione. |
| `environment.ipV4` | Utilizzato come fallback [visitatore univoco](../../components/metrics/unique-visitors.md) metodo di identificazione. Generalmente popolato utilizzando `X-Forwarded-For` Intestazione HTTP. |
| `environment.language` | La dimensione mobile Locale. |
| `environment.operatingSystem` | La dimensione mobile [Sistema operativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.operatingSystemVersion` | La dimensione mobile [Versione sistema operativo](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html#dimensions). |
| `environment.type` | Indica se l’evento proviene da un [indossabile](https://experienceleague.adobe.com/docs/mobile-services/android/wearables-android/c-android-wearables--additional-notes.html) dispositivo. I valori validi includono `Application` (l’evento proviene dall’app), `Extension` (l’evento proviene dall’app wearable), oppure `Widget` (l&#39;evento proviene da un widget mobile). |
| `_experience.analytics.customDimensions.eVars.eVar1` -<br/>`_experience.analytics.customDimensions.eVars.eVar250` | Imposta i rispettivi [eVar](../../components/dimensions/evar.md) dimensione. |
| `_experience.analytics.customDimensions.listProps.prop1.delimiter` -<br/>`_experience.analytics.customDimensions.listProps.prop75.delimiter` | Il delimitatore utilizzato per una data [Prop elenco](../vars/page-vars/prop.md#list-props). |
| `_experience.analytics.customDimensions.listProps.prop1.values` -<br/>`_experience.analytics.customDimensions.listProps.prop75.values` | Matrice di stringhe contenente il rispettivo [Prop elenco](../vars/page-vars/prop.md#list-props) valori. |
| `_experience.analytics.customDimensions.lists.list1.list` -<br/>`_experience.analytics.customDimensions.lists.list3.list` | Imposta i rispettivi [Variabile elenco](../vars/page-vars/list.md). |
| `_experience.analytics.customDimensions.props.prop1` -<br/>`_experience.analytics.customDimensions.props.prop75` | Imposta i rispettivi [Prop](../../components/dimensions/prop.md) dimensione. |
| `_experience.analytics.event1to100.event1.id` -<br/>`_experience.analytics.event901to1000.event1000.value` | Si applica [serializzazione degli eventi](../vars/page-vars/events/event-serialization.md) al rispettivo [Eventi personalizzati](../../components/metrics/custom-events.md) metrica. |
| `_experience.analytics.event1to100.event1.value` -<br/>`_experience.analytics.event901to1000.event1000.value` | Incrementa il rispettivo [Eventi personalizzati](../../components/metrics/custom-events.md) metrica per la quantità desiderata. |
| `identityMap.ECID[0].id` | La [ID del servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). |
| `marketing.trackingCode` | Imposta la [Codice di tracciamento](../../components/dimensions/tracking-code.md) dimensione. |
| `media.mediaTimed.completes.value` | Metrica Media Analytics [Contenuto completato](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-complete). |
| `media.mediaTimed.dropBeforeStart.value` | `c.a.media.view`, `c.a.media.timePlayed`, `c.a.media.play` |
| `media.mediaTimed.federated.value` | Metrica Media Analytics [Dati federati](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#federated-data). |
| `media.mediaTimed.firstQuartiles.value` | Metrica Media Analytics [Marcatore progresso 25 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#twenty-five-progress-marker). |
| `media.mediaTimed.mediaSegmentView.value` | Metrica Media Analytics [Visualizzazioni dei segmenti di contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment-views). |
| `media.mediaTimed.midpoints.value` | Metrica Media Analytics [Marcatore progresso 50 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#fifty-progress-marker). |
| `media.mediaTimed.pauseTime.value` | Metrica Media Analytics [Durata totale pausa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#total-pause-duration). |
| `media.mediaTimed.pauses.value` | Metrica Media Analytics [Pausa eventi](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#pause-events). |
| `media.mediaTimed.primaryAssetReference.`<br/>`@id` | Dimensione Media Analytics [ID risorsa](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#asset-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`dc:title` | Dimensione Media Analytics [Nome video](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-name). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Creator[N].iptc4xmpExt:Name` | Dimensione Media Analytics [Originatore](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#originator). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Episode.iptc4xmpExt:Number` | Dimensione Media Analytics [Episodio](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#episode). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Genre` | Dimensione Media Analytics [Genere](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#genre). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Rating[N].iptc4xmpExt:RatingValue` | Dimensione Media Analytics [Valutazione dei contenuti](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-rating). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Season.iptc4xmpExt:Number` | Dimensione Media Analytics [Stagione](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#season). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Identifier` | Dimensione Media Analytics [ID contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-id). |
| `media.mediaTimed.primaryAssetReference.`<br/>`iptc4xmpExt:Series.iptc4xmpExt:Name` | Dimensione Media Analytics [Mostra](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show). |
| `media.mediaTimed.primaryAssetReference.`<br/>`showType` | Dimensione Media Analytics [Mostra tipo](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#show-type). |
| `media.mediaTimed.primaryAssetReference.`<br/>`xmpDM:duration` | Dimensione Media Analytics [Lunghezza video](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#video-length). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`@id` | Dimensione Media Analytics [ID sessione multimediale](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-session-id). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastChannel` | Dimensione Media Analytics [Canale del contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-channel). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastContentType` | Dimensione Media Analytics [Tipo di contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`broadcastNetwork` | Dimensione Media Analytics [Rete](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#network). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`mediaSegmentView.value` | Dimensione Media Analytics [Segmento di contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-segment). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerName` | Dimensione Media Analytics [Nome del lettore di contenuti](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-player-name). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`playerSDKVersion.version` | Dimensione Media Analytics [Versione SDK](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#sdk-version). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`sourceFeed` | Dimensione Media Analytics [Tipo di feed multimediale](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-feed-type). |
| `media.mediaTimed.primaryAssetViewDetails.`<br/>`streamFormat` | Dimensione Media Analytics [Formato flusso](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#stream-format). |
| `media.mediaTimed.progress10.value` | Metrica Media Analytics [Marcatore progresso 10 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ten-progress-marker). |
| `media.mediaTimed.progress95.value` | Metrica Media Analytics [Marcatore progresso 95 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#ninety-five-progress-marker). |
| `media.mediaTimed.resumes.value` | Metrica Media Analytics [Riprende il contenuto](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-resumes). |
| `media.mediaTimed.starts.value` | Metrica Media Analytics [Media Starts](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-starts). |
| `media.mediaTimed.thirdQuartiles.value` | Metrica Media Analytics [Marcatore progresso 75 %](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#seventy-five-progress-marker). |
| `media.mediaTimed.timePlayed.value` | Metrica Media Analytics [Tempo contenuto trascorso](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#content-time-spent). |
| `media.mediaTimed.totalTimePlayed.value` | Metrica Media Analytics [Tempo trascorso per contenuti multimediali](https://experienceleague.adobe.com/docs/media-analytics/using/metrics-and-metadata/audio-video-parameters.html#media-time-spent). |
| `placeContext.geo.latitude` | La dimensione mobile Latitude. |
| `placeContext.geo.longitude` | La dimensione Mobile Longitudine. |
| `placeContext.geo.postalCode` | La [Codice postale](../../components/dimensions/zip-code.md) dimensione. |
| `placeContext.geo.stateProvince` | La [Stati Uniti](../../components/dimensions/us-states.md) dimensione. |
| `productListItems[].lineItemId` | La [Categoria](../../components/dimensions/category.md) dimensione. |
| `productListItems[].name` | La [Prodotto](../../components/dimensions/product.md) dimensione. |
| `productListItems[].priceTotal` | Aiuta a determinare il [Entrate](../../components/metrics/revenue.md) metrica. |
| `productListItems[].quantity` | Aiuta a determinare il [Unità](../../components/metrics/units.md) metrica. |
| `web.webInteraction.URL` | La [linkURL](../vars/config-vars/linkurl.md) variabile di implementazione. |
| `web.webInteraction.name` | La [Collegamento personalizzato](../../components/dimensions/custom-link.md), [Collegamento di download](../../components/dimensions/download-link.md)oppure [Collegamento di uscita](../../components/dimensions/exit-link.md) a seconda del valore in `web.webInteraction.type` |
| `web.webInteraction.type` | Determina il tipo di collegamento su cui è stato fatto clic. I valori validi includono `other` (Collegamenti personalizzati), `download` (collegamenti di download) e `exit` (Collegamenti di uscita). |
| `web.webPageDetails.URL` | La [URL della pagina](../../components/dimensions/page-url.md) dimensione. |
| `web.webPageDetails.errorPage` | Flag che consente di determinare le &quot;Pagine non trovate&quot; [dimension](../../components/dimensions/pages-not-found.md) e [metrica](../../components/metrics/pages-not-found.md). |
| `web.webPageDetails.name` | La [Pagina](../../components/dimensions/page.md) dimensione. |
| `web.webPageDetails.server` | La [Server](../../components/dimensions/server.md) dimensione. |
| `web.webPageDetails.siteSection` | La [Sezione del sito](../../components/dimensions/site-section.md) dimensione. |
| `web.webReferrer.URL` | La [Referrer](../../components/dimensions/referrer.md) dimensione. |

{style=&quot;table-layout:auto&quot;}

<!-- `environment.browserDetails.javaScriptVersion` and `web.webPageDetails.homePage` were included in the original table, but they no longer exist in Analytics. | -->

## Mappatura di altri campi XDM su variabili Analytics

Se esistono dimensioni o metriche da aggiungere ad Adobe Analytics, puoi farlo tramite [Variabili di dati di contesto](../vars/page-vars/contextdata.md). Tutti gli elementi del campo XDM vengono inviati ad Adobe Analytics come dati contestuali con il prefisso . `a.x`. Puoi quindi mappare questa variabile di dati di contesto alla variabile di Analytics desiderata utilizzando [Regole di elaborazione](../../admin/admin/c-processing-rules/processing-rules.md). Ad esempio, se invii il seguente evento:

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
