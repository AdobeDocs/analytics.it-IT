---
description: Per l'evento di acquisto, le variabili Analytics vengono utilizzate per acquisire informazioni di acquisto specifiche. La variabile s. purchaseid viene utilizzata per serializzare (eliminare) l'evento.
keywords: Implementazione di Analytics
seo-description: Per l'evento di acquisto, le variabili Analytics vengono utilizzate per acquisire informazioni di acquisto specifiche. La variabile s. purchaseid viene utilizzata per serializzare (eliminare) l'evento.
seo-title: Eventi di acquisto
solution: Analytics
title: Eventi di acquisto
topic: Sviluppatore e implementazione
uuid: d 90 cdec 7-7397-445 a -84 e 5-31014 f 7 ff 875
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Eventi di acquisto

Per l'evento di acquisto, le variabili Analytics vengono utilizzate per acquisire informazioni di acquisto specifiche. La variabile s. purchaseid viene utilizzata per serializzare (eliminare) l'evento.

The *`purchaseID`* is limited to 20 characters. The *`purchaseID`* variable serializes all events passed in the variable [!UICONTROL s.events], and overrides any serialization value for events. If *`purchaseID`* is left blank, each instance of the purchase event, even page reloads, is counted.

If a purchase event is called without a *`purchaseID`*, a unique one is automatically generated based on the *`s.products`* and *`s.events`* variables. This automatically generated *`purchaseID`* is stored locally as a cookie value within the visitor's browser, and is not sent to any report suite tables. Manually defined *`purchaseID`*s on the other hand are sent to a back-end table within the report suite. The last five purchases made by a visitor (with or without *`purchaseID`*) are stored in the local cookie.

Quando un visitatore effettua un acquisto, vengono eseguiti i seguenti controlli:

* *`purchaseID`* Soddisfa i cinque valori di cookie? In tal caso, la richiesta dell'immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l'evento di acquisto, non vengono visualizzate nei report.
* If *`purchaseID`* is defined, does it match any value in the report suite's back-end table? In tal caso, la richiesta dell'immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l'evento di acquisto, non vengono visualizzate nei report.
* If the *`purchaseID`* is unique to both the last 5 stored values in the cookie and the report suite's *`purchaseID`* table, the image request is unique and included in reporting. Ad esempio, se nel cookie locale sono già inclusi cinque acquisti, il più vecchio viene sovrascritto.

Un codice lato server specifico può essere utilizzato per generare il numero univoco (valore alfanumerico) incorporato nell'origine HTML. In genere, a questo scopo viene utilizzato l'ID ordine, o un valore alfanumerico simile. Questo valore non deve cambiare se l'utente aggiorna la pagina. The following is a short example (note the *`purchaseID`* code in bold):

## Sintassi {#section_4FBF138093BD41F59885D2ACC429FF5B}

```js
s.products="Category;ProductName;Qty;total_price [,Category2;ProductName2;Qty;total_price]" 
s.state="XX" 
s.zip="00000" 
 
<b>s.purchaseID="<%=getPurchaseID()%>"</b> 
s.events="purchase" 
```

## Esempi {#section_2CBA9B6386A146C0BEF375E1B55687BC}

```js
s.products="Footwear;Hiking Boots (1234);1;170.00" 
s.state="UT" 
s.zip="84097" 
s.purchaseID="12341234" 
s.events="purchase"
```

## Note aggiuntive {#section_5A0590B8FD4F40DC89776F55ED9DE668}

* Assicuratevi di utilizzare il codice lato server per generare l'identificatore univoco dell'evento. Do not use a JavaScript randomization function to generate a number, which generates unique numbers each time the page is loaded (each [!UICONTROL instance]/ [!UICONTROL pageview] counts).

* Gli identificatori unici sono applicabili a tutti gli utenti per tutte le sessioni. Pertanto, assicuratevi che l'identificatore sia univoco tra utenti e sessioni. For instance, if the Order ID repeats after 30 days, append the date of the order to make the [!UICONTROL Order ID] sufficiently unique.
* Il valore di serializzazione può contenere valori alfanumerici fino a 20 caratteri. This is identical to the limitations of [!UICONTROL s.purchaseID] (replace s. with s_ for G Code).
* The [!UICONTROL s.purchaseID] variable serializes all events passed in the variable [!UICONTROL s.events], and overrides any serialization value for events. Do not use [!UICONTROL Event serialization] for any events if the [!UICONTROL s.purchaseID] variable is used on the current page (replace s. with s_ for G Code).

