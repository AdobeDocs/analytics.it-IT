---
title: Tempo precedente all’evento
description: La quantità di tempo tra la metrica e il primo hit della visita.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 9%

---

# Tempo precedente all’evento

La &#39;dimensione Tempo precedente all&#39;evento&#39; [dimension](overview.md) indica il tempo trascorso tra il primo hit della visita e la metrica desiderata. Questa dimensione è utile per determinare il tempo necessario per raggiungere un evento di successo, ad esempio l’invio di un modulo o un acquisto.

## Popolare questa dimensione con i dati

Questa dimensione funziona tecnicamente in modo predefinito per tutte le implementazioni, ma funziona meglio con eventi personalizzati e di acquisto. Adobe consiglia di implementare eventi personalizzati sul sito. Se implementi eventi personalizzati, non è necessaria alcuna implementazione aggiuntiva per questa dimensione.

## Elementi dimensionali

Gli elementi Dimension includono bucket basati sul tempo che vanno da `"Less than 1 minute"` a `"More than 15 hours"`. Ad esempio, se un visitatore ha impiegato 23 minuti dal suo primo hit per effettuare un acquisto, questo apparterrà all&#39;elemento dimensione `"10 to 30 minutes"`. Non è possibile personalizzare i bucket per questa metrica.
