---
title: Dimensioni di qualità dei servizi di contenuti multimediali in streaming
description: Dimensioni disponibili quando si abilita [!UICONTROL Media Quality] per una suite di rapporti.
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---

# Dimensioni di qualità dei servizi di contenuti multimediali in streaming

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Media Quality] per una suite di rapporti. Per informazioni sulle metriche disponibili, vedere [Metriche di qualità dei servizi multimediali in streaming](../metrics/sm-quality.md).*

Le dimensioni di qualità dei servizi di contenuti multimediali in streaming forniscono rapporti relativi alla qualità dei contenuti utilizzati dal visitatore. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Quality]** in [Generazione rapporti multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le seguenti dimensioni:

| Nome dimensioni | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Average bitrate]** | Il bitrate medio, in intervalli di bucket di 100 KBPS. Viene calcolata come media ponderata di tutti i valori di bitrate in relazione alla durata di riproduzione per una determinata sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`bitrateAverageBucket` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrate`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateAverageBucket` |
| **[!UICONTROL Bitrate changes]** | Il numero di modifiche del bitrate che si sono verificate durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL Buffer events]** | Il numero di volte in cui il lettore multimediale è entrato in uno stato di buffer durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bufferCount` |
| **[!UICONTROL Total buffer duration]** | La quantità totale di tempo impiegato per il buffering, in secondi. | Chiusura file multimediale | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bufferTime` |
| **[!UICONTROL Dropped frames]** | Numero totale di fotogrammi saltati durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`droppedFrames` |
| **[!UICONTROL Errors]** | Numero totale di errori che si sono verificati durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`errorCount` |
| **[!UICONTROL External error IDs]** | Tutti gli ID di errore univoci da qualsiasi origine esterna, ad esempio errori CDN. Devi fornire i codici di errore o gli ID desiderati. Sono consentiti più ID di errore. | Chiusura file multimediale | `a.media.qoe.`<br>`externalErrors` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`externalErrors` |
| **[!UICONTROL Player SDK error IDs]** | Tutti gli ID di errore univoci generati dal lettore di contenuti SDK. Devi fornire i codici di errore o gli ID desiderati. Sono consentiti più ID di errore. | Chiusura file multimediale | `a.media.qoe.`<br>`playerSdkErrors` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`playerSdkErrors` |
| **[!UICONTROL Time to start]** | Il valore predefinito è `0` se non è impostato tramite QoSObject. Imposta il valore in millisecondi. Analysis Workspace segnala questa dimensione in secondi. | Avvio file multimediale, Chiusura file multimediale | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`timeToStart` |
