---
title: Motore di ricerca
description: Il motore di ricerca utilizzato dal visitatore per raggiungere il sito.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---


# Motore di ricerca

La dimensione &quot;Motore di ricerca&quot; indica i motori di ricerca utilizzati dai visitatori per raggiungere il sito. Per classificare come motore di ricerca un referente deve soddisfare entrambi i requisiti seguenti:

* Il dominio di riferimento è riconosciuto da Adobe come motore di ricerca valido;
* Nell&#39;URL di provenienza esiste un parametro di stringa di query per parole chiave. Il parametro della stringa di query può essere vuoto (come accade con diversi motori di ricerca a causa delle pratiche sulla privacy).

Per distinguere tra ricerca a pagamento e ricerca naturale, è necessario il rilevamento [della ricerca a](/help/admin/admin/paid-search-detection/paid-search-detection.md) pagamento. Sono disponibili più dimensioni per i motori di ricerca:

* **Motore** di ricerca: Il motore di ricerca utilizzato per raggiungere il sito, indipendentemente dal fatto che sia pagato o naturale.
* **Motore di ricerca - a pagamento**: Il motore di ricerca utilizzato per raggiungere il sito, che corrispondeva al rilevamento a pagamento.
* **Motore di ricerca - naturale**: Il motore di ricerca utilizzato per raggiungere il sito, che non corrisponde al rilevamento di ricerca a pagamento.

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento a più tabelle di ricerca interne ad Adobe. Ogni valore è basato sul [referente](referrer.md) dell’hit, che dipende dai filtri [URL](/help/admin/admin/internal-url-filter-admin.md)interni. Accertatevi che la dimensione del referente e i filtri URL interni siano configurati correttamente.

## Elementi dimensione

Gli elementi dimensionali includono i motori di ricerca utilizzati per raggiungere il sito. I valori di esempio includono `"Google"`, `"Microsoft Bing"`e `"DuckDuckGo"`. L’elemento `"Unspecified"` dimensione è tutto traffico non di ricerca.
