---
title: Dimensioni dei metadati video di Streaming Media Services
description: Dimensioni disponibili quando si abilita [!UICONTROL Video Metadata] per una suite di rapporti.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 7%

---

# Dimensioni dei metadati video di Streaming Media Services

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Video Metadata] per una suite di rapporti. Per informazioni sulle metriche disponibili, vedere [Metriche metadati video di Streaming Media Services](../metrics/sm-video-metadata.md).*

I servizi e le dimensioni di Streaming Media forniscono funzionalità di reporting supplementari per la raccolta dati tramite le librerie di raccolta di servizi multimediali in streaming. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Video Metadata]** in [Generazione rapporti multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le seguenti dimensioni:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Caricamenti degli annunci | Tipo di annuncio caricato. | Da definire | `a.media.adLoad` |
| Fascia oraria | L’ora del giorno in cui il contenuto è stato trasmesso o riprodotto. Qualsiasi valore stringa è supportato. | Avvio file multimediale, Chiusura file multimediale | `a.media.dayPart` |
| Episodio | Numero dell’episodio. | Avvio file multimediale, Chiusura file multimediale | `a.media.episode` |
| Tipo di feed multimediale | Tipo di feed. | Avvio file multimediale, Chiusura file multimediale | `a.media.feed` |
| Genere | Tipo o raggruppamento di contenuti definiti dal produttore del contenuto. Questa dimensione supporta più valori, delimitati da virgole. | Avvio file multimediale, Chiusura file multimediale | `a.media.genre` |
| MVPD | Il MVPD fornito dall’autenticazione di Adobe. | Avvio file multimediale, Chiusura file multimediale | `a.media.pass.mvpd` |
| Rete | Nome di rete o di canale | Avvio file multimediale, Chiusura file multimediale | `a.media.network` |
| Stagione | Il numero di stagione a cui appartiene lo spettacolo. | Avvio file multimediale, Chiusura file multimediale | `a.media.season` |
| Spettacolo | Il nome del programma o della serie. | Avvio file multimediale, Chiusura file multimediale | `a.media.show` |
| Tipo di spettacolo | Numero intero che rappresenta il tipo di contenuto.<br>`0`: episodio completo<br>`1`: anteprima o trailer<br>`2`: clip<br>`3`: altro | Avvio file multimediale, Chiusura file multimediale | `a.media.type` |

{style="table-layout:auto"}
