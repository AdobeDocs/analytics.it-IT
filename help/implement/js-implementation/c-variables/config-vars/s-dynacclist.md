---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountList

> [!NOTE] La `s.dynamicAccountList` variabile non è supportata nelle librerie [AppMeasurement](../../c-appmeasurement-js/appmeasure-mjs.md)correnti. È utilizzato solo in AppMeasurement legacy, ad esempio H Code.

La `s.dynamicAccountList` variabile viene utilizzata per determinare in modo dinamico una suite di rapporti a cui inviare i dati. Viene utilizzato insieme alle `dynamicAccountSelection` variabili e `dynamicAccountMatch` alle variabili. Le regole in `dynamicAccountList` vengono applicate se `dynamicAccountSelection` sono impostate su `true`, e si applicano alla sezione dell'URL specificata in `dynamicAccountMatch`.

## Sintassi e valori possibili

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

Un input valido è un elenco separato da punto e virgola di coppie nome=valore (regole). Ciascun elenco contiene i seguenti elementi:

* Uno o più ID suite di rapporti (separati da virgole)
* Simbolo uguale a
* Uno o più filtri URL (separati da virgole)

Nella stringa devono essere utilizzati solo i caratteri ASCII standard (senza spazi).

## Esempi

Per tutti gli esempi seguenti, l’URL della pagina è `https://example.com/path2/?prod_id=12345`, la `dynamicAccountSelection` variabile è impostata su `true`e la `s_account` variabile è impostata su `examplersid`.

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## Insidie, domande e suggerimenti

* Le regole elencate in questa variabile vengono applicate in ordine da sinistra a destra. Se la `dynamicAccountMatch` variabile corrisponde a più regole, per determinare la suite di rapporti viene utilizzata la regola più a sinistra. Di conseguenza, collocate a destra dell'elenco regole più generiche.
* Se nessuna regola corrisponde, `s_account` viene utilizzata la suite di rapporti predefinita in.
* Se la pagina viene salvata sul disco rigido di un utente o tradotta tramite un motore di traduzione basato sul Web (come le pagine tradotte di Google), la selezione dell'account dinamico probabilmente non funzionerà.
* Le `dynamicAccountSelection` regole si applicano solo alla sezione dell'URL specificato in `dynamicAccountMatch`.
* Utilizzate l'icona [!DNL Adobe Experience Cloud Debugger] per testare la suite di rapporti di destinazione.
