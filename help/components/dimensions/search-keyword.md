---
title: Cerca parola chiave
description: La parola chiave di ricerca utilizzata dal visitatore per raggiungere il sito.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---


# Cerca parola chiave

La dimensione &#39;Ricerca parola chiave&#39; riporta le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito.

>[!IMPORTANT] La maggior parte dei motori di ricerca non supera più la parola chiave di ricerca a causa dell’aumento delle pratiche di privacy. Hit in cui Adobe riconosce un motore di ricerca ma non dispone di gruppi di parole chiave sotto il valore della dimensione `"Keyword unavailable"`.

Per classificare come parola chiave di ricerca un referente deve soddisfare entrambi i seguenti criteri:

* Il dominio di riferimento è riconosciuto da Adobe come motore [di](search-engine.md)ricerca valido;
* Nell&#39;URL di provenienza esiste un parametro di stringa di query per parole chiave. Se la stringa di query per parole chiave esiste ma non contiene un valore, viene raggruppata sotto il valore della dimensione `"Keyword unavailable"`.

Per distinguere tra ricerca a pagamento e ricerca naturale, è necessario il rilevamento [della ricerca a](/help/admin/admin/paid-search-detection/paid-search-detection.md) pagamento. Sono disponibili più dimensioni per le parole chiave di ricerca:

* **Parola chiave** di ricerca: La parola chiave di ricerca utilizzata per raggiungere il sito, indipendentemente dal fatto che sia pagata o naturale.
* **Parola chiave di ricerca - paid**: La parola chiave di ricerca utilizzata per raggiungere il sito, che ha soddisfatto il rilevamento della ricerca a pagamento.
* **Parola chiave di ricerca - naturale**: La parola chiave di ricerca utilizzata per raggiungere il sito, che non corrisponde al rilevamento della ricerca a pagamento.

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento a più tabelle di ricerca interne ad Adobe. Ogni valore è basato sul [referente](referrer.md) dell’hit, che dipende dai filtri [URL](/help/admin/admin/internal-url-filter-admin.md)interni. Accertatevi che la dimensione del referente e i filtri URL interni siano configurati correttamente.

## Valori dimensione

I valori delle dimensioni includono le parole chiave di ricerca utilizzate per raggiungere il sito. Il valore della `"Unspecified"` dimensione è tutto traffico non di ricerca.
