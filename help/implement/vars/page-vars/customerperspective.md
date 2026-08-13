---
title: customerPerspective
description: Specifica se si è verificato un hit in un'app mobile mentre l'app era in primo piano o in background.
feature: Appmeasurement Implementation
role: Admin, Developer
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# customerPerspective

La variabile `customerPerspective` specifica se si è verificato un hit in un&#39;app mobile mentre l&#39;app era in primo piano o in background. Viene inviato alla raccolta dati di Adobe come parametro di query `cp` e popola la dimensione [Tipo di hit](/help/components/dimensions/hit-type.md).

## Valori validi

`customerPerspective` accetta i seguenti valori stringa:

* `foreground`: l&#39;hit si è verificato mentre l&#39;app era in uso.
* `background`: l&#39;hit si è verificato mentre l&#39;app era in esecuzione in background, ad esempio un aggiornamento della posizione o un hit attivato da una notifica push.

## Impostazione di questa variabile

Adobe Mobile SDK (versione 4.13.6 e successive) imposta `customerPerspective` automaticamente; in genere non viene impostato manualmente. Gli hit inviati da un browser tramite AppMeasurement segnalano sempre come `foreground`. Se la variabile è assente da un hit, tale hit viene trattato come un hit in primo piano.

## Impatto sul reporting

La distinzione in primo piano/sfondo influisce sul modo in cui vengono elaborate le visite:

* Le visite vengono conteggiate solo se contengono almeno un hit in primo piano.
* Gli hit in background possono ancora essere attribuiti a eventi di conversione e possono essere analizzati tramite [sessioni in base al contesto](/help/components/vrs/vrs-mobile-visit-processing.md) nelle suite di rapporti virtuali. Questo comportamento è utile quando si misura l’efficacia delle notifiche push.
