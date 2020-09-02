---
title: URL della pagina
description: URL della pagina.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 1%

---


# URL della pagina

La dimensione &quot;URL pagina&quot; elenca gli URL sul sito.

>[!IMPORTANT]
>
>Questa dimensione è disponibile solo nella Data Warehouse. Se desiderate utilizzare una dimensione URL in altre soluzioni Analytics, provate a copiare il valore in un eVar [](evar.md) su ogni hit.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalle [`g` stringhe `-g` di query e query nelle chiamate di visualizzazione](/help/implement/validate/query-parameters.md) Pagina ( [)`t()`](/help/implement/vars/functions/t-method.md). [Le chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) eliminano sempre questa dimensione, anche se la stringa di `g` query esiste.

A volte gli URL superano i 255 byte. AppMeasurement utilizza il parametro della stringa di `g` query per i primi 255 byte dell’URL nelle richieste di immagini. Se un URL supera i 255 byte, il resto dell&#39;URL viene memorizzato nel parametro della stringa di `-g` query. Le stringhe di protocollo e query nell’URL sono incluse in questa variabile.

AppMeasurement raccoglie automaticamente questi dati in base all&#39;URL della pagina. È possibile sostituire il valore raccolto utilizzando la [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabile.

## Compilare un eVar  con l’URL

 Adobe consiglia di impostare un eVar  sulla stringa concatenata `window.location.hostname + window.location.pathname`. Questa stringa in genere funziona meglio `window.location.href` perché omette il protocollo, le stringhe di query e i tag di ancoraggio.

Se desiderate che il eVar  corrisponda esattamente alla dimensione &quot;URL pagina&quot; nella Data Warehouse, potete utilizzare variabili [](/help/implement/vars/page-vars/dynamic-variables.md) dinamiche e impostare il eVar  su `D=g` ogni hit.

## Elementi Dimension

Gli elementi di Dimension includono gli URL delle pagine del sito.
