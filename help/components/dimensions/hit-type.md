---
title: Tipo di hit
description: Determina se l'hit era un hit in primo piano o in background.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---

# Tipo di hit

La dimensione &quot;Hit type&quot; (Tipo di hit) determina se un’app mobile era in primo piano o in background quando l’hit è stato inviato ai server di raccolta dati di Adobe. Questa dimensione è pertinente solo alle suite di rapporti che contengono dati per le applicazioni mobili. I dati del browser raccolti tramite AppMeasurement segnalano sempre l&#39;hit come &quot;In primo piano&quot;.

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni SDK per dispositivi mobili sulla versione 4.13.6 o successiva. Se non utilizzi l’SDK per dispositivi mobili, tutti gli hit sono elencati sotto l’elemento dimensione &quot;In primo piano&quot;. Se è selezionata l’opzione &quot;Disabilita reporting legacy e attribuzione per hit in background&quot;, gli hit in background verranno visualizzati solo in [Suite di rapporti virtuali](../vrs/vrs-mobile-visit-processing.md).

## Elementi Dimension

Gli elementi del Dimension includono `"Foreground"` e `"Background"`. Qualsiasi hit che non è stato inviato in background di un’app mobile appartiene alla `"Foreground"` elemento dimensione. Qualsiasi hit inviato in cui l’app mobile era in background appartiene alla `"Background"` elemento dimensione.
