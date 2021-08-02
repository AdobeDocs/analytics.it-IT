---
title: Tempo precedente all’evento
description: Il tempo tra la metrica e il primo hit della visita.
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
source-git-commit: 2c363dce63768101356a6f43ea1e45ae8dd7b139
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 5%

---

# Tempo precedente all’evento

La dimensione &quot;Tempo precedente all’evento&quot; indica il tempo trascorso tra il primo hit della visita e la metrica desiderata. Questa dimensione è utile per determinare il tempo necessario per raggiungere un evento di successo, ad esempio un invio di un modulo o un acquisto.

## Popolare questa dimensione con i dati

Questa dimensione funziona tecnicamente come standard per tutte le implementazioni, ma funziona al meglio con eventi personalizzati e di acquisto. Adobe consiglia di implementare eventi personalizzati sul sito. Se implementi eventi personalizzati, non è necessaria alcuna implementazione aggiuntiva per questa dimensione.

## Elementi Dimension

Gli elementi di Dimension includono bucket basati sul tempo che vanno da `"Less than 1 minute"` a `"More than 15 hours"`. Ad esempio, se ci sono voluti 23 minuti dal primo hit per un acquisto, il visitatore deve appartenere all’elemento della dimensione `"10 to 30 minutes"` . Impossibile personalizzare i bucket per questa metrica.
