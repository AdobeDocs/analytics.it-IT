---
title: Tipo di hit
description: Determina se l’hit è stato un hit in primo piano o in background.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# Tipo di hit

Il &quot;tipo di hit&quot; [dimensione](overview.md) determina se un’app mobile era in primo piano o in background quando l’hit è stato inviato ai server di raccolta dati Adobe. Questa dimensione è pertinente solo per le suite di rapporti che contengono dati per le applicazioni mobili. I dati del browser raccolti tramite AppMeasurement segnalano sempre l’hit come &quot;Primo piano&quot;.

## Popola questa dimensione con i dati

Questa dimensione funziona come previsto per tutte le implementazioni dell’SDK per dispositivi mobili nella versione 4.13.6 o successiva. Se non utilizzi l’SDK per dispositivi mobili, visualizza l’elenco di tutti gli hit sotto l’elemento dimensione &quot;Primo piano&quot;. Se è selezionata l’opzione &quot;Disattiva generazione rapporti e attribuzione legacy per hit in background&quot;, gli hit in background verranno visualizzati solo in [Suite di rapporti virtuali](../vrs/vrs-mobile-visit-processing.md).

## Elementi dimensionali

Gli elementi del Dimension includono `"Foreground"` e `"Background"`. Qualsiasi hit non inviato in background in un’app mobile appartiene al `"Foreground"` elemento dimensione. Qualsiasi hit inviato con l’app mobile in background appartiene al `"Background"` elemento dimensione.
