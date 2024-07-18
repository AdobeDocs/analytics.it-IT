---
title: URL della pagina
description: URL della pagina.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 4%

---

# URL della pagina

La &#39;dimensione URL pagina&#39; [dimensione](overview.md) elenca gli URL sul sito.

>[!IMPORTANT]
>
>Questa dimensione è disponibile solo nella Data Warehouse. Se desideri utilizzare una dimensione URL in altre soluzioni Analytics, prova a copiare il valore in un [eVar](evar.md) per ogni hit.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalle stringhe di query [`g` e `-g`](/help/implement/validate/query-parameters.md) in [chiamate di visualizzazione pagina (`t()`)](/help/implement/vars/functions/t-method.md). [Le chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) eliminano sempre questa dimensione, anche se la stringa di query `g` esiste.

A volte gli URL sono più lunghi di 255 byte. In AppMeasurement viene utilizzato il parametro della stringa di query `g` per i primi 255 byte dell&#39;URL nelle richieste di immagini. Se un URL è più lungo di 255 byte, il resto dell&#39;URL viene memorizzato nel parametro della stringa di query `-g`. In questa variabile sono incluse le stringhe di protocollo e di query nell’URL.

AppMeasurement raccoglie automaticamente questi dati in base all’URL della pagina. È possibile sovrascrivere il valore raccolto utilizzando la variabile [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Compilare un eVar con l’URL

L&#39;Adobe consiglia di impostare un eVar per la stringa concatenata `window.location.hostname + window.location.pathname`. Questa stringa funziona in genere meglio di `window.location.href` perché omette i tag di protocollo, le stringhe di query e di ancoraggio.

Se desideri che l&#39;eVar corrisponda esattamente alla dimensione &quot;URL pagina&quot; in Data Warehouse, puoi utilizzare [variabili dinamiche](/help/implement/vars/page-vars/dynamic-variables.md) e impostare l&#39;eVar su `D=g` per ogni hit.

## Elementi dimensionali

Gli elementi di Dimension includono gli URL delle pagine del sito.
