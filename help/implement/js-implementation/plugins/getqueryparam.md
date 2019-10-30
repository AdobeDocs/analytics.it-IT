---
description: Restituisce il valore di un parametro di stringa di query specificato, se presente nell’URL della pagina corrente. Perché dati importanti (come codici di tracciamento campagna, parole chiave di ricerca interne, ecc.) è disponibile nella stringa di query su una pagina, getQueryParam consente di acquisire i dati nelle variabili di Analytics.
keywords: Implementazione di Analytics
seo-description: Restituisce il valore di un parametro di stringa di query specificato, se presente nell’URL della pagina corrente. Perché dati importanti (come codici di tracciamento campagna, parole chiave di ricerca interne, ecc.) è disponibile nella stringa di query su una pagina, getQueryParam consente di acquisire i dati nelle variabili di Analytics.
seo-title: getQueryParam
solution: Analytics
subtopic: Plug-in
title: getQueryParam
topic: Sviluppatore e implementazione
uuid: ba202756-c728-4ebc-8fd9-5bc29a9f673b
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# getQueryParam

Restituisce il valore di un parametro di stringa di query specificato, se presente nell’URL della pagina corrente. Perché dati importanti (come codici di tracciamento campagna, parole chiave di ricerca interne, ecc.) è disponibile nella stringa di query su una pagina, getQueryParam consente di acquisire i dati nelle variabili di Analytics.

>[!IMPORTANT]
>
>Questo plug-in è utilizzato solo dal codice H. [AppMeasurement per JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) fornisce questa funzionalità in modo nativo utilizzando [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

Una volta installato nel [!DNL AppMeasurement] codice JavaScript, il plug-in viene configurato selezionando una [!DNL Analytics] variabile da compilare utilizzando i dati presenti nella stringa di query e specificando i valori stringa di query da acquisire. Il plug-in rileva la stringa di query specificata, se presente, e compila la variabile scelta con il relativo valore. Se con tale valore non viene trovato alcun parametro di stringa di query, viene restituita una stringa vuota. Se un parametro di stringa di query esiste ma non ha un valore (come param1 in `?param1&param2=value`), viene restituita la parola *`true`* .

> [!NOTE] Il codice di base per il plug-in deve essere installato nel codice JavaScript [!DNL AppMeasurement] per consentire il funzionamento degli esempi seguenti.

Se desiderate utilizzare *`s.campaign`* per acquisire i codici di tracciamento campagna disponibili come valori del parametro di *`cid`* query, immettete quanto segue nella *`doPlugins()`* funzione nel codice [!DNL AppMeasurement] per JavaScript:

`s.campaign=s.getQueryParam('cid')`

In questo esempio, se l’utente arrivava a una pagina di destinazione sul sito in cui si trovava l’URL, [!DNL https://www.yoursite.com/index.html?cid=123456]riceverebbe un valore pari a *`s.campaign`* 123456 **. Questo potrebbe essere visualizzato utilizzando il [!DNL DigitalPulse] file [!UICONTROL Debugger], che dovrebbe mostrare *v0=123456* come parte della richiesta di immagine.

> [!NOTE] Il parametro *`cid`* e altri sono utilizzati come esempi. Potete sostituirli con eventuali parametri di stringa di query presenti sul sito.

Il *`getQueryParam`* plug-in dispone di due argomenti aggiuntivi (opzioni) che possono essere utilizzati per acquisire dati in variabili Analytics:

```js
s.getQueryParam('p','d','u') 
 
where: 
p = comma-separated list of query parameters to locate (can also be a single value with no comma) 
d = delimiter for list of values (in case more than one specified parameter is found) 
u = where to search for value (e.g., document.referrer); set to current page URL by default
```

Se *p* è un elenco di parametri di stringa di query e nell’URL si trova più di un parametro di stringa di query, tutti i valori vengono restituiti in un elenco separato dal carattere di delimitazione, *d*, che può essere un singolo carattere o una stringa di caratteri, ad esempio " : " (spazio-due punti). Se *d* viene omesso, non viene utilizzato alcun delimitatore tra i valori. Se un parametro della stringa di query ha la precedenza su un altro, quando entrambi vengono trovati, utilizzare un'istruzione *if* come illustrato di seguito.

```js
// cid takes precedence over iid if both exist in the query string 
s.campaign=s.getQueryParam('cid'); 
 if(!s.campaign) 
 s.campaign=s.getQueryParam('iid'); 
```

A partire dalla versione *`getQueryParam`* v2.0, il plug-in accetta un terzo argomento opzionale, *u*, che consente di specificare l'URL dal quale si desidera estrarre i parametri delle stringhe di query. Per impostazione predefinita (ovvero se questo terzo argomento viene omesso o lasciato vuoto), il plug-in utilizza l’URL della pagina. Ad esempio, se desiderate estrarre una stringa di query dal referente, potete utilizzare il seguente codice:

```js
// take the query string from the referrer 
 s.eVar1=s.getQueryParam('pid','',document.referrer); 
```

Il flag "f" deve essere utilizzato in questo terzo argomento con i frame, quando il parametro della stringa di query necessario viene trovato nella barra degli indirizzi e non nell'URL del frame corrente:

```js
// take the query string from the parent frame 
 s.eVar1=s.getQueryParam('pid','',f); 
```

Quando utilizzate i frame e il parametro *f* , si consiglia di utilizzare il *`getValOnce`* plug-in per impedire che il codice di tracciamento della campagna venga inviato con ciascuna visualizzazione di pagina.

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

**Codice plug-in**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getQueryParam 2.3 
 */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
 /* Plugin Example: getQueryParam 2.3 
 //single parameter 
 s.campaign=s.getQueryParam('cid'); 
 
 //multiple parameters 
 s.campaign=s.getQueryParam('cid,sid',':'); 
 
 //non-page URL example 
 s.campaign=s.getQueryParam('cid','',document.referrer); 
 
 //parent frame example 
 s.campaign=s.getQueryParam('cid','','f'); 
 
 */ 
 
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
  
 None
```

