---
description: La variabile di conversione dell'intuizione personalizzata (eVar) viene inserita nel codice Adobe su alcune pagine Web del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei report di marketing personalizzati.
keywords: Implementazione di Analytics;eVar;variabile di conversione;eVar value;conversion;success event
seo-description: La variabile di conversione dell'intuizione personalizzata (eVar) viene inserita nel codice Adobe su alcune pagine Web del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei report di marketing personalizzati.
seo-title: Conversion Variables (Variabili di conversione) (eVars)
solution: Analytics
title: Conversion Variables (Variabili di conversione) (eVars)
topic: Sviluppatore e implementazione
uuid: 50071c1c-be00-4b3a-a7ee-5d129acf498b
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Conversion Variables (Variabili di conversione) (eVars)

La variabile di conversione dell'intuizione personalizzata (eVar) viene inserita nel codice Adobe su alcune pagine Web del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei report di marketing personalizzati.

Le eVar vengono utilizzate in modo ottimale per misurare la causa e l'effetto, ad esempio:

* Quali campagne interne hanno influenzato le entrate
* Quali banner pubblicitari sono risultati in ultima istanza una registrazione
* Numero di volte in cui è stata utilizzata una ricerca interna prima di eseguire un ordine

>[!IMPORTANT]
>
>Durante l'implementazione di Analytics, è importante sapere quali eVar utilizzerete e quanti. Devi anche capire come configurare queste eVar nell'Admin Console. Per informazioni dettagliate sulle eVar, vedi Variabili di [conversione (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) nella Guida di Analytics e nella documentazione di riferimento.

Un eVar può essere basato su visite e funzionare in modo simile ai cookie. I valori passati alle variabili eVar seguono l'utente per un periodo di tempo predeterminato.

Quando un eVar viene impostato su un valore per un visitatore, Adobe ricorda automaticamente tale valore fino alla scadenza. Eventuali eventi di successo riscontrati da un visitatore mentre il valore eVar è attivo vengono conteggiati per il valore eVar.

> [!NOTE] In una richiesta di immagine è possibile memorizzare un solo valore in una eVar. Se più valori sono desiderati in un valore eVar, si consiglia di implementare le variabili [](/help/implement/js-implementation/c-variables/page-variables.md) Elenco (variabili elenco).

Per ulteriori informazioni sulle variabili, vedi:

* [Variabili per implementazione e reporting](../../implement/js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB) di Analytics in questa guida
* [Variabili - Modalità di utilizzo nei report](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [Variabili pagina](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variabile campagna](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variabile "products"](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variabile](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html) "products" nella documentazione di Mobile SDK

