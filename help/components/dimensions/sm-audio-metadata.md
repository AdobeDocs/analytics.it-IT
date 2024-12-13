---
title: Dimensioni dei metadati audio per contenuti multimediali in streaming
description: Dimensioni disponibili quando si abilita [!UICONTROL Audio Metadata] per una suite di rapporti.
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 8%

---

# Dimensioni dei metadati audio per contenuti multimediali in streaming

Le dimensioni degli annunci per contenuti multimediali in streaming forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di raccolta di contenuti multimediali in streaming. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Streaming Media Collection]**. Per informazioni, contatta il team dell’account Adobe.

Quando abiliti **[!UICONTROL Audio Metadata]** in [Generazione rapporti multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le seguenti dimensioni:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Album | Nome dell&#39;album. | Avvio file multimediale, Chiusura file multimediale | `a.media.album` |
| Artista | Il nome dell&#39;artista. | Avvio file multimediale, Chiusura file multimediale | `a.media.artist` |
| Autore | Nome dell&#39;autore dell&#39;audiolibro. | Avvio file multimediale, Chiusura file multimediale | `a.media.author` |
| Etichetta | Nome dell&#39;etichetta discografica. | Avvio file multimediale, Chiusura file multimediale | `a.media.label` |
| Editore | Nome dell&#39;autore del contenuto audio. | Avvio file multimediale, Chiusura file multimediale | `a.media.publisher` |
| Stazione | Nome o ID della stazione radio. | Avvio file multimediale, Chiusura file multimediale | `a.media.station` |

{style="table-layout:auto"}
