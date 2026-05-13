---
title: Tipo di hit
description: Determina se l’hit è stato un hit in primo piano o in background.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 6%

---

# Tipo di hit

La dimensione [tipo di hit](overview.md) determina se un&#39;app mobile si trovava in primo piano o in background al momento dell&#39;invio dell&#39;hit ai server di raccolta dati di Adobe. Questa dimensione è pertinente solo per le suite di rapporti che contengono dati per le applicazioni mobili. I dati del browser raccolti tramite AppMeasurement segnalano sempre l’hit come &quot;Primo piano&quot;.

## Popolare questa dimensione con i dati

Questa dimensione funziona come previsto per tutte le implementazioni di SDK per dispositivi mobili nella versione 4.13.6 o successiva. Se non utilizzi il SDK mobile, tutti gli hit sono elencati nell’elemento dimensione &quot;Primo piano&quot;. Se è selezionata l&#39;opzione &quot;Disabilita generazione rapporti e attribuzione legacy per hit in background&quot;, gli hit in background verranno visualizzati solo nelle [suite di rapporti virtuali](../vrs/vrs-mobile-visit-processing.md).

## Elementi dimensionali

Gli elementi Dimension includono `"Foreground"` e `"Background"`. Qualsiasi hit non inviato in background in un&#39;app mobile appartiene all&#39;elemento dimensione `"Foreground"`. Qualsiasi hit inviato con l&#39;applicazione mobile in background appartiene all&#39;elemento dimensione `"Background"`.
