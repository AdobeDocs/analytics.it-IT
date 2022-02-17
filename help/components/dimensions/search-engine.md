---
title: Motore di ricerca
description: Il motore di ricerca utilizzato dal visitatore per raggiungere il sito.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---

# Motore di ricerca

La dimensione &quot;Motore di ricerca&quot; indica i motori di ricerca utilizzati dai visitatori per raggiungere il sito. Per classificare come motore di ricerca un referente deve soddisfare entrambi i requisiti seguenti:

* Il dominio di riferimento è riconosciuto dall’Adobe come motore di ricerca valido;
* Nell’URL di riferimento esiste un parametro della stringa di query per parole chiave. Il parametro della stringa di query può essere vuoto (come nel caso di diversi motori di ricerca a causa di pratiche di privacy).

Se si desidera distinguere la ricerca a pagamento e la ricerca naturale, [Rilevamento di ricerca a pagamento](/help/admin/admin/paid-search-detection/paid-search-detection.md) è obbligatorio. Sono disponibili più dimensioni per i motori di ricerca:

* **Motore di ricerca**: Il motore di ricerca utilizzato per raggiungere il tuo sito, indipendentemente dal fatto che sia pagato o naturale.
* **Motore di ricerca - paid**: Il motore di ricerca utilizzato per raggiungere il tuo sito, che corrisponde al rilevamento di ricerche a pagamento.
* **Motore di ricerca - naturale**: Il motore di ricerca utilizzato per raggiungere il tuo sito, che non corrisponde al rilevamento di ricerca a pagamento.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a più tabelle di ricerca interne all’Adobe. Ogni valore è basato sul [referrer](referrer.md) dell’hit, che dipende da [Filtri URL interni](/help/admin/admin/internal-url-filter-admin.md). Assicurati che la dimensione del referente e i filtri URL interni siano configurati correttamente.

## Elementi Dimension

Gli elementi di Dimension includono i motori di ricerca utilizzati per raggiungere il tuo sito. I valori di esempio includono `"Google"`, `"Microsoft Bing"`e `"DuckDuckGo"`. La `"Unspecified"` l’elemento dimensione è tutto traffico non di ricerca.
