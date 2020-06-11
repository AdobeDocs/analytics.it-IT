---
title: URL della pagina
description: URL della pagina.
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 2%

---


# URL della pagina

La dimensione &quot;URL pagina&quot; elenca gli URL sul sito.

>[!IMPORTANT] Questa dimensione è disponibile solo in Data Warehouse. Se desiderate utilizzare una dimensione URL in altre soluzioni Analytics, utilizzate una [eVar](evar.md).

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`g` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabile.

## Compilare un&#39;eVar con l&#39;URL

Adobe consiglia di impostare un eVar sulla stringa concatenata `window.location.hostname + window.location.pathname`. Questa stringa in genere funziona meglio `window.location.href` perché omette il protocollo, le stringhe di query e i tag di ancoraggio.

Se si desidera che l&#39;eVar corrisponda esattamente alla dimensione &quot;URL pagina&quot; in Data Warehouse, è possibile utilizzare variabili [](/help/implement/vars/page-vars/dynamic-variables.md) dinamiche e impostare l&#39;eVar su `D=g` ogni hit. Questo metodo non funziona per gli hit di collegamento personalizzati, in quanto l’URL della pagina viene rimosso per tutte [`tl()`](/help/implement/vars/functions/tl-method.md) le chiamate.

## Valori dimensione

I valori delle dimensioni includono gli URL delle pagine del sito.
