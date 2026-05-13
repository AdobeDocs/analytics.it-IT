---
title: Pagine non trovate (metriche)
description: Il numero di hit contenenti un errore.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
TQID: https://experienceleague.adobe.com/V5jVT8wh71qMrchQmmM6c4EMofHPUEI388TmAf7Zf6M
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 5%

---

# Pagine non trovate

*Questa pagina della Guida descrive il funzionamento di &quot;Pagine non trovate&quot; come metrica. Per ulteriori informazioni su come funziona come dimensione, vedere la pagina delle dimensioni [Pagine non trovate](../dimensions/pages-not-found.md).*

La [metrica](overview.md) &quot;Pagine non trovate&quot; mostra il numero di hit in cui una dimensione è stata impostata o persistita al momento in cui un visitatore ha riscontrato un errore. Questa metrica è utile quando desideri vedere quali pagine o URL contenevano messaggi di errore (ad esempio, un errore 404). Puoi quindi trasmettere queste informazioni al team di sviluppo Web, che può determinare la causa dell’errore e risolverlo.

## Come è calcolata questa metrica

Questa metrica conta tutti gli hit in cui la variabile [`pageType`](/help/implement/vars/page-vars/pagetype.md) è uguale al valore di `"errorPage"`. Equivale alla metrica della dimensione [Pagine non trovate](../dimensions/pages-not-found.md).
