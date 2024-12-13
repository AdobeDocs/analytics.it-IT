---
title: Metriche di tracciamento dello stato del lettore multimediale in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Player State Tracking] per una suite di rapporti.
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---

# Metriche di tracciamento dello stato del lettore multimediale in streaming

Le metriche di tracciamento dello stato del lettore multimediale in streaming forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di raccolta multimediale in streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Streaming Media Collection]**. Per informazioni, contatta il team dell’account Adobe.

Quando abiliti **[!UICONTROL Player State Tracking]** in [Report multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Flussi interessati dalla funzione sottotitoli | Attivazione se durante una sessione di riproduzione si è verificato almeno uno stato di Sottotitoli. | Chiusura file multimediale | `a.media.states.closedcaptioning.set` |
| Conteggi dei sottotitoli | Il numero di volte in cui il video è entrato in uno stato Sottotitoli. | Chiusura file multimediale | `a.media.states.closedcaptioning.count` |
| Durata totale sottotitoli | La quantità di tempo in cui il video era in stato Sottotitoli, in secondi. | Chiusura file multimediale | `a.media.states.closedcaptioning.time` |
| Flussi interessati dallo schermo intero | Attivazione se durante una sessione di riproduzione si è verificato almeno uno stato Schermo intero. | Chiusura file multimediale | `a.media.states.fullscreen.set` |
| Conteggi schermo intero | Il numero di volte in cui il video è entrato in uno stato Schermo intero. | Chiusura file multimediale | `a.media.states.fullscreen.count` |
| Durata totale schermo intero | La quantità di tempo in cui il video era nello stato Schermo intero, in secondi. | Chiusura file multimediale | `a.media.states.fullscreen.time` |
| Flussi interessati da in focus | Attivazione se durante una sessione di riproduzione si è verificato almeno uno stato In Focus. | Chiusura file multimediale | `a.media.states.infocus.set` |
| Conteggi in focus | Il numero di volte in cui il video è entrato in stato In focus. | Chiusura file multimediale | `a.media.states.infocus.count` |
| Durata totale in focus | La quantità di tempo in cui il video era in stato In focus, in secondi. | Chiusura file multimediale | `a.media.states.infocus.time` |
| Flussi interessati dalla disattivazione audio | Attivazione se durante una sessione di riproduzione si è verificato almeno uno stato di disattivazione audio. | Chiusura file multimediale | `a.media.states.mute.set` |
| Conteggi disattivazione audio | Il numero di volte in cui il video è entrato in uno stato di disattivazione audio. | Chiusura file multimediale | `a.media.states.mute.count` |
| Durata totale disattivazione audio | La quantità di tempo in cui il video era in stato di disattivazione audio, in secondi. | Chiusura file multimediale | `a.media.states.mute.time` |
| Flussi interessati da picture in picture | Attivazione se durante una sessione di riproduzione si è verificato almeno uno stato di immagine nell’immagine (Picture In Picture). | Chiusura file multimediale | `a.media.states.pictureinpicture.set` |
| Conteggio immagini nell’immagine (Picture in Picture) | Il numero di volte in cui il video è entrato in uno stato di immagine nell’immagine (Picture In Picture). | Chiusura file multimediale | `a.media.states.pictureinpicture.count` |
| Durata totale immagine nell’immagine (Picture in Picture) | Quantità di tempo in cui il video era in stato di immagine nell’immagine (Picture in Picture), in secondi. | Chiusura file multimediale | `a.media.states.pictureinpicture.time` |

{style="table-layout:auto"}
