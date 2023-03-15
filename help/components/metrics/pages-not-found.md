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

*Questa pagina della guida descrive come funziona &quot;Pagine non trovate&quot; come metrica. Consulta la [Pagine non trovate](../dimensions/pages-not-found.md) per ulteriori informazioni.*

La metrica &quot;Pagine non trovate&quot; mostra il numero di hit in cui la pagina conteneva un errore. Questa metrica è utile quando desideri visualizzare quali pagine o URL contenevano messaggi di errore (ad esempio, un errore 404), in modo da poter determinare la causa dell’errore e correggerlo.

## Modalità di calcolo di questa metrica

Questa metrica conta tutti gli hit in cui [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabile è uguale al valore di `"errorPage"`. È l’equivalente metrico del valore [Pagine non trovate](../dimensions/pages-not-found.md) dimensione.
