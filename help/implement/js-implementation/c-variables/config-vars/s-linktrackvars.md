---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkTrackVars

La variabile è un elenco separato da virgole di variabili che vengono inviate con collegamenti personalizzati, di uscita e di download.

Il [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) parametro deve includere ogni variabile da monitorare con ogni download di file, collegamento di uscita e collegamento personalizzato.

Le impostazioni per `linkTrackVars` e all'interno `linkTrackEvents` del file JS influiscono su ogni download di file, collegamento di uscita e collegamento personalizzato. Le istanze di ogni variabile ed evento possono essere ingrandite nelle situazioni in cui la variabile (o evento) si applica alla pagina corrente, ma non allo specifico download del file, collegamento di uscita o collegamento personalizzato.

Per garantire che le variabili corrette siano impostate con codice di collegamento personalizzato, Adobe consiglia di impostare `linkTrackVars` e `linkTrackEvents` all’interno del codice di collegamento personalizzato, come segue:

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

Nell'esempio precedente, il valore per prop1 è impostato all'interno del codice di collegamento personalizzato stesso. Il valore di prop2 deriva dal valore corrente della variabile impostato sulla pagina.

I valori di `linkTrackVars` e `linkTrackEvents` ignorare le impostazioni nel file JS e assicurarsi che solo le variabili e gli eventi specificati nel codice di collegamento personalizzato siano impostati per il collegamento specifico.

*Nota: Se`linkTrackVars`(o`linkTrackEvents`) è null (o una stringa vuota come ""), vengono tracciate tutte le variabili (o gli eventi) di Analytics definite per la pagina corrente. In altre parole, tutte le variabili con valori vengono inviate con dati di collegamento. Ciò determinerà probabilmente un aumento delle istanze di ogni variabile. Per evitare l'inflazione delle istanze o delle visualizzazioni di pagina associate ad altre variabili, Adobe consiglia di compilare`linkTrackVars`e`linkTrackEvents`nel[!UICONTROL onClick]caso di un collegamento utilizzato per il tracciamento dei collegamenti.*

Tutte le variabili che devono essere inviate con dati di collegamento (collegamenti personalizzati, di uscita e di download) devono essere elencate in `linkTrackVars`. Se `linkTrackEvents` viene utilizzato, `linkTrackVars` deve contenere "events".

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Any | "Nessuno" |

Durante la compilazione `linkTrackVars`, non utilizzare 's.'. per le variabili. Ad esempio, invece di compilare `linkTrackVars` con "s.prop1", è consigliabile compilarlo con "prop1". L'esempio seguente illustra come `linkTrackVars` utilizzare il prodotto.

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

Poiché il collegamento a google.com è un collegamento di uscita (a meno che non siate Google), event1 e eVar1 vengono inviati con i dati del collegamento di uscita, aumentando le istanze associate a eVar1 e il numero di volte in cui event1 viene attivato. Nel collegamento a [!DNL test.php], [!UICONTROL eVar1] viene inviato con un valore "C", perché corrisponde al valore corrente di eVar1 nel momento in cui `tl()` viene chiamato.

## Sintassi e valori possibili

La `linkTrackVars` variabile è un elenco di nomi di variabili con distinzione tra maiuscole e minuscole, senza il prefisso del nome dell'oggetto. Utilizzate 'eVar1' invece di 's.eVar1'.

```
s.linkTrackVars="variable_name[,variable_name[...]]"
```

La `linkTrackVars` variabile può contenere solo variabili a cui è inviato [!DNL Analytics], ovvero: `events`, `campaign`, `purchaseID`, `products`, `eVar1-75`, `prop1-75`, `hier1-5`, `channel`, `server`, `state``zip``pageType`, , e .

## Esempi

```
s.linkTrackVars="events,prop1,eVar49"
```

```
s.linkTrackVars="products"
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* Se `linkTrackVars` è vuoto, tutte le variabili con valori vengono tracciate con tutte le chiamate server.
* Vengono tracciate tutte le variabili elencate in `linkTrackVars` cui è associato un valore al momento del download, dell'uscita o del collegamento personalizzato.
* Se `linkTrackEvents` viene utilizzato, `linkTrackVars` deve contenere "events".

* Non utilizzare "s". o "s_objectname."  per le variabili.
