---
description: Acquisisce il valore di una variabile di Analytics nella visualizzazione pagina successiva. Ad esempio, potete utilizzare il plug-in per acquisire il valore s.pageName dalla visualizzazione pagina precedente in una variabile Traffico personalizzato. È inoltre disponibile un'opzione per acquisire un valore precedente solo quando sono impostati eventi di successo specifici.
keywords: Implementazione di Analytics
seo-description: Acquisisce il valore di una variabile di Analytics nella visualizzazione pagina successiva. Ad esempio, potete utilizzare il plug-in per acquisire il valore s.pageName dalla visualizzazione pagina precedente in una variabile Traffico personalizzato. È inoltre disponibile un'opzione per acquisire un valore precedente solo quando sono impostati eventi di successo specifici.
seo-title: getPreviousValue
solution: Analytics
subtopic: Plug-in
title: getPreviousValue
topic: Sviluppatore e implementazione
uuid: 20da7b4a-9820-4690-a1cc-d10b6dd627a7
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# getPreviousValue

Acquisisce il valore di una variabile di Analytics nella visualizzazione pagina successiva. Ad esempio, potete utilizzare il plug-in per acquisire il valore s.pageName dalla visualizzazione pagina precedente in una variabile Traffico personalizzato. È inoltre disponibile un'opzione per acquisire un valore precedente solo quando sono impostati eventi di successo specifici.

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

## Codice plug-in e implementazione {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SEZIONE** CONFIGURAZIONE: Nessuna modifica richiesta per questa sezione.

**Configurazione plug-in**

Inserire il codice seguente all'interno della *`s_doPlugins()`* funzione, che si trova nell'area del *`s_code.js`* file denominato *Plugin Config*. Scegliete una variabile Traffico personalizzato (s.prop) o Conversione personalizzata (s.eVar) da usare per l’acquisizione di dati di valore persistenti. Deve essere una variabile abilitata tramite Admin Console, ma attualmente non utilizzata per altri scopi. Potete utilizzare l'esempio seguente e aggiornarlo in base alle vostre esigenze.

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`* presenta tre argomenti:

1. Variabile da acquisire dalla pagina precedente ( *`s.pageName`* sopra).
1. Nome del cookie da utilizzare per memorizzare il valore per il recupero ( *`gpv_pn`* sopra).
1. Gli eventi che devono essere impostati nella visualizzazione pagina per attivare il recupero del valore precedente ( *`event1`* sopra). Se lasciato vuoto o omesso, il plug-in acquisisce il valore precedente in tutte le visualizzazioni di pagina.

**SEZIONE** PLUG-IN: Aggiungere il codice seguente all'area del [!DNL s_code.js] file con etichetta PLUGINS SECTION. Non apportare modifiche a questa parte del codice plug-in.

```js
/* 
 * Plugin: getPreviousValue_v1.0 - return previous value of designated 
 * variable (requires split utility) 
 */ 
s.getPreviousValue=new Function("v","c","el","" 
+"var s=this,t=new Date,i,j,r='';t.setTime(t.getTime()+1800000);if(el" 
+"){if(s.events){i=s.split(el,',');j=s.split(s.events,',');for(x in i" 
+"){for(y in j){if(i[x]==j[y]){if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t)" 
+":s.c_w(c,'no value',t);return r}}}}}else{if(s.c_r(c)) r=s.c_r(c);v?" 
+"s.c_w(c,v,t):s.c_w(c,'no value',t);return r}"); 
/* 
 * Utility Function: split v1.5 - split a string (JS 1.0 compatible) 
 */ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a"); 
```

**Note**

* Verificate sempre in modo esteso le installazioni dei plug-in per garantire che la raccolta dei dati avvenga come previsto prima della distribuzione in un ambiente di produzione.
* Se non è presente alcun valore per la variabile selezionata su una determinata pagina, il testo *non verrà impostato alcun valore* nel cookie.
* Per ogni cookie viene ora impostata una scadenza fissa di 30 minuti, che viene aggiornata con ogni caricamento di pagina. Il plug-in funziona per tutta la durata di una visita.
* Poiché la funzione deve essere chiamata come parte della sezione dei plug-in del codice, il codice viene eseguito ogni volta *`s.t()`* o *`s.tl()`* viene chiamato.

* La variabile selezionata deve essere compilata con un valore prima della chiamata a *`s.getPreviousValue`*. Poiché la *`s_doPlugins()`* funzione viene eseguita dopo la compilazione delle variabili sulla pagina, questo problema si verifica raramente. Dovrebbe essere preoccupante solo se la variabile utilizzata con questo plug-in viene compilata all'interno della *`s_doPlugins()`* funzione e dopo la chiamata a *`s.getPreviousValue`*.

