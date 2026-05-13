---
title: Tempo precedente all’evento
description: La quantità di tempo tra la metrica e il primo hit della visita.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 159
ht-degree: 9%

---

# Tempo precedente all’evento

La &#39;dimensione Tempo precedente all&#39;evento&#39; [dimension](overview.md) indica il tempo trascorso tra il primo hit della visita e la metrica desiderata. Questa dimensione è utile per determinare il tempo necessario per raggiungere un evento di successo, ad esempio l’invio di un modulo o un acquisto.

## Popolare questa dimensione con i dati

Questa dimensione funziona tecnicamente in modo predefinito per tutte le implementazioni, ma funziona meglio con eventi personalizzati e di acquisto. Adobe consiglia di implementare eventi personalizzati sul sito. Se implementi eventi personalizzati, non è necessaria alcuna implementazione aggiuntiva per questa dimensione.

## Elementi dimensionali

Gli elementi Dimension includono bucket basati sul tempo che vanno da `"Less than 1 minute"` a `"More than 15 hours"`. Ad esempio, se un visitatore ha impiegato 23 minuti dal suo primo hit per effettuare un acquisto, questo apparterrà all&#39;elemento dimensione `"10 to 30 minutes"`. Non è possibile personalizzare i bucket per questa metrica.
