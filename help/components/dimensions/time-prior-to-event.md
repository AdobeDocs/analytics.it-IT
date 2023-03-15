---
title: Tempo precedente all’evento
description: La quantità di tempo tra la metrica e il primo hit della visita.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 6%

---

# Tempo precedente all’evento

La dimensione &quot;Tempo precedente all’evento&quot; riporta il tempo trascorso tra il primo hit della visita e la metrica desiderata. Questa dimensione è utile per determinare il tempo necessario per raggiungere un evento di successo, ad esempio l’invio di un modulo o un acquisto.

## Popola questa dimensione con i dati

Questa dimensione funziona tecnicamente in modo predefinito per tutte le implementazioni, ma funziona meglio con eventi personalizzati e di acquisto. L’Adobe consiglia di implementare eventi personalizzati sul sito. Se implementi eventi personalizzati, non è necessaria alcuna implementazione aggiuntiva per questa dimensione.

## Elementi dimensionali

Gli elementi del Dimension includono contenitori temporizzati che vanno da `"Less than 1 minute"` a `"More than 15 hours"`. Ad esempio, se un visitatore ha impiegato 23 minuti dal suo primo hit per effettuare un acquisto, questo apparterrà al di sotto di `"10 to 30 minutes"` elemento dimensione. Non è possibile personalizzare i bucket per questa metrica.
