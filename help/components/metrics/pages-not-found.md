---
title: Pagine non trovate (metriche)
description: Il numero di hit contenenti un errore.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 5%

---

# Pagine non trovate

*Questa pagina della Guida descrive il funzionamento di &quot;Pagine non trovate&quot; come metrica. Per ulteriori informazioni su come funziona come dimensione, vedere la pagina delle dimensioni [Pagine non trovate](../dimensions/pages-not-found.md).*

La [metrica](overview.md) &quot;Pagine non trovate&quot; mostra il numero di hit in cui una dimensione è stata impostata o persistita al momento in cui un visitatore ha riscontrato un errore. Questa metrica è utile quando desideri vedere quali pagine o URL contenevano messaggi di errore (ad esempio, un errore 404). Puoi quindi trasmettere queste informazioni al team di sviluppo Web, che può determinare la causa dell’errore e risolverlo.

## Come è calcolata questa metrica

Questa metrica conta tutti gli hit in cui la variabile [`pageType`](/help/implement/vars/page-vars/pagetype.md) è uguale al valore di `"errorPage"`. Equivale alla metrica della dimensione [Pagine non trovate](../dimensions/pages-not-found.md).
