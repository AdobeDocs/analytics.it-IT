---
title: Ordini
description: Il numero di acquisti effettuati.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
TQID: https://experienceleague.adobe.com/jRd-oUTfcJXACj-mkEyzRm8k-rxcVCxe7U3lROIy7DQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 90
ht-degree: 7%

---

# Ordini

La [metrica](overview.md) di &#39;Ordini&#39; mostra il numero totale di eventi di acquisto effettuati sul sito. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito a un ordine. Ad esempio, puoi visualizzare le campagne principali (utilizzando la dimensione [Codice di tracciamento](../dimensions/tracking-code.md)) o i termini di ricerca interni principali (utilizzando un [eVar](../dimensions/evar.md)) che hanno contribuito agli acquisti.

## Come è calcolata questa metrica

Questa metrica conta il numero di hit in cui `purchase` esiste nella variabile [`events`](/help/implement/vars/page-vars/events/events-overview.md).
