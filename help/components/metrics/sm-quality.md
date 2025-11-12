---
title: Metriche di qualità dei servizi di contenuti multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Media Quality] per una suite di rapporti.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 2%

---

# Metriche di qualità dei servizi di contenuti multimediali in streaming

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Media Quality] per una suite di rapporti. Vedere [Dimensioni di qualità dei servizi multimediali in streaming](../dimensions/sm-quality.md) per le dimensioni disponibili.*

Le metriche di qualità dei servizi di contenuti multimediali in streaming forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie dei servizi di contenuti multimediali in streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Quality]** in [Report multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Average bitrate]** | Media ponderata di tutti i valori di bitrate per la durata di riproduzione di una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`bitrateAverage` | `xdm.mediaReporting.`<br>`qoeDataDetails.bitrateAverage` |
| **[!UICONTROL Bitrate change impacted streams]** | Valore booleano che viene attivato se il bitrate cambia almeno una volta durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`bitrateChange` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBitrateChangeImpactedStreams` |
| **[!UICONTROL Bitrate changes]** | Il numero di volte in cui il bitrate è cambiato. | Chiusura file multimediale | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL Buffer impacted streams]** | Valore booleano che viene attivato se il video entra in uno stato buffer almeno una volta. | Chiusura file multimediale | `a.media.qoe.`<br>`buffer` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBufferImpactedStreams` |
| **[!UICONTROL Buffer events]** | Il numero di volte in cui il video è stato inserito nel buffer durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferCount` |
| **[!UICONTROL Total buffer duration]** | Il tempo impiegato da un video per il buffering in tutti gli eventi del buffer, in secondi. | Chiusura file multimediale | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferTime` |
| **[!UICONTROL Drops before start]** | Valore booleano che viene attivato se un utente si chiude prima dell’avvio del contenuto principale di un video. | Chiusura file multimediale | `a.media.qoe.`<br>`dropBeforeStart` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`isDroppedBeforeStart` |
| **[!UICONTROL Dropped frames]** | Numero intero che rappresenta il numero totale di fotogrammi saltati durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.droppedFrames` |
| **[!UICONTROL Dropped frame impacted streams]** | Valore booleano che viene attivato quando vengono rilasciati fotogrammi durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`droppedFrames` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasDroppedFrameImpactedStreams` |
| **[!UICONTROL Error impacted streams]** | Valore booleano che viene attivato quando un video genera un errore in un momento qualsiasi durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`error` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasErrorImpactedStreams` |
| **[!UICONTROL Error events]** | Numero intero che rappresenta il numero totale di errori rilevati durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.errorCount` |
| **[!UICONTROL Time to start]** | Il tempo necessario per avviare un video, in millisecondi. Adobe converte e memorizza questo valore in secondi. | Chiusura file multimediale | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.timeToStart` |
