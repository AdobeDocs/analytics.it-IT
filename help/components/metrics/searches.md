---
title: Ricerche
description: Il numero di volte in cui un hit corrisponde a criteri di ricerca esterni.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 1%

---

# Ricerche

La metrica &quot;Ricerche&quot; mostra il numero di hit che corrispondono al rilevamento di ricerche esterne di Adobe. Questa metrica è utile quando desideri esaminare elementi dimensionali non di ricerca e vedere come hanno contribuito al traffico del motore di ricerca.

## Calcolo di questa metrica

Questa metrica conta il numero di hit che corrispondono al rilevamento di ricerca esterno di Adobe. Deve corrispondere a entrambi i seguenti elementi:

* Il valore referente dell&#39;hit è un dominio di ricerca riconosciuto da Adobe
* L&#39;URL di riferimento dell&#39;hit contiene un parametro della stringa di query per parole chiave. A causa delle pratiche di privacy moderne, questo valore della stringa di query è comunemente vuoto. Adobe riconosce le stringhe di query per parole chiave vuote come parte del rilevamento di ricerca.
