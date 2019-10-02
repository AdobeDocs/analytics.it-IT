---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# s.dynamicAccountList

> [!NOTE] La `s.dynamicAccountList` variabile non è supportata nelle librerie [AppMeasurement](../../c-appmeasurement-js/appmeasure-mjs.md)correnti. It is only used in legacy AppMeasurement, such as H Code.

La `s.dynamicAccountList` variabile viene utilizzata per determinare in modo dinamico una suite di rapporti a cui inviare i dati. It is used in conjunction with the `dynamicAccountSelection` and `dynamicAccountMatch` variables. Le regole in `dynamicAccountList` vengono applicate se `dynamicAccountSelection` sono impostate su `true`, e si applicano alla sezione dell'URL specificata in `dynamicAccountMatch`.

## Sintassi e valori possibili

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

Valid input is a semicolon-separated list of name=value pairs (rules). Each list contains the following items:

* Uno o più ID suite di rapporti (separati da virgole)
* An equals sign
* Uno o più filtri URL (separati da virgole)

Nella stringa devono essere utilizzati solo i caratteri ASCII standard (senza spazi).

## Esempi

For all the following examples, the page URL is , the  variable is set to , and the  variable is set to .`https://example.com/path2/?prod_id=12345``dynamicAccountSelection``true``s_account``examplersid`

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

## Pitfalls, Questions, and Tips

* The rules listed in this variable are applied in a left-to-right order. If the  variable matches more than one rule, the left-most rule is used to determine the report suite. `dynamicAccountMatch` As a result, place more generic rules to the right of the list.
* If no rules match, the default report suite in `s_account` is used.
* If your page is saved to someone's hard drive or translated via a web-based translation engine (such as Google's translated pages), the dynamic account selection likely won't work.
* The  rules apply only to the section of the URL specified in .`dynamicAccountSelection``dynamicAccountMatch`
* Use the [!DNL Adobe Experience Cloud Debugger] to test the destination report suite.
