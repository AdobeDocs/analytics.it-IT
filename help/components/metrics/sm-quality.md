---
title: Metriche di qualità dei contenuti multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Media Quality] per una suite di rapporti.
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Metriche di qualità dei contenuti multimediali in streaming

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Media Quality] per una suite di rapporti. Vedi [Dimensioni di qualità Streaming Media](../dimensions/sm-quality.md) per le dimensioni disponibili.*

Le metriche di qualità dei contenuti multimediali in streaming forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di raccolta di contenuti multimediali in streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Streaming Media Collection]**. Per informazioni, contatta il team dell’account Adobe.

Quando abiliti **[!UICONTROL Media Quality]** in [Report multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Bitrate medio | Media ponderata di tutti i valori di bitrate per la durata di riproduzione di una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.bitrateAverage` |
| Flussi interessati dalla modifica del bitrate | Valore booleano che viene attivato se il bitrate cambia almeno una volta durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.bitrateChange` |
| Modifiche al bitrate | Il numero di volte in cui il bitrate è cambiato. | Chiusura file multimediale | `a.media.qoe.bitrateChangeCount` |
| Flussi interessati dal buffer | Valore booleano che viene attivato se il video entra in uno stato buffer almeno una volta. | Chiusura file multimediale | `a.media.qoe.buffer` |
| Eventi buffer | Il numero di volte in cui il video è stato inserito nel buffer durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.bufferCount` |
| Durata totale buffer | Il tempo impiegato da un video per il buffering in tutti gli eventi del buffer, in secondi. | Chiusura file multimediale | `a.media.qoe.bufferTime` |
| Perdite prima dell’inizio | Valore booleano che viene attivato se un utente si chiude prima dell’avvio del contenuto principale di un video. | Chiusura file multimediale | `a.media.qoe.dropBeforeStart` |
| Fotogrammi persi | Numero intero che rappresenta il numero totale di fotogrammi saltati durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.droppedFrameCount` |
| Flussi interessati da fotogrammi saltati | Valore booleano che viene attivato quando vengono rilasciati fotogrammi durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.droppedFrames` |
| Flussi interessati da errori | Valore booleano che viene attivato quando un video genera un errore in un momento qualsiasi durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.error` |
| Eventi di errore | Numero intero che rappresenta il numero totale di errori rilevati durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.errorCount` |
| Tempo di avvio | Il tempo necessario per avviare un video, in millisecondi. Adobe converte e memorizza questo valore in secondi. | Chiusura file multimediale | `a.media.qoe.timeToStart` |
