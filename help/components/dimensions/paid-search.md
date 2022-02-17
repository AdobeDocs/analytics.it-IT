---
title: Ricerca a pagamento
description: Consente di distinguere le metriche dalla ricerca a pagamento e naturale.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 2%

---

# Ricerca a pagamento

La dimensione &quot;Ricerca a pagamento&quot; consente di esaminare qualsiasi metrica e di confrontarla tra ricerca a pagamento e ricerca naturale. Tutti gli altri hit esterni ai motori di ricerca vengono omessi. Questa dimensione è utile per comprendere in che modo le attività di ricerca a pagamento si confrontano con la ricerca organica.

## Popolare questa dimensione con i dati

L&#39;unico requisito per il corretto funzionamento di questa dimensione è quello di [Rilevamento di ricerca a pagamento](/help/admin/admin/paid-search-detection/paid-search-detection.md) configurato correttamente nelle impostazioni della suite di rapporti. Se il rilevamento della ricerca a pagamento è configurato correttamente e una suite di rapporti dispone di dati, questa dimensione funziona sempre.

## Elementi Dimension

Gli elementi di Dimension includono due valori statici: `"Natural"` e `"Paid"`. Se una visita soddisfa i criteri per un motore di ricerca e corrisponde anche al rilevamento di ricerca a pagamento, appartiene alla `"Paid"` elemento dimensione. Se una visita soddisfa i criteri di un motore di ricerca e lo fa *not* rilevamento di ricerca a pagamento abbinato, appartiene al `"Natural"` elemento dimensione.
