---
title: Parola chiave di ricerca
description: La parola chiave di ricerca utilizzata dal visitatore per raggiungere il sito.
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 2%

---

# Parola chiave di ricerca

La dimensione &quot;Parola chiave di ricerca&quot; indica le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito.

>[!IMPORTANT]
>
>La maggior parte dei motori di ricerca non passa più la parola chiave di ricerca a causa dell’aumento delle pratiche di privacy. Hit in cui Adobe riconosce un motore di ricerca ma manca un gruppo di parole chiave sotto l’elemento dimensione `"Keyword unavailable"`.

Per classificare come parola chiave di ricerca, un referente deve soddisfare entrambi i valori seguenti:

* Il dominio di riferimento è riconosciuto dall&#39;Adobe come valido [Motore di ricerca](search-engine.md);
* Nell’URL di riferimento esiste un parametro della stringa di query per parole chiave. Se la stringa di query per parole chiave esiste ma non contiene un valore, viene raggruppata sotto l’elemento dimensione `"Keyword unavailable"`.

Se si desidera distinguere la ricerca a pagamento e la ricerca naturale, [Rilevamento di ricerca a pagamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) è obbligatorio. Sono disponibili più dimensioni per le parole chiave di ricerca:

* **Parola chiave di ricerca**: Parola chiave di ricerca utilizzata per raggiungere il sito, indipendentemente dal fatto che sia pagato o naturale.
* **Parola chiave di ricerca - paid**: La parola chiave di ricerca utilizzata per raggiungere il sito, che corrisponde al rilevamento di ricerche a pagamento.
* **Parola chiave di ricerca - naturale**: Parola chiave di ricerca utilizzata per raggiungere il tuo sito, che non corrisponde al rilevamento di ricerche a pagamento.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a più tabelle di ricerca interne all’Adobe. Ogni valore è basato sul [referrer](referrer.md) dell’hit, che dipende da [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). Assicurati che la dimensione del referente e i filtri URL interni siano configurati correttamente.

## Elementi dimensionali

Gli elementi di Dimension includono parole chiave di ricerca utilizzate per raggiungere il sito. La `"Unspecified"` l’elemento dimensione è tutto traffico non di ricerca.
