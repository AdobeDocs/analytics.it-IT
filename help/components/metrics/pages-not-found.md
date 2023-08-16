---
title: Pagine non trovate (metriche)
description: Il numero di hit contenenti un errore.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: ed4538efa9a28d40ab18fecd3bd87545808d9ac5
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 6%

---

# Pagine non trovate

*Questa pagina della guida descrive come funziona &quot;Pagine non trovate&quot; come metrica. Consulta la [Pagine non trovate](../dimensions/pages-not-found.md) per ulteriori informazioni.*

La metrica &quot;Pagine non trovate&quot; mostra il numero di hit in cui una dimensione è stata impostata o persistita al momento in cui un visitatore ha riscontrato un errore. Questa metrica è utile quando desideri vedere quali pagine o URL contenevano messaggi di errore (ad esempio, un errore 404). Puoi quindi trasmettere queste informazioni al team di sviluppo Web, che può determinare la causa dell’errore e risolverlo.

## Come è calcolata questa metrica

Questa metrica conta tutti gli hit in cui [`pageType`](/help/implement/vars/page-vars/pagetype.md) variabile è uguale al valore di `"errorPage"`. È l’equivalente metrico del valore [Pagine non trovate](../dimensions/pages-not-found.md) dimensione.
