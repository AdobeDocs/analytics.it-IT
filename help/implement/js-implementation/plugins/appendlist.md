---
description: Il plug-in apl (o appendList) consente di aggiungere un valore a qualsiasi elenco delimitato, con l'opzione di un controllo sensibile alle maiuscole/minuscole o senza distinzione tra maiuscole e minuscole per verificare che il valore non sia già presente nell'elenco. Il plug-in APL è indicato da diversi plug-in standard, ma può essere utilizzato direttamente in diverse situazioni.
keywords: Analytics Implementation
solution: Analytics
subtopic: Plug-ins
title: appendList
topic: Developer and implementation
uuid: e923c86c-eaa6-4e17-a3a4-0e08af886674
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# appendList

Il plug-in apl (o appendList) consente di aggiungere un valore a qualsiasi elenco delimitato, con l'opzione di un controllo sensibile alle maiuscole/minuscole o senza distinzione tra maiuscole e minuscole per verificare che il valore non sia già presente nell'elenco. Il plug-in APL è indicato da diversi plug-in standard, ma può essere utilizzato direttamente in diverse situazioni.

Questo plug-in è utile per:

* Aggiunta di un evento alla variabile degli eventi correnti
* Aggiunta di un valore a una variabile di elenco senza duplicazione di un valore nell'elenco
* Aggiunta di un prodotto alla variabile "products" corrente in base ad una logica di pagina
* Aggiunta di valori ai parametri *`linkTrackVars`* e *`linkTrackEvents`*

**Caso di utilizzo 1**

<table id="table_5AAC1D9892CD4E5C9060E119EE4E7DC8"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Scenario </p> </td> 
   <td colname="col2"> <p>Aggiungete <span class="term"> event1 </span> alla variabile degli eventi correnti, accertandovi che l'evento non sia duplicato. </p> <p>s.events="scCheckout" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Risultati </p> </td> 
   <td colname="col2"> <p>s.events="scCheckout,event1" </p> </td> 
  </tr> 
 </tbody> 
</table>

**Caso d’uso 2**

<table id="table_C4356C9AB95948F3929A7B75E07AE9E7"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Scenario </p> </td> 
   <td colname="col2"> <p>Aggiungete la cronologia del valore <span class="term"> alla variabile di elenco </span> prop1 <span class="varname"> , </span>cronologia <span class="term"> e </span> cronologia <span class="term"> </span> considerate lo stesso valore. </p> <p>s.prop1="Scienza, Storia" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice </p> </td> 
   <td colname="col2"> <p>s.prop1=s.apl(s.prop1,"history",",",2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Risultati </p> </td> 
   <td colname="col2"> <p>s.prop1="Scienza, Storia" </p> <p> <span class="term"> la cronologia non </span> è stata aggiunta perché <span class="term"> History </span> è già presente nell'elenco. </p> </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

## Implementazione {#section_F4C91CA2037F478C9F7B53F357E6A5F0}

Per implementare il plug-in APL, effettuate le seguenti operazioni.

1. Richiedete il codice plug-in all'Assistenza clienti o al consulente Adobe attualmente assegnato.
1. Aggiungi le chiamate alla funzione API secondo necessità all'interno della *`s_doPlugins`* funzione

Di seguito viene illustrato l’aspetto del codice sul sito:

```js
/* Plugin Config */ 
 
s.usePlugins=true 
 
function s_doPlugins(s) { 
 
/* Add calls to plugins here */ 
 
s.events=s.apl(s.events,"event1",",",1) 
 
} 
 
s.doPlugins=s_doPlugins
```

**Browser supportati**

Questo plug-in richiede che il browser supporti JavaScript versione 1.0.

**Informazioni sui plug-in**

<table id="table_7B9EDD616C164D6B8B53558337DF12C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Informazioni sui plug-in </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Parametri </p> </td> 
   <td colname="col2"> <p>apl((L,v,d,u) </p> <p>L= elenco di origine, elenco vuoto accettato </p> <p> v = valore da aggiungere </p> <p> d = delimiter elenco </p> <p> u (facoltativo, con impostazione predefinita 0) Controllo del valore univoco. 0=nessun controllo univoco. Il valore viene sempre aggiunto. 1=verifica senza distinzione tra maiuscole e minuscole, aggiungere solo se il valore non è nell’elenco. 2=controllo sensibile alle maiuscole/minuscole, aggiungere solo se il valore non è nell’elenco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valore restituito </p> </td> 
   <td colname="col2"> <p>elenco originale, con valore aggiunto </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esempi di utilizzo </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1); </p> </td> 
  </tr> 
 </tbody> 
</table>

L'elenco di origine può essere un elenco vuoto, ad esempio *`L=""`*. Il valore restituito sarà un elenco vuoto o un elenco di un valore.

**Codice plug-in**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin Utility: apl v1.1 
 */ 
s.apl=new Function("l","v","d","u","" 
+"var s=this,m=0;if(!l)l='';if(u){var i,n,a=s.split(l,d);for(i=0;i<a." 
+"length;i++){n=a[i];m=m||(u==1?(n==v):(n.toLowerCase()==v.toLowerCas" 
+"e()));}}if(!m)l=l?l+d+v:v;return l"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
  
 Not Applicable - Utility function only 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 s.split
```

