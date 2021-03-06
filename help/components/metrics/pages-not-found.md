---
title: Pagine non trovate (metriche)
description: Il numero di hit contenenti un errore.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 2%

---

# Pagine non trovate

*Questa pagina di aiuto descrive il funzionamento di &quot;Pagine non trovate&quot; come metrica. Consulta la sezione [Pagine non trovate](../dimensions/pages-not-found.md) per ulteriori informazioni.*

La metrica &quot;Pagine non trovate&quot; mostra il numero di hit in cui la pagina conteneva un errore. Questa metrica è utile quando desideri vedere quali pagine o URL contenevano messaggi di errore (ad esempio un 404), in modo da determinare la causa dell’errore e correggerlo.

## Calcolo di questa metrica

Questa metrica conta tutti gli hit in cui [`pageType`](/help/implement/vars/page-vars/pagetype.md) è uguale al valore di `"errorPage"`. È l’equivalente metrico del [Pagine non trovate](../dimensions/pages-not-found.md) dimensione.
