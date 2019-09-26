---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.linkTrackVars

La variabile è un elenco separato da virgole di variabili che vengono inviate con collegamenti personalizzati, di uscita e di download.

If  is set to "", all variables that have values are sent with link data. *`linkTrackVars`* Per evitare l'inflazione delle istanze o delle visualizzazioni di pagina associate ad altre variabili, Adobe consiglia di compilare *`linkTrackVars`* e *`linkTrackEvents`* nel [!UICONTROL onClick] caso di un collegamento utilizzato per il tracciamento dei collegamenti.

Tutte le variabili che devono essere inviate con dati di collegamento (collegamenti personalizzati, di uscita e di download) devono essere elencate in *`linkTrackVars`*. If *`linkTrackEvents`* is used, *`linkTrackVars`* should contain "events."

| Dimensioni massime | Debugger Parameter | Reports Populated | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Any | "Nessuno" |

When populating , do not use the 's.' prefix for variables. *`linkTrackVars`* Ad esempio, invece di compilare *`linkTrackVars`* con "s.prop1", è consigliabile compilarlo con "prop1". The following example illustrates how  should be used.*`linkTrackVars`*

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

Poiché il collegamento a google.com è un collegamento di uscita (a meno che non siate Google), event1 e eVar1 vengono inviati con i dati del collegamento di uscita, aumentando le istanze associate a eVar1 e il numero di volte in cui event1 viene attivato. In the link to ,  is sent with a value of 'value C' because that is the current value of  at the time that  is called.[!DNL test.php][!UICONTROL eVar1][!UICONTROL eVar1]*`tl()`*

## Syntax and Possible Values

The  variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. *`linkTrackVars`* Utilizzate 'eVar1' invece di 's.eVar1'.

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

The  variable may contain only variables that are sent to , namely: , , , , , , , , , , , and .*`linkTrackVars`*[!DNL Analytics]*`events`**`campaign`**`purchaseID`**`products`*[!UICONTROL eVar1-75][!UICONTROL prop1-75][!UICONTROL hier1-5]*`channel`**`server`**`state`**`zip`**`pageType`*

## Esempi

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## Configuration Settings

Nessuno

## Insidie, domande e suggerimenti

* If  is blank, all variables that have values are tracked with all server calls.*`linkTrackVars`*
* Any variable listed in  that has a value at the time of any download, exit, or custom link, are tracked.*`linkTrackVars`*
* If  is used,  must contain "events."*`linkTrackEvents`**`linkTrackVars`*

* Non utilizzare "s". o "s_objectname." prefix for variables.