---
title: URL della pagina
description: URL della pagina.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 1%

---

# URL della pagina

La dimensione &quot;URL pagina&quot; elenca gli URL sul sito.

>[!IMPORTANT]
>
>Questa dimensione è disponibile solo nella Data Warehouse. Se desideri utilizzare una dimensione URL in altre soluzioni Analytics, prova a copiare il valore in un [eVar](evar.md) su ogni hit.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dal [`g` e `-g` stringhe di query](/help/implement/validate/query-parameters.md) in [Chiamate per la visualizzazione della pagina (`t()`)](/help/implement/vars/functions/t-method.md). [Chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) elimina sempre questa dimensione, anche se `g` stringa query esistente.

A volte gli URL superano i 255 byte. AppMeasurement utilizza il `g` parametro della stringa query per i primi 255 byte dell&#39;URL nelle richieste di immagini. Se un URL supera i 255 byte, il resto dell&#39;URL viene memorizzato nella variabile `-g` parametro della stringa query. Le stringhe di protocollo e query nell’URL sono incluse in questa variabile.

AppMeasurement raccoglie automaticamente questi dati in base all&#39;URL della pagina. Puoi sovrascrivere il valore raccolto utilizzando la variabile [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabile.

## Compilare un eVar con l’URL

Adobe consiglia di impostare un eVar per la stringa concatenata `window.location.hostname + window.location.pathname`. Questa stringa funziona generalmente meglio di `window.location.href` perché omette il protocollo, le stringhe di query e i tag di ancoraggio.

Se desideri che l’eVar corrisponda esattamente alla dimensione &quot;URL pagina&quot; nella Data Warehouse, puoi utilizzare [variabili dinamiche](/help/implement/vars/page-vars/dynamic-variables.md) e imposta l&#39;eVar su `D=g` su ogni hit.

## Elementi Dimension

Gli elementi di Dimension includono gli URL delle pagine del sito.
