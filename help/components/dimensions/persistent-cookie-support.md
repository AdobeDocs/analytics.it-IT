---
title: Supporto dei cookie persistenti
description: Determina se il visitatore può supportare cookie persistenti.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%

---

# Supporto dei cookie persistenti

La dimensione &#39;Supporto cookie persistente&#39; mostra se l&#39;hit ha utilizzato un identificatore visitatore proveniente da una sorgente persistente. L&#39;origine persistente più comune proviene da un cookie, ma può anche utilizzare intestazioni mobili e altre sorgenti.

## Popolare questa dimensione con i dati

L&#39;Adobe determina il valore di questa dimensione lato server in base all&#39;origine dell&#39;identificatore dell&#39;hit. Non esiste un modo per impostarlo direttamente. Funziona come standard per tutte le implementazioni.

## Elementi Dimension

* **`Enabled`**: L&#39;identificatore visitatore dell&#39;hit proviene da un&#39;origine che in genere persiste. Gli esempi più comuni includono `aid`, `fid`oppure `mid` i parametri della stringa di query, in quanto derivano i loro valori da un cookie.
* **`Disabled`**: L&#39;identificatore visitatore dell&#39;hit proviene da un&#39;origine che Adobe non riconosce come persistente, ad esempio IP + stringa agente utente. Questo elemento della dimensione include anche ID visitatore personalizzati che utilizzano [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variabile.

## Differenza tra &#39;Supporto cookie&#39; e &#39;Supporto cookie persistente&#39;

* **Supporto per cookie**: AppMeasurement tenta di impostare un cookie generico. L’elemento dimensionale si basa su se il cookie è stato impostato correttamente.
* **Supporto dei cookie persistenti**: L&#39;elemento dimensionale si basa su se l&#39;identificatore dell&#39;hit proviene da un&#39;origine persistente, ad esempio un cookie.
