---
title: Supporto dei cookie persistenti
description: Determina se il visitatore può supportare i cookie persistenti.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 6%

---

# Supporto dei cookie persistenti

La dimensione [dimension](overview.md) del supporto dei cookie persistenti mostra se l&#39;hit ha utilizzato un identificatore visitatore proveniente da un&#39;origine persistente. La sorgente persistente più comune proviene da un cookie, ma può anche utilizzare intestazioni mobili e altre sorgenti.

## Popolare questa dimensione con i dati

Adobe determina il valore di questa dimensione lato server in base all’origine dell’identificatore dell’hit. Non esiste un modo per impostarlo direttamente. Funziona automaticamente per tutte le implementazioni.

## Elementi dimensionali

* **`Enabled`**: l&#39;identificatore del visitatore dell&#39;hit proviene da un&#39;origine che in genere persiste. Gli esempi più comuni includono `aid`, `fid` o `mid` parametri della stringa di query, in quanto derivano i loro valori da un cookie.
* **`Disabled`**: l&#39;identificatore visitatore dell&#39;hit proviene da un&#39;origine che Adobe non riconosce come persistente, ad esempio IP + stringa dell&#39;agente utente. Questo elemento dimensione include anche gli ID visitatore personalizzati che utilizzano la variabile [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

## Differenza tra &quot;Supporto cookie&quot; e &quot;Supporto cookie persistente&quot;

* **Supporto cookie**: AppMeasurement tenta di impostare un cookie generico. L’elemento dimensione si basa sulla verifica se il cookie è stato impostato correttamente.
* **Supporto cookie persistenti**: l&#39;elemento dimensione si basa sul fatto che l&#39;identificatore dell&#39;hit provenga da un&#39;origine persistente, ad esempio un cookie.
