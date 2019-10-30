---
description: AppMeasurement per JavaScript è una nuova libreria che fornisce le stesse funzionalità di base di s_code.js, ma è più leggera e veloce da utilizzare sia sui siti mobili che su quelli desktop.
keywords: appmeasurement;Analytics Implementation;javascript;appmeasurement for javascript;initialize;retrieve appmeasurement instance;clear vars;clearvars;appmeasurement utility;appmeasurement instance;appmeasurement Benefits
seo-description: AppMeasurement per JavaScript è una nuova libreria che fornisce le stesse funzionalità di base di s_code.js, ma è più leggera e veloce da utilizzare sia sui siti mobili che su quelli desktop.
seo-title: Informazioni su AppMeasurement per JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Informazioni su AppMeasurement per JavaScript
topic: Sviluppatore e implementazione
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Informazioni su AppMeasurement per JavaScript

[!DNL AppMeasurement] per JavaScript è una nuova libreria che fornisce le stesse funzionalità di base di s_code.js, ma è più leggera e veloce da utilizzare sia sui siti mobili che su quelli desktop.

## Things to know before you migrate {#section_B8E7B39E8469468883BA0B41234F21C4}

L'elenco seguente contiene le modifiche da comprendere prima di passare a questa nuova [!DNL AppMeasurement] versione:

* Alcuni plug-in non sono più supportati. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).
* La libreria non supporta la selezione dinamica dell'account ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md)e [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* La libreria e il codice della pagina possono essere distribuiti all'interno del `<head>` tag .
* I moduli Media e Integrate sono supportati utilizzando il codice del modulo aggiornato presente nel pacchetto di download JavaScript [!DNL AppMeasurement] . Il modulo del sondaggio non è supportato.
* Il codice di pagina esistente è compatibile con la nuova versione.
* La libreria fornisce utility native per ottenere parametri di query, cookie di lettura e scrittura ed eseguire il tracciamento avanzato dei collegamenti.

## Domande frequenti {#section_9BD41B08F7B54197B230937714B9357A}

Consultate le [domande frequenti](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3) per informazioni su prestazioni, tracciamento video, dispositivi mobili e altro ancora.

## Processo di inizializzazione {#section_F6D5680F6D134B6AB1F01C6235860635}

Chiama `s_gi()`, passando l’ID della suite di rapporti per inizializzare un’ [!DNL AppMeasurement] istanza:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

Quando `s_gi` viene chiamato, se non esiste un' [!DNL AppMeasurement] istanza per il dato `s_account`, viene creata una nuova istanza. In caso contrario, viene restituita l’istanza esistente. In questo modo si evita di creare oggetti duplicati per lo stesso account.

## Recuperare un'istanza AppMeasurement {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

In tutto il codice, chiamate la funzione [globale](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD) s_gi() per recuperare un' [!DNL AppMeasurement] istanza esistente.

## Utilità {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] fornisce le seguenti utility integrate:

* [Util.cookieRead](../../../implement/js-implementation/util-cookieread.md#concept_33BD774A90504F2C8094DDC16D47440D)
* [Util.cookieWrite](../../../implement/js-implementation/util-cookiewrite.md#concept_9BE4F7D9CDAE4445B9AF3212BC7E61F2)
* [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)

## Cancella variabili {#section_597C411E7EDB42BC9A6A0508C9D57147}

È disponibile un nuovo `clearVars` metodo per cancellare i seguenti valori dall'oggetto instance:

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

* 3-7x più veloce del codice H.25.
* Solo 21 k non compressi e 8 k gzip (H.25 codice 33 k non compresso e 13 k gzip).
* Supporto nativo per diversi plug-in comuni ().
* Piccoli e veloci da usare con i siti mobili e sufficientemente robusti da essere utilizzati su tutto il Web desktop, per sfruttare una singola libreria in tutti gli ambienti Web.

