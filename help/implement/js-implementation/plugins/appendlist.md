---
description: Il plug-in apl (o appendlist) consente di aggiungere un valore a qualsiasi elenco delimitato, con l'opzione di un controllo con distinzione tra maiuscole e minuscole per verificare che il valore non sia già presente nell'elenco. A un plug-in APL viene fatto riferimento da diversi plug-in standard, che possono essere utilizzati direttamente in diverse situazioni.
keywords: Implementazione di Analytics
seo-description: Il plug-in apl (o appendlist) consente di aggiungere un valore a qualsiasi elenco delimitato, con l'opzione di un controllo con distinzione tra maiuscole e minuscole per verificare che il valore non sia già presente nell'elenco. A un plug-in APL viene fatto riferimento da diversi plug-in standard, che possono essere utilizzati direttamente in diverse situazioni.
seo-title: Appendlist
solution: Analytics
subtopic: Plug-in
title: Appendlist
topic: Sviluppatore e implementazione
uuid: e 923 c 86 c-eaa 6-4 e 17-a 3 a 4-0 e 08 af 886674
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Appendlist

Il plug-in apl (o appendlist) consente di aggiungere un valore a qualsiasi elenco delimitato, con l'opzione di un controllo con distinzione tra maiuscole e minuscole per verificare che il valore non sia già presente nell'elenco. A un plug-in APL viene fatto riferimento da diversi plug-in standard, che possono essere utilizzati direttamente in diverse situazioni.

Questo plug-in è utile per:

* Aggiunta di un evento alla variabile eventi corrente
* Aggiunta di un valore a una variabile elenco senza duplicare un valore nell'elenco
* Aggiunta di un prodotto alla variabile prodotti corrente in base ad alcuni logica della pagina
* Adding values to the parameters *`linkTrackVars`* and *`linkTrackEvents`*

**Caso d'uso 1**

<table id="table_5AAC1D9892CD4E5C9060E119EE4E7DC8"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Scenario </p> </td> 
   <td colname="col2"> <p>Add <span class="term"> event1 </span> to the current events variable while ensuring the event isn't duplicated. </p> <p>s. events = "sccheckout" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice </p> </td> 
   <td colname="col2"> <p>s. events = s. apl (s. events, "event 1", ",", 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Risultati </p> </td> 
   <td colname="col2"> <p>s. events = "sccheckout, event 1" </p> </td> 
  </tr> 
 </tbody> 
</table>

**Caso d'uso 2**

<table id="table_C4356C9AB95948F3929A7B75E07AE9E7"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Scenario </p> </td> 
   <td colname="col2"> <p>Add the value <span class="term"> history </span> to the list variable <span class="varname"> prop1 </span>, with <span class="term"> history </span> and <span class="term"> History </span> considered the same value. </p> <p>s. prop 1 = "Science, History" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice </p> </td> 
   <td colname="col2"> <p>s. prop 1 = s. apl (s. apl 1, "history", ",", 2) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Risultati </p> </td> 
   <td colname="col2"> <p>s. prop 1 = "Science, History" </p> <p> <span class="term"> history </span> non viene aggiunta perché <span class="term"> History </span> è già presente nell'elenco. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le istruzioni seguenti richiedono di modificare il codice della raccolta dati sul sito. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Implementazione {#section_F4C91CA2037F478C9F7B53F357E6A5F0}

Per implementare il plug-in APL, effettuate le seguenti operazioni.

1. Richiedi il codice plug-in dall'Assistenza clienti o dal consulente Adobe attualmente assegnato.
1. Add call(s) to the API function as needed within the *`s_doPlugins`* function

Questo è l'aspetto del codice sul sito:

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

Questo plug-in richiede che il browser supporti javascript versione 1.0.

**Informazioni plug-in**

<table id="table_7B9EDD616C164D6B8B53558337DF12C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Informazioni plug-in </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Parametri </p> </td> 
   <td colname="col2"> <p>apl ((L, v, d, u) </p> <p>L = elenco sorgente, elenco vuoto </p> <p> v = valore da aggiungere </p> <p> d = delimitatore elenco </p> <p> u (facoltativo, impostazione predefinita 0) Controllo del valore univoco. 0 = nessun controllo univoco, il valore viene sempre aggiunto. Check 1 = check-insensitive check, append only if value is't nell list. 2 = controllo sensibile alle maiuscole/minuscole, aggiungete solo se il valore non è nell'elenco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valore restituito </p> </td> 
   <td colname="col2"> <p>elenco originale, con valore aggiunto se aggiunto </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esempi di utilizzo </p> </td> 
   <td colname="col2"> <p>s. events = s. apl (s. events, "event 1", ",", 1); </p> </td> 
  </tr> 
 </tbody> 
</table>

The source list L can be an empty list, such as *`L=""`*. Il valore restituito sarà un elenco vuoto o un elenco di un valore.

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

