---
title: Ricerca a pagamento
description: Consente di distinguere le metriche dalla ricerca a pagamento e naturale.
translation-type: tm+mt
source-git-commit: d71edc74644907b47bfb6492e7a6c47c06d5984f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Ricerca a pagamento

La dimensione &quot;Ricerca a pagamento&quot; consente di esaminare qualsiasi metrica e di confrontarla tra ricerca a pagamento e ricerca naturale. Tutti gli altri hit esterni ai motori di ricerca vengono omessi. Questa dimensione è utile per comprendere in che modo i vostri sforzi di ricerca a pagamento si confrontano con la ricerca organica.

## Compilare questa dimensione con i dati

L&#39;unico requisito per il corretto funzionamento di questa dimensione è che il rilevamento [della ricerca a](/help/admin/admin/paid-search-detection/paid-search-detection.md) pagamento sia configurato correttamente nelle impostazioni della suite di rapporti. Se il rilevamento della ricerca a pagamento è configurato correttamente e una suite di rapporti dispone di dati, questa dimensione funziona sempre.

## Valori dimensione

I valori delle dimensioni includono due valori statici: `"Natural"` e `"Paid"`. Se una visita soddisfa i criteri per un motore di ricerca e corrisponde anche al rilevamento a pagamento, appartiene al valore della `"Paid"` dimensione. Se una visita soddisfa i criteri per un motore di ricerca e *non* corrisponde al rilevamento della ricerca a pagamento, appartiene al valore della `"Natural"` dimensione.
