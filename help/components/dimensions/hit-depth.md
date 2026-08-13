---
title: Profondità di hit
description: Il numero di hit nella visita.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
TQID: https://experienceleague.adobe.com/dH1ItdXZTw9vcqvej3VOQDM-J9FFA38f4bq8HTJbKMo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 1ed4ab984231b7c72580c5ae505b1a16c0330c2f
workflow-type: tm+mt
source-wordcount: 314
ht-degree: 20%

---

# Profondità di hit

La &#39;Profondità di hit&#39; [dimensione](overview.md) indica quanto è distante una visita da un determinato hit. Questa dimensione è utile per comprendere fino a che punto in una visita i visitatori eseguono azioni sul sito. La profondità degli hit conta tutti i tipi di hit, incluse le visualizzazioni di pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e gli hit di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi Dimension includono la stringa `"Hit Depth"` seguita da un numero che rappresenta il numero di hit nella visita. L&#39;elemento dimensione di `"Hit Depth 1"` rappresenta il primo hit della visita, mentre l&#39;elemento dimensione `"Hit Depth 8"` rappresenta l&#39;ottavo hit della visita.

>[!NOTE]
>
>Adobe Analytics registra i timestamp con precisione di solo secondo livello. Per gli hit che condividono la stessa marca temporale in secondo luogo, Adobe non può garantire che l’ordine riportato nei rapporti sia lo stesso dell’ordine in cui si sono verificati gli hit. Se la precisione a livello di millisecondi è una priorità per la tua organizzazione, puoi utilizzare Customer Journey Analytics.

## Confronto con profondità di visita

La profondità degli hit conta tutti i tipi di hit, inclusi gli hit di visualizzazione pagina e di tracciamento dei collegamenti. Incrementi solo di profondità di visita per gli hit di visualizzazione pagina, _e_ l&#39;elemento dimensione [Pagina](page.md) non corrisponde al valore della pagina precedente. La profondità della visita è anche una dimensione basata sulla visita, il che significa che è lo stesso valore per tutti gli hit nella visita. La tabella seguente illustra un esempio di visita e come considera la profondità di hit + la profondità di visita:

| Sequenza di pagine | Profondità di hit | Conta per la profondità di visita? | Profondità della visita |
| --- | --- | --- | --- |
| Pagina Home | 1 | Sì | 4 |
| Pagina di prodotto | 2 | Sì | 4 |
| Pagina Home | 3 | Sì | 4 |
| Clic collegamento personalizzato | 4 | No (collegamento personalizzato) | 4 |
| Clic collegamento personalizzato | 5 | No (collegamento personalizzato) | 4 |
| Pagina di prodotto | 6 | Sì | 4 |
| Clic collegamento personalizzato | 7 | No (collegamento personalizzato) | 4 |
| Pagina di prodotto | 8 | No (come nella pagina precedente) | 4 |
