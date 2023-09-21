---
title: Supporto dei cookie persistenti
description: Determina se il visitatore può supportare i cookie persistenti.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 3%

---

# Supporto dei cookie persistenti

&quot;Supporto dei cookie persistenti&quot; [dimensione](overview.md) mostra se l’hit ha utilizzato un identificatore visitatore proveniente da una sorgente persistente. La sorgente persistente più comune proviene da un cookie, ma può anche utilizzare intestazioni mobili e altre sorgenti.

## Popola questa dimensione con i dati

L’Adobe determina il valore di questa dimensione lato server in base all’origine dell’identificatore dell’hit. Non esiste un modo per impostarlo direttamente. Funziona automaticamente per tutte le implementazioni.

## Elementi dimensionali

* **`Enabled`**: l’identificatore del visitatore dell’hit proviene da un’origine che in genere persiste. Gli esempi più comuni includono `aid`, `fid`, o `mid` parametri della stringa di query, in quanto derivano i loro valori da un cookie.
* **`Disabled`**: l’identificatore visitatore dell’hit proviene da un’origine che Adobe non riconosce come persistente, ad esempio IP + stringa dell’agente utente. Questo elemento dimensione include anche gli ID visitatore personalizzati che utilizzano [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variabile.

## Differenza tra &quot;Supporto cookie&quot; e &quot;Supporto cookie persistente&quot;

* **Supporto per cookie**: AppMeasurement tenta di impostare un cookie generico. L’elemento dimensione si basa sulla verifica se il cookie è stato impostato correttamente.
* **Supporto dei cookie persistenti**: l’elemento dimensione si basa sul fatto che l’identificatore dell’hit provenga da un’origine persistente, ad esempio un cookie.
