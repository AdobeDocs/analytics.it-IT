---
description: La variabile di conversione personalizzata (o evar) viene inserita nel codice Adobe sulle pagine Web selezionate del sito. Il suo scopo primario è quello di segmentare le metriche di successo conversione nei report di marketing personalizzati.
keywords: Implementazione di Analytics; Evar; variabile di conversione; Evar, valore; conversione; Evento success
seo-description: La variabile di conversione personalizzata (o evar) viene inserita nel codice Adobe sulle pagine Web selezionate del sito. Il suo scopo primario è quello di segmentare le metriche di successo conversione nei report di marketing personalizzati.
seo-title: Variabili di conversione (evars)
solution: Analytics
title: Variabili di conversione (evars)
topic: Sviluppatore e implementazione
uuid: 50071 c 1 c-be 00-4 b 3 a-a 7 ee -5 d 129 acf 498 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variabili di conversione (evars)

La variabile di conversione personalizzata (o evar) viene inserita nel codice Adobe sulle pagine Web selezionate del sito. Il suo scopo primario è quello di segmentare le metriche di successo conversione nei report di marketing personalizzati.

Le evar sono utilizzate per misurare cause ed effetti, ad esempio:

* Campagne interne influite sui ricavi
* Quali annunci banner hanno generato una registrazione
* Numero di volte in cui è stata utilizzata una ricerca interna prima di effettuare un ordine

>[!IMPORTANT]
>
>Durante l'implementazione di Analytics, è importante sapere quali evar utilizzeranno e quanti. Devi anche comprendere come configurare queste evar in Admin Console. For detailed information about eVars, see [Conversion Variables (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) in the Analytics Help and reference documentation.

Un evar può essere basato su visite e funziona in modo simile ai cookie. I valori passati nelle variabili evar seguono l'utente per un periodo di tempo predeterminato.

Quando un evar è impostato su un valore per un visitatore, Adobe ricorda automaticamente tale valore fino alla scadenza. Tutti gli eventi di successo rilevati da un visitatore mentre il valore evar è attivo vengono conteggiati verso il valore evar.

>[!NOTE]
>
>In una richiesta di immagine è possibile memorizzare solo un singolo valore. If multiple values are desired in an eVar value, we recommend that you implement [List variables](/help/implement/js-implementation/c-variables/page-variables.md) (list vars).

Per ulteriori informazioni sulle variabili, vedi:

* [Variabili per implementazione e reporting di Analytics](../../implement/js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB) in questa guida
* [Variabili - Modalità di utilizzo nel reporting](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [Variabili di pagina](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variabile Campaign](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variabile "products"](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variabile dei prodotti](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html) nella documentazione SDK di Mobile

