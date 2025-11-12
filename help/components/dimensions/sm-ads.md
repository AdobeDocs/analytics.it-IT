---
title: Servizi e dimensioni per contenuti multimediali in streaming
description: Dimensioni disponibili quando si abilita [!UICONTROL Media Ads] per una suite di rapporti.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 3%

---

# Servizi e dimensioni per contenuti multimediali in streaming

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Media Ads] per una suite di rapporti. Vedi [Metriche degli annunci multimediali in streaming](../metrics/sm-ads.md) per le metriche disponibili.*

I servizi e le dimensioni di Streaming Media forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di Streaming Media Services. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Ads]** in [Generazione rapporti multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le seguenti dimensioni:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Ad]** | L’identificatore univoco dell’annuncio. | Avvio annuncio, Chiusura annuncio | `a.media.ad.`<br>`name` | `xdm.mediaCollection.`<br>`advertisingDetails.name`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.name` |
| **[!UICONTROL Ad name (variable)]** | Il nome descrittivo dell’annuncio. È disponibile anche una dimensione di classificazione denominata &#39;[!UICONTROL Ad name]&#39;, che fornisce uno scopo simile. Questa dimensione e la classificazione sono trattate come due dimensioni distinte. | Avvio annuncio, Chiusura annuncio | `a.media.ad.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`advertisingDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.friendlyName` |
| **[!UICONTROL Ad player name]** | Nome del lettore che esegue il rendering dell’annuncio. | Avvio annuncio, Chiusura annuncio | `a.media.ad.`<br>`playerName` | `xdm.mediaCollection.`<br>`advertisingDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.playerName` |
| **[!UICONTROL Ad length (variable)]** | La lunghezza dell’annuncio video, in secondi. | Avvio annuncio, Chiusura annuncio | `a.media.ad.`<br>`length` | `xdm.mediaCollection.`<br>`advertisingDetails.length`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.length` |
| **[!UICONTROL Ad pod]** | Identificatore univoco per il pod dell’annuncio. | Avvio annuncio, Chiusura annuncio | `a.media.ad.`<br>`pod` | |
| **[!UICONTROL Ad in pod position]** | Posizione dell’indice dell’annuncio all’interno dell’interruzione pubblicitaria principale (indicizzata a 0). | Avvio annuncio, Chiusura annuncio | `a.media.ad.`<br>`podPosition` | `xdm.mediaCollection.`<br>`advertisingDetails.podPosition`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.podPosition` |
| **[!UICONTROL Advertiser]** | L’azienda o il marchio visualizzato nell’annuncio. | Avvio annuncio, Chiusura annuncio | `a.media.ad.`<br>`advertiser` | `xdm.mediaCollection.`<br>`advertisingDetails.advertiser`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.advertiser` |
| **[!UICONTROL Campaign ID]** | ID della campagna pubblicitaria | Avvio annuncio, Chiusura annuncio | `a.media.ad.`<br>`campaign` | `xdm.mediaCollection.`<br>`advertisingDetails.campaignID`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.campaignID` |

Oltre alle dimensioni di cui sopra, Adobe crea automaticamente le seguenti dimensioni di classificazione. Per visualizzare i rapporti che utilizzano queste dimensioni, devi caricare i dati di classificazione.

| Nome classificazione | Dimensione principale | Descrizione |
| --- | --- | --- |
| **[!UICONTROL Asset ID]** | [[!UICONTROL Content]](sm-core.md) | Identificatore univoco del contenuto della risorsa multimediale. Alcuni esempi includono l’identificatore di un episodio di una serie TV, di una risorsa di un film o di un evento live. Questi ID sono in genere derivati da autorità di metadati come EIDR, TMS/Gracenote, Rovi o da altri sistemi proprietari o interni. |
| **[!UICONTROL Content rating]** | [[!UICONTROL Content]](sm-core.md) | La classificazione è definita dalle linee guida TV per genitori. |
| **[!UICONTROL First air date]** | [[!UICONTROL Content]](sm-core.md) | La data in cui il contenuto è andato in onda per la prima volta in televisione. Poiché questa dimensione di classificazione è una stringa, è consentito qualsiasi formato di data. Adobe consiglia di utilizzare un formato data coerente, ad esempio `YYYY-MM-DD`. |
| **[!UICONTROL First digital date]** | [[!UICONTROL Content]](sm-core.md) | La data in cui il contenuto è andato in onda per la prima volta su qualsiasi canale o piattaforma digitale. Poiché questa dimensione di classificazione è una stringa, è consentito qualsiasi formato di data. Adobe consiglia di utilizzare un formato data coerente, ad esempio `YYYY-MM-DD`. |
| **[!UICONTROL Ad length]** | [!UICONTROL Ad] | La lunghezza dell’annuncio video, in secondi. |
| **[!UICONTROL Ad name]** | [!UICONTROL Ad] | Il nome descrittivo dell’annuncio. Equivalente di classificazione di &#39;[!UICONTROL Ad name (variable)]&#39;. |
| **[!UICONTROL Creative ID]** | [!UICONTROL Ad] | ID della creatività dell’annuncio. |
| **[!UICONTROL Pod name]** | [!UICONTROL Ad pod] | Il nome descrittivo del pod dell’annuncio. |
| **[!UICONTROL Pod position]** | [!UICONTROL Ad pod] | Lo scostamento dell’interruzione pubblicitaria all’interno del contenuto, in secondi. |
