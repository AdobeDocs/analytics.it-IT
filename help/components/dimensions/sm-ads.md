---
title: Servizi e dimensioni per contenuti multimediali in streaming
description: Dimensioni disponibili quando si abilita [!UICONTROL Media Ads] per una suite di rapporti.
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 7%

---

# Servizi e dimensioni per contenuti multimediali in streaming

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Media Ads] per una suite di rapporti. Vedi [Metriche degli annunci multimediali in streaming](../metrics/sm-ads.md) per le metriche disponibili.*

I servizi e le dimensioni di Streaming Media forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di Streaming Media Services. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Ads]** in [Generazione rapporti multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le seguenti dimensioni:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Annuncio | L’identificatore univoco dell’annuncio. | Avvio annuncio, Chiusura annuncio | `a.media.ad.name` |
| Nome annuncio (variabile) | Il nome descrittivo dell’annuncio. È disponibile anche una dimensione di classificazione denominata &quot;Nome annuncio&quot;, che ha uno scopo simile. Questa dimensione e la classificazione sono trattate come due dimensioni distinte. | Avvio annuncio, Chiusura annuncio | `a.media.ad.friendlyName` |
| Nome del lettore dell’annuncio | Nome del lettore che esegue il rendering dell’annuncio. | Avvio annuncio, Chiusura annuncio | `a.media.ad.playerName` |
| Lunghezza annuncio (variabile) | La lunghezza dell’annuncio video, in secondi. | Avvio annuncio, Chiusura annuncio | `a.media.ad.length` |
| Ad pod | Identificatore univoco per il pod dell’annuncio. | Avvio annuncio, Chiusura annuncio | `a.media.ad.pod` |
| Posizione annuncio nel pod | Posizione dell’indice dell’annuncio all’interno dell’interruzione pubblicitaria principale (indicizzata a 0). | Avvio annuncio, Chiusura annuncio | `a.media.ad.podPosition` |
| Inserzionista | L’azienda o il marchio visualizzato nell’annuncio. | Avvio annuncio, Chiusura annuncio | `a.media.ad.advertiser` |
| ID campagna | ID della campagna pubblicitaria | Avvio annuncio, Chiusura annuncio | `a.media.ad.campaign` |

{style="table-layout:auto"}

Oltre alle dimensioni di cui sopra, Adobe crea automaticamente le seguenti dimensioni di classificazione. Per visualizzare i rapporti che utilizzano queste dimensioni, devi caricare i dati di classificazione.

| Nome classificazione | Dimensione principale | Descrizione |
| --- | --- | --- |
| ID risorsa | [Contenuto](sm-core.md) | Identificatore univoco del contenuto della risorsa multimediale. Alcuni esempi includono l’identificatore di un episodio di una serie TV, di una risorsa di un film o di un evento live. Questi ID sono in genere derivati da autorità di metadati come EIDR, TMS/Gracenote, Rovi o da altri sistemi proprietari o interni. |
| Valutazione dei contenuti | [Contenuto](sm-core.md) | La classificazione è definita dalle linee guida TV per genitori. |
| Data della prima messa in onda | [Contenuto](sm-core.md) | La data in cui il contenuto è andato in onda per la prima volta in televisione. Poiché questa dimensione di classificazione è una stringa, è consentito qualsiasi formato di data. Adobe consiglia di utilizzare un formato data coerente, ad esempio `YYYY-MM-DD`. |
| Data prima versione digitale | [Contenuto](sm-core.md) | La data in cui il contenuto è andato in onda per la prima volta su qualsiasi canale o piattaforma digitale. Poiché questa dimensione di classificazione è una stringa, è consentito qualsiasi formato di data. Adobe consiglia di utilizzare un formato data coerente, ad esempio `YYYY-MM-DD`. |
| Lunghezza annuncio | Annuncio | La lunghezza dell’annuncio video, in secondi. |
| Nome annuncio | Annuncio | Il nome descrittivo dell’annuncio. È l’equivalente di classificazione di &quot;Nome annuncio (variabile)&quot;. |
| ID creatività | Annuncio | ID della creatività dell’annuncio. |
| Nome del pod | Ad pod | Il nome descrittivo del pod dell’annuncio. |
| Posizione del pod | Ad pod | Lo scostamento dell’interruzione pubblicitaria all’interno del contenuto, in secondi. |

{style="table-layout:auto"}
