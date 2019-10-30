---
description: Il numero di volte in cui un valore è stato impostato per una variabile.
keywords: instance
seo-description: Il numero di volte in cui un valore è stato impostato per una variabile.
seo-title: Istanze
solution: Analytics
title: Istanze
topic: Metriche
uuid: fec94bdd-a1dc-4cb0-8983-ea575b69589f
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Istanze

Il numero di volte in cui un valore è stato impostato per una variabile.

Le istanze vengono conteggiate per tutti i tipi di hit, ma non nel caso in cui un valore venga registrato per una variabile su una hit successiva a causa della persistenza.

Ad esempio, se un utente arriva sul sito tramite [!DNL example.com], la prima richiesta di immagine sul sito contiene il referente di [!DNL example.com]. Quando questo valore viene impostato, viene attribuita un'istanza a [!DNL example.com] anche se il referente viene registrato per tutte le pagine visualizzate durante la visita.

Le istanze per le variabili di conversione in data warehouse sono state aggiunte a metà del 2011, consentendo alle richieste data warehouse di trattare una specifica istanza di variabile di conversione come una metrica. Queste metriche non sono disponibili per il reporting prima del momento in cui sono state introdotte.
