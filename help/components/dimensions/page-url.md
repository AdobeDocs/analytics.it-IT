---
title: URL della pagina
description: URL della pagina.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# URL della pagina

La dimensione &quot;URL della pagina&quot; elenca gli URL sul sito.

>[!IMPORTANT]
>
>Questa dimensione è disponibile solo nella Data Warehouse. Se desideri utilizzare una dimensione URL in altre soluzioni Analytics, prova a copiare il valore in un [eVar](evar.md) su ogni hit.

## Popola questa dimensione con i dati

Questa dimensione recupera i dati da [`g` e `-g` stringhe di query](/help/implement/validate/query-parameters.md) in [Chiamate di visualizzazione pagina (`t()`)](/help/implement/vars/functions/t-method.md). [Chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) elimina sempre questa dimensione, anche se `g` stringa di query esistente.

A volte gli URL sono più lunghi di 255 byte. AppMeasurement utilizza `g` parametro della stringa di query per i primi 255 byte dell’URL nelle richieste di immagini. Se un URL è più lungo di 255 byte, il resto dell&#39;URL viene memorizzato in `-g` parametro stringa query. In questa variabile sono incluse le stringhe di protocollo e di query nell’URL.

AppMeasurement raccoglie automaticamente questi dati in base all’URL della pagina. Puoi sovrascrivere il valore raccolto utilizzando [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabile.

## Compilare un eVar con l’URL

Adobe consiglia di impostare un eVar per la stringa concatenata `window.location.hostname + window.location.pathname`. Questa stringa in genere funziona meglio di `window.location.href` perché omette tag di protocollo, stringhe di query e tag di ancoraggio.

Se desideri che l’eVar corrisponda esattamente alla dimensione &quot;URL della pagina&quot; in Data Warehouse, puoi utilizzare [variabili dinamiche](/help/implement/vars/page-vars/dynamic-variables.md) e imposta l’eVar su `D=g` su ogni hit.

## Elementi dimensionali

Gli elementi di Dimension includono gli URL delle pagine del sito.
