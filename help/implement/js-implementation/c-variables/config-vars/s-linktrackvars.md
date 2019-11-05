---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.linkTrackVars

La variabile è un elenco separato da virgole di variabili che vengono inviate con collegamenti personalizzati, di uscita e di download.

Se *`linkTrackVars`* è impostato su "", tutte le variabili con valori vengono inviate con dati di collegamento. Per evitare l'inflazione delle istanze o delle visualizzazioni di pagina associate ad altre variabili, Adobe consiglia di compilare *`linkTrackVars`* e *`linkTrackEvents`* nel [!UICONTROL onClick] caso di un collegamento utilizzato per il tracciamento dei collegamenti.

Tutte le variabili che devono essere inviate con dati di collegamento (collegamenti personalizzati, di uscita e di download) devono essere elencate in *`linkTrackVars`*. Se *`linkTrackEvents`* viene utilizzato, *`linkTrackVars`* deve contenere "events".

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Any | "Nessuno" |

Durante la compilazione *`linkTrackVars`*, non utilizzare 's.'. per le variabili. Ad esempio, invece di compilare *`linkTrackVars`* con "s.prop1", è consigliabile compilarlo con "prop1". L'esempio seguente illustra come *`linkTrackVars`* utilizzare il prodotto.

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

Poiché il collegamento a google.com è un collegamento di uscita (a meno che non siate Google), event1 e eVar1 vengono inviati con i dati del collegamento di uscita, aumentando le istanze associate a eVar1 e il numero di volte in cui event1 viene attivato. Nel collegamento a [!DNL test.php], [!UICONTROL eVar1] viene inviato con il valore "C", perché corrisponde al valore corrente di [!UICONTROL eVar1] al momento in cui *`tl()`* viene chiamato.

## Sintassi e valori possibili

La *`linkTrackVars`* variabile è un elenco di nomi di variabili con distinzione tra maiuscole e minuscole, senza il prefisso del nome dell'oggetto. Utilizzate 'eVar1' invece di 's.eVar1'.

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

La *`linkTrackVars`* variabile può contenere solo variabili a cui è inviato [!DNL Analytics], ovvero: *`events`*, *`campaign`*, *`purchaseID`*, *`products`*, [!UICONTROL eVar1-75], [!UICONTROL prop1-75], [!UICONTROL hier1-5], *`channel`*, *`server`*, *`state`**`zip`**`pageType`*, , e .

## Esempi

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* Se *`linkTrackVars`* è vuoto, tutte le variabili con valori vengono tracciate con tutte le chiamate server.
* Vengono tracciate tutte le variabili elencate in *`linkTrackVars`* cui è associato un valore al momento del download, dell'uscita o del collegamento personalizzato.
* Se *`linkTrackEvents`* viene utilizzato, *`linkTrackVars`* deve contenere "events".

* Non utilizzare "s". o "s_objectname."  per le variabili.
