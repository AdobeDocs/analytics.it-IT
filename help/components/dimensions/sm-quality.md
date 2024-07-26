---
title: Dimensioni di qualità dei contenuti multimediali in streaming
description: Dimensioni disponibili quando si abilita [!UICONTROL Media Quality] per una suite di rapporti.
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 1%

---

# Dimensioni di qualità dei contenuti multimediali in streaming

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Media Quality] per una suite di rapporti. Vedi [Metriche di qualità dei contenuti multimediali in streaming](../metrics/sm-quality.md) per le metriche disponibili.*

Le dimensioni di qualità dei contenuti multimediali in streaming forniscono rapporti relativi alla qualità dei contenuti utilizzati dal visitatore. L&#39;utilizzo di queste dimensioni richiede [!UICONTROL Adobe Streaming Media Collection add-on]. Per informazioni, contatta il team dell’account Adobe.

Quando abiliti **[!UICONTROL Media Quality]** in [Generazione rapporti multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le seguenti dimensioni:

| Nome Dimension | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Bitrate medio | Il bitrate medio, in intervalli di bucket di 100 KBPS. Viene calcolata come media ponderata di tutti i valori di bitrate in relazione alla durata di riproduzione per una determinata sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.bitrateAverageBucket` |
| Modifiche al bitrate | Il numero di modifiche del bitrate che si sono verificate durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.bitrateChangeCount` |
| Eventi buffer | Il numero di volte in cui il lettore multimediale è entrato in uno stato di buffer durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.bufferCount` |
| Durata totale buffer | La quantità totale di tempo impiegato per il buffering, in secondi. | Chiusura file multimediale | `a.media.qoe.bufferTime` |
| Fotogrammi persi | Numero totale di fotogrammi saltati durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.droppedFrameCount` |
| Errori | Numero totale di errori che si sono verificati durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.qoe.errorCount` |
| ID errore esterni | Tutti gli ID di errore univoci da qualsiasi origine esterna, ad esempio errori CDN. Devi fornire i codici di errore o gli ID desiderati. Sono consentiti più ID di errore. | Chiusura file multimediale | `a.media.qoe.externalErrors` |
| ID errore SDK del lettore | Tutti gli ID di errore univoci generati dall’SDK del lettore di contenuti. Devi fornire i codici di errore o gli ID desiderati. Sono consentiti più ID di errore. | Chiusura file multimediale | `a.media.qoe.playerSdkErrors` |
| Tempo di avvio | Il valore predefinito è `0` se non è impostato tramite QoSObject. Imposta il valore in millisecondi. Analysis Workspace segnala questa dimensione in secondi. | Avvio file multimediale, Chiusura file multimediale | `a.media.qoe.timeToStart` |

{style="table-layout:auto"}
