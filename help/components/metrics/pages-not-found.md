---
title: Pagine non trovate
description: Numero di hit contenenti un errore.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%

---


# Pagine non trovate

*Questa pagina della guida descrive il funzionamento di &quot;Pagine non trovate&quot; come metrica. Per ulteriori informazioni, vedere la dimensione[Pagine non trovata](../dimensions/pages-not-found.md).*

La metrica &quot;Pagine non trovate&quot; mostra il numero di hit in cui la pagina conteneva un errore. Questa metrica è utile per vedere quali pagine o URL contenevano messaggi di errore (come 404), in modo da determinare la causa dell’errore e correggerlo.

## Modalità di calcolo di questa metrica

Questa metrica conta tutti gli hit in cui la [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabile è uguale al valore di `"errorPage"`. Equivale alla metrica della dimensione [Pagine non trovata](../dimensions/pages-not-found.md) .