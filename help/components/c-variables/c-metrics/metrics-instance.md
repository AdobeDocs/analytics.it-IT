---
description: Il numero di volte in cui un valore è stato impostato per una variabile.
keywords: istanze
seo-description: Il numero di volte in cui un valore è stato impostato per una variabile.
seo-title: Istanze
solution: Analytics
title: Istanze
topic: Metrics (Metriche)
uuid: fec 94 bdd-a 1 dc -4 cb 0-8983-ea 575 b 69589 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Istanze

Il numero di volte in cui un valore è stato impostato per una variabile.

Le istanze vengono conteggiate per tutti i tipi di hit, ma non nel caso in cui un valore venga registrato per una variabile su una hit successiva a causa della persistenza.

For example, if a user arrives on your site via [!DNL example.com], the first image request on your site contains the referrer of [!DNL example.com]. When this value is set, one Instance is attributed to [!DNL example.com] even though this referrer is recorded for all pages viewed during that visit.

Le istanze delle variabili di conversione nel data warehouse sono state aggiunte alla metà -2011, consentendo la gestione di un'istanza specifica della variabile di conversione come metrica. Queste metriche non sono disponibili per il reporting prima dell'introduzione.
