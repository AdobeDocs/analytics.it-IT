---
title: Motore di ricerca
description: Il motore di ricerca utilizzato dal visitatore per raggiungere il sito.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 6%

---

# Motore di ricerca

La [dimensione](overview.md) del &#39;motore di ricerca&#39; segnala i motori di ricerca utilizzati dai visitatori per raggiungere il sito. Un referente deve soddisfare entrambe le seguenti condizioni per essere classificato come motore di ricerca:

* Il dominio di riferimento è riconosciuto da Adobe come un motore di ricerca valido;
* Nell&#39;URL di riferimento esiste un parametro di stringa di query per parola chiave. Il parametro della stringa di query può essere vuoto (come nel caso di diversi motori di ricerca a causa di pratiche di privacy).

Per distinguere la ricerca a pagamento da quella naturale, è necessario [Rilevamento ricerca a pagamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md). Sono disponibili più dimensioni per i motori di ricerca:

* **Motore di ricerca**: il motore di ricerca utilizzato per raggiungere il sito, indipendentemente dal fatto che sia a pagamento o naturale.
* **Motore di ricerca - a pagamento**: motore di ricerca utilizzato per raggiungere il sito, che corrisponde al rilevamento di ricerche a pagamento.
* **Motore di ricerca - naturale**: motore di ricerca utilizzato per raggiungere il sito, che non corrisponde al rilevamento di ricerche a pagamento.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a più tabelle di ricerca interne a Adobe. Ogni valore è basato sul [referrer](referrer.md) dell&#39;hit, che dipende da [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). Assicurati che la dimensione del referente e i filtri URL interni siano configurati correttamente.

## Elementi dimensionali

Gli elementi di Dimension includono i motori di ricerca utilizzati per raggiungere il sito. Valori di esempio includono `"Google"`, `"Microsoft Bing"`, e `"DuckDuckGo"`. L&#39;elemento dimensione `"Unspecified"` è tutto traffico non di ricerca.
