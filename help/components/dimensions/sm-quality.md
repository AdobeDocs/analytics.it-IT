---
title: Dimensioni di qualità dei servizi di contenuti multimediali in streaming
description: Dimensioni disponibili quando si abilita [!UICONTROL Media Quality] per una suite di rapporti.
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Dimensioni di qualità dei servizi di contenuti multimediali in streaming

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Media Quality] per una suite di rapporti. Per informazioni sulle metriche disponibili, vedere [Metriche di qualità dei servizi multimediali in streaming](../metrics/sm-quality.md).*

Le dimensioni di qualità dei servizi di contenuti multimediali in streaming forniscono rapporti relativi alla qualità dei contenuti utilizzati dal visitatore. L&#39;utilizzo di queste dimensioni richiede [!UICONTROL Adobe Analytics for Streaming Media Ad-on]. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Quality]** in [Generazione rapporti multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le seguenti dimensioni:

| Nome dimensioni | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Bitrate medio | Il bitrate medio, in intervalli di bucket di 100 KBPS. Viene calcolata come media ponderata di tutti i valori di bitrate in relazione alla durata di riproduzione per una determinata sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.bitrateAverageBucket` |
| Modifiche al bitrate | Il numero di modifiche del bitrate che si sono verificate durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.bitrateChangeCount` |
| Eventi buffer | Il numero di volte in cui il lettore multimediale è entrato in uno stato di buffer durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.bufferCount` |
| Durata totale buffer | La quantità totale di tempo impiegato per il buffering, in secondi. | Chiusura file multimediale | `a.media.qoe.bufferTime` |
| Fotogrammi persi | Numero totale di fotogrammi saltati durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.droppedFrameCount` |
| Errori | Numero totale di errori che si sono verificati durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.errorCount` |
| ID errore esterni | Tutti gli ID di errore univoci da qualsiasi origine esterna, ad esempio errori CDN. Devi fornire i codici di errore o gli ID desiderati. Sono consentiti più ID di errore. | Chiusura file multimediale | `a.media.qoe.externalErrors` |
| ID errore SDK del lettore | Tutti gli ID di errore univoci generati dal lettore di contenuti SDK. Devi fornire i codici di errore o gli ID desiderati. Sono consentiti più ID di errore. | Chiusura file multimediale | `a.media.qoe.playerSdkErrors` |
| Tempo di avvio | Il valore predefinito è `0` se non è impostato tramite QoSObject. Imposta il valore in millisecondi. Analysis Workspace segnala questa dimensione in secondi. | Avvio file multimediale, Chiusura file multimediale | `a.media.qoe.timeToStart` |

{style="table-layout:auto"}
