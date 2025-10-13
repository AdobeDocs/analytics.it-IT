---
title: Ricerche
description: Il numero di volte in cui un hit corrisponde ai criteri di ricerca esterni.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 5%

---

# Ricerche

La [metrica](overview.md) di &#39;Ricerche&#39; mostra il numero di hit che corrispondono al rilevamento di ricerche esterne di Adobe. Questa metrica è utile quando desideri esaminare gli elementi dimensionali non di ricerca e vedere come hanno contribuito al traffico del motore di ricerca.

## Come è calcolata questa metrica

Questa metrica conta il numero di hit che corrispondono al rilevamento di ricerche esterne di Adobe. Deve corrispondere a entrambi i seguenti elementi:

* Il valore referrer dell’hit è un dominio di ricerca riconosciuto da Adobe
* L’URL di riferimento dell’hit contiene un parametro di stringa di query per parola chiave. A causa delle moderne procedure sulla privacy, questo valore della stringa di query è solitamente vuoto. Adobe riconosce le stringhe di query vuote per parole chiave come parte del rilevamento di ricerche.
