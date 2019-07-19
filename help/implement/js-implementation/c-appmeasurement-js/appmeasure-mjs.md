---
description: Appmeasurement per javascript è una nuova libreria che offre la stessa funzionalità di base di s_ code. js, ma più leggera e più veloce per l'utilizzo sia sui siti mobili che sui siti desktop.
keywords: appmeasurement; Implementazione di Analytics; javascript; appmeasurement per javascript; initialization; retrieve appmeasurement instance; cancella var; clearvar; appmeasurement utilities; appmeasurement instance; vantaggi delle app
seo-description: Appmeasurement per javascript è una nuova libreria che offre la stessa funzionalità di base di s_ code. js, ma più leggera e più veloce per l'utilizzo sia sui siti mobili che sui siti desktop.
seo-title: Informazioni su appmeasurement per javascript
solution: Analytics
subtopic: Javascript appmeasurement
title: Informazioni su appmeasurement per javascript
topic: Sviluppatore e implementazione
uuid: dc 71 ad 7 a -92 bd -40 cd -8 fab -707 f 6 f 8472 e 2
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Informazioni su appmeasurement per javascript

[!DNL AppMeasurement] per javascript è una nuova libreria che fornisce le stesse funzionalità di base di s_ code. js, ma è più leggera e più veloce per l'utilizzo sia sui siti mobili che sui siti desktop.

## Things to know before you migrate {#section_B8E7B39E8469468883BA0B41234F21C4}

The following list contains changes you need to understand before switching to this new [!DNL AppMeasurement] version:

* Alcuni plug-in non sono più supportati. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).
* The library does not support dynamic account selection ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md), and [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* The library and page code can be deployed inside the `<head>` tag.
* The Media and Integrate modules are supported using updated module code that is in the JavaScript [!DNL AppMeasurement] download package. Il modulo Sondaggio non è supportato.
* Il codice della pagina esistente è compatibile con la nuova versione.
* La libreria fornisce utility native per ottenere parametri di query, leggere e scrivere i cookie ed eseguire il tracciamento avanzato dei collegamenti.

## Domande frequenti {#section_9BD41B08F7B54197B230937714B9357A}

See the [FAQ](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3) for information about performance, video tracking, mobile, and more.

## Initialization process {#section_F6D5680F6D134B6AB1F01C6235860635}

Call `s_gi()`, passing the report suite ID to initialize an [!DNL AppMeasurement] instance:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

When `s_gi` is called, if an [!DNL AppMeasurement] instance does not exist for the specified `s_account`, a new instance is created. In caso contrario, viene restituita l'istanza esistente. In questo modo si evita di creare oggetti duplicati per lo stesso account.

## Retrieve an AppMeasurement instance {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

Throughout your code, call the global [s_gi() function](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD) to retrieve an existing [!DNL AppMeasurement] instance.

## Utilities {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] provides the following built-in utilities:

* [Util. cookieread](../../../implement/js-implementation/util-cookieread.md#concept_33BD774A90504F2C8094DDC16D47440D)
* [Util. cookiewrite](../../../implement/js-implementation/util-cookiewrite.md#concept_9BE4F7D9CDAE4445B9AF3212BC7E61F2)
* [Util. getqueryparam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)

## Clear Vars {#section_597C411E7EDB42BC9A6A0508C9D57147}

A new `clearVars` method is available to clear the following values from the instance object:

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

Ad esempio:

```js
s.clearVars()
```

## Vantaggi {#section_091E5A28E89E438E8A54A95F55165743}

* 3-7 x più veloce del codice H .25.
* Solo 21 k non compressa e 8 kzicompressa (il codice H .25 è di 33 k non compresso e 13 k è decompressa).
* Supporto nativo per diversi plug-in comuni ().
* Sufficientemente veloce e veloce da usare con siti mobili e sufficientemente robusti da utilizzare sul web desktop completo, consentendoti di sfruttare una singola libreria in tutti gli ambienti web.

