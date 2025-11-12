---
title: Metriche di tracciamento dello stato del lettore di servizi multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Player State Tracking] per una suite di rapporti.
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---

# Metriche di tracciamento dello stato del lettore di servizi multimediali in streaming

Le metriche di tracciamento dello stato del lettore di servizi multimediali in streaming forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di servizi multimediali in streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Player State Tracking]** in [Report multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Streams impacted by closed captioning]** | Attivazione se durante una sessione di riproduzione si è verificato almeno uno stato di Sottotitoli. | Chiusura file multimediale | `a.media.states.`<br>`closedcaptioning.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Closed captioning counts]** | Il numero di volte in cui il video è entrato in uno stato Sottotitoli. | Chiusura file multimediale | `a.media.states.`<br>`closedcaptioning.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Closed captioning total duration]** | La quantità di tempo in cui il video era in stato Sottotitoli, in secondi. | Chiusura file multimediale | `a.media.states.`<br>`closedcaptioning.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by full screen]** | Attivazione se durante una sessione di riproduzione si è verificato almeno uno stato Schermo intero. | Chiusura file multimediale | `a.media.states.`<br>`fullscreen.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Full screen counts]** | Il numero di volte in cui il video è entrato in uno stato Schermo intero. | Chiusura file multimediale | `a.media.states.`<br>`fullscreen.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Full screen total duration]** | La quantità di tempo in cui il video era nello stato Schermo intero, in secondi. | Chiusura file multimediale | `a.media.states.`<br>`fullscreen.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by in focus]** | Attivazione se durante una sessione di riproduzione si è verificato almeno uno stato In Focus. | Chiusura file multimediale | `a.media.states.`<br>`infocus.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL In focus counts]** | Il numero di volte in cui il video è entrato in stato In focus. | Chiusura file multimediale | `a.media.states.`<br>`infocus.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL In focus total duration]** | La quantità di tempo in cui il video era in stato In focus, in secondi. | Chiusura file multimediale | `a.media.states.`<br>`infocus.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by mute]** | Attivazione se durante una sessione di riproduzione si è verificato almeno uno stato di disattivazione audio. | Chiusura file multimediale | `a.media.states.`<br>`mute.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL Mute counts]** | Il numero di volte in cui il video è entrato in uno stato di disattivazione audio. | Chiusura file multimediale | `a.media.states.`<br>`mute.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Mute total duration]** | La quantità di tempo in cui il video era in stato di disattivazione audio, in secondi. | Chiusura file multimediale | `a.media.states.`<br>`mute.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL Streams impacted by picture in picture]** | Attivazione se durante una sessione di riproduzione si è verificato almeno uno stato di immagine nell’immagine (Picture In Picture). | Chiusura file multimediale | `a.media.states.`<br>`pictureinpicture.set` | `mediaReporting.states.`<br>`[*].isSet` |
| **[!UICONTROL Picture in picture counts]** | Il numero di volte in cui il video è entrato in uno stato di immagine nell’immagine (Picture In Picture). | Chiusura file multimediale | `a.media.states.`<br>`pictureinpicture.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL Picture in picture total duration]** | Quantità di tempo in cui il video era in stato di immagine nell’immagine (Picture in Picture), in secondi. | Chiusura file multimediale | `a.media.states.`<br>`pictureinpicture.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
