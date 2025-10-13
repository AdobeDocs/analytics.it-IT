---
title: Tipo di hit
description: Determina se l’hit è stato un hit in primo piano o in background.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 6%

---

# Tipo di hit

La dimensione [tipo di hit](overview.md) determina se un&#39;app mobile si trovava in primo piano o in background al momento dell&#39;invio dell&#39;hit ai server di raccolta dati di Adobe. Questa dimensione è pertinente solo per le suite di rapporti che contengono dati per le applicazioni mobili. I dati del browser raccolti tramite AppMeasurement segnalano sempre l’hit come &quot;Primo piano&quot;.

## Popolare questa dimensione con i dati

Questa dimensione funziona come previsto per tutte le implementazioni di SDK per dispositivi mobili nella versione 4.13.6 o successiva. Se non utilizzi il SDK mobile, tutti gli hit sono elencati nell’elemento dimensione &quot;Primo piano&quot;. Se è selezionata l&#39;opzione &quot;Disabilita generazione rapporti e attribuzione legacy per hit in background&quot;, gli hit in background verranno visualizzati solo nelle [suite di rapporti virtuali](../vrs/vrs-mobile-visit-processing.md).

## Elementi dimensionali

Gli elementi Dimension includono `"Foreground"` e `"Background"`. Qualsiasi hit non inviato in background in un&#39;app mobile appartiene all&#39;elemento dimensione `"Foreground"`. Qualsiasi hit inviato con l&#39;applicazione mobile in background appartiene all&#39;elemento dimensione `"Background"`.
