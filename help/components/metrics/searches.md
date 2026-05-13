---
title: Ricerche
description: Il numero di volte in cui un hit corrisponde ai criteri di ricerca esterni.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
TQID: https://experienceleague.adobe.com/bcK-h9tkOKRHFoZ5EbX05ppNtV5S8Kok8dhMJZxf-ao
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 118
ht-degree: 5%

---

# Ricerche

La [metrica](overview.md) di &#39;Ricerche&#39; mostra il numero di hit che corrispondono al rilevamento di ricerche esterne di Adobe. Questa metrica è utile quando desideri esaminare gli elementi dimensionali non di ricerca e vedere come hanno contribuito al traffico del motore di ricerca.

## Come è calcolata questa metrica

Questa metrica conta il numero di hit che corrispondono al rilevamento di ricerche esterne di Adobe. Deve corrispondere a entrambi i seguenti elementi:

* Il valore referrer dell’hit è un dominio di ricerca riconosciuto da Adobe
* L’URL di riferimento dell’hit contiene un parametro di stringa di query per parola chiave. A causa delle moderne procedure sulla privacy, questo valore della stringa di query è solitamente vuoto. Adobe riconosce le stringhe di query vuote per parole chiave come parte del rilevamento di ricerche.
