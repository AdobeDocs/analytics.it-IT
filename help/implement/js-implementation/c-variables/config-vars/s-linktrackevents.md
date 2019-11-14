---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkTrackEvents

La variabile è un elenco separato da virgole di eventi inviati con un collegamento personalizzato, di uscita o di download. Il `linkTrackEvents` parametro deve includere ogni evento da monitorare con ogni download di file, collegamento di uscita e collegamento personalizzato. Quando si verifica uno di questi tipi di collegamento, viene tracciato il valore corrente di ciascuna variabile identificata. Questa variabile viene considerata solo se `linkTrackVars` contiene "events".

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Conversione | "Nessuno" |

Se un evento non si trova in `linkTrackEvents`, non viene inviato ad Analytics, anche se viene popolato in `onClick` caso di collegamento, come illustrato nell'esempio seguente:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

I valori di [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) e `linkTrackEvents` ignorare le impostazioni nel file JS e assicurarsi che solo le variabili e gli eventi specificati nel codice di collegamento personalizzato siano impostati per il collegamento specifico. Le impostazioni relative a entrambi influiscono su ogni download di file, collegamento di uscita e collegamento personalizzato. Le istanze di ogni variabile ed evento possono essere ingrandite nelle situazioni in cui la variabile (o evento) si applica alla pagina corrente, ma non allo specifico download del file, collegamento di uscita o collegamento personalizzato.

Per garantire che le variabili corrette siano impostate con codice di collegamento personalizzato, Adobe consiglia di impostare *`linkTrackVars`* e *`linkTrackEvents`* all’interno del codice di collegamento personalizzato, come segue:

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

*Nota: Se`linkTrackVars`(o`linkTrackEvents`) è null (o una stringa vuota come ""), vengono tracciate tutte le variabili (o gli eventi) di Analytics definite per la pagina corrente. In altre parole, tutte le variabili con valori vengono inviate con dati di collegamento. Ciò determinerà probabilmente un aumento delle istanze di ogni variabile. Per evitare l'inflazione delle istanze o delle visualizzazioni di pagina associate ad altre variabili, Adobe consiglia di compilare`linkTrackVars`e`linkTrackEvents`nel[!UICONTROL onClick]caso di un collegamento utilizzato per il tracciamento dei collegamenti.*

Tutte le variabili che devono essere inviate con dati di collegamento (collegamenti personalizzati, di uscita e di download) devono essere elencate in `linkTrackVars`. Se `linkTrackEvents` viene utilizzato, `linkTrackVars` deve contenere "events".

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Any | "Nessuno" |

Durante la compilazione `linkTrackEvents`, non utilizzare 's.'. per le variabili. Ad esempio, invece di compilarlo con "s.event1", è consigliabile compilarlo con "event1". L'esempio seguente illustra come dovrebbe essere utilizzato.

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

Nel primo collegamento, la variabile degli eventi mantiene il valore impostato prima che sia fatto clic sul collegamento. Questo consente di inviare event1 con il collegamento personalizzato. Nel secondo esempio, il collegamento a event2 non viene registrato perché non è elencato in `linkTrackEvents`.

Per evitare confusione e potenziali problemi, Adobe consiglia di compilare [`linkTrackVars`](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html) e `linkTrackEvents` nel `onClick` caso di un collegamento utilizzato per il tracciamento dei collegamenti.

## Sintassi e valori possibili

La *`linkTrackEvents`* variabile è un elenco di eventi separati da virgole (senza spazi).

```
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

In `linkTrackEvents`. Questi eventi sono elencati in [Eventi](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html). Se uno spazio compare prima o dopo il nome dell’evento, l’evento non può essere inviato con richieste di immagini di collegamento.

## Esempi

Per tenere traccia `prop1`, `eVar1`e `event1` con ogni download di file, collegamento di uscita e collegamento personalizzato, utilizzate le seguenti impostazioni all'interno del file JS globale:

```
s.linkTrackVars="prop1,eVar1,events"
```

```
s.linkTrackEvents="event1"
```

**Altri esempi**

```
s.linkTrackEvents="purchase,event1"
```

```
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* Il file JavaScript viene utilizzato solo `linkTrackEvents` se `linkTrackVars` contiene la variabile "events". "events" deve essere incluso `linkTrackVars` solo quando `linkTrackEvents` è definito.

* Attenzione se un evento viene attivato su una pagina ed è elencato in `linkTrackEvents`. Tale evento viene registrato nuovamente con eventuali [!UICONTROL exit], [!UICONTROL download]o [!UICONTROL custom] collegamenti, a meno che la variabile degli eventi non venga reimpostata prima di tale evento (in [!UICONTROL onClick] un collegamento o dopo la chiamata alla `t()` funzione).

* Se `linkTrackEvents` contiene spazi tra i nomi degli eventi, gli eventi non vengono registrati.
