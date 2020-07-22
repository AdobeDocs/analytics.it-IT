---
title: Ora precedente all’evento
description: Il tempo tra la metrica e il primo hit della visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# Ora precedente all’evento

La dimensione &quot;Tempo precedente all’evento&quot; indica il tempo trascorso tra il primo hit della visita e la metrica desiderata. Questa dimensione è utile per determinare il tempo necessario per raggiungere un evento di successo, ad esempio l&#39;invio di un modulo o l&#39;acquisto.

## Compilare questa dimensione con i dati

Questa dimensione tecnicamente funziona automaticamente per tutte le implementazioni, ma funziona meglio con gli eventi personalizzati e di acquisto. Adobe consiglia di implementare eventi personalizzati sul sito. Se implementate eventi personalizzati, non è richiesta alcuna implementazione aggiuntiva per questa dimensione.

## Elementi dimensione

Gli elementi dimensione includono intervalli temporali che vanno da `"Less than 1 minute"` a `"More than 15 hours"`. Ad esempio, se un visitatore impiegava 23 minuti dal primo hit a un acquisto, apparirebbe sotto l’elemento `"10 to 30 minutes"` dimensione.
