---
title: Ricerche
description: Il numero di volte in cui un hit corrisponde ai criteri di ricerca esterni.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 1%

---

# Ricerche

La metrica &quot;Ricerche&quot; mostra il numero di hit che corrispondono al rilevamento di ricerche esterne di Adobe. Questa metrica è utile quando desideri esaminare gli elementi dimensionali non di ricerca e vedere come hanno contribuito al traffico del motore di ricerca.

## Modalità di calcolo di questa metrica

Questa metrica conta il numero di hit che corrispondono al rilevamento di ricerche esterne di Adobe. Deve corrispondere a entrambi i seguenti elementi:

* Il valore del referente dell’hit è un dominio di ricerca riconosciuto da Adobe
* L’URL di riferimento dell’hit contiene un parametro di stringa di query per parola chiave. A causa delle moderne procedure sulla privacy, questo valore della stringa di query è solitamente vuoto. Adobe riconosce le stringhe di query vuote per parole chiave come parte del rilevamento di ricerche.
