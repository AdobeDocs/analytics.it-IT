---
title: Metriche dei metadati video di Streaming Media Services
description: Metriche disponibili quando abiliti [!UICONTROL Video Metadata] per una suite di rapporti.
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 5%

---

# Metriche dei metadati video di Streaming Media Services

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Video metadata] per una suite di rapporti. Vedere [Dimensioni metadati video di Streaming Media Services](../dimensions/sm-video-metadata.md) per le dimensioni disponibili.*

Le metriche dei metadati video di Streaming Media Services forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di servizi multimediali in streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Video Metadata]** in [Report multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), è disponibile la metrica seguente:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Authorized]** | Valore booleano che viene attivato quando l’utente viene autorizzato tramite l’autenticazione di Adobe. | Avvio file multimediale, Chiusura file multimediale | `a.media.pass.auth` | `xdm.mediaCollection.`<br>`sessionDetails.authorized`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.authorized` |
