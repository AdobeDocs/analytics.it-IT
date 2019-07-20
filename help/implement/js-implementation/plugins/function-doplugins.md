---
description: I plug-in javascript vengono in genere denominati dalla funzione doplugins, che viene eseguita quando la funzione t () viene chiamata nel Codice da incollare.
keywords: Implementazione di Analytics
seo-description: I plug-in javascript vengono in genere denominati dalla funzione doplugins, che viene eseguita quando la funzione t () viene chiamata nel Codice da incollare.
seo-title: Funzione doplugins
solution: Analytics
subtopic: Plug-in
title: Funzione doplugins
topic: Sviluppatore e implementazione
uuid: 367 d 5550-f 8 e 2-477 d -8681-18 ae 9665 d 699
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Funzione doplugins

I plug-in javascript vengono in genere denominati dalla funzione doplugins, che viene eseguita quando la funzione t () viene chiamata nel Codice da incollare.

Consequently, if you set a variable in the `doPlugins` function, you may overwrite a variable you set on the HTML page. The only time the `doPlugins` function is not called is when the *`usePlugins`* variable is set to `false`.

**Esempio di codice**

The `doPlugins` function is typically called `s_doPlugins`. However, in certain circumstances (usually when more than one version of [!DNL Analytics] code may appear on a single page), you can change the `doPlugins` function name. If the standard `doPlugins` function needs to be renamed to avoid conflicts, assign `doPlugins` the correct function name, as shown in the example below.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function  
<b>s_mc_doPlugins</b>(s_mc) { 
/* Add calls to plugins here */ 
} 
s_mc.doPlugins= 
<b>s_mc_doPlugins</b>
```

**Utilizzo di doplugins**

Questa funzione fornisce un modo semplice per fornire valori predefiniti alle variabili o per prendere valori dai parametri delle stringhe query su qualsiasi pagina del sito. Using `doPlugins` can be easier than populating the values in the HTML page, because only one file must be updated. Le modifiche al file javascript non sono sempre immediate. I visitatori che arrivano sul sito spesso utilizzano le versioni memorizzate nella cache del file javascript. Ciò significa che gli aggiornamenti al file potrebbero non essere applicati a tutti i visitatori fino a un mese dopo la modifica.

The following examples show how you can use the `doPlugins` function to set a default value for a variable and to get a value from the query string.

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
/* Add calls to plugins here */ 
// if prop1 doesn't have a value, set it to "Default Value" 
if(!s.prop1) 
s.prop1="Default Value" 
 
// if campaign doesn't have a value, get cid from the query string 
if(!s.campaign) 
s.campaign=getQueryParam('cid'); 
} 
s.doPlugins=s_doPlugins
```

**Plug-in installati**

To find out whether a plugin is included in your JavaScript file and ready for use, look in the [!UICONTROL Plugins Section] of the JavaScript file. The following example shows what the `getQueryParam` function looks like in the [!UICONTROL Plugins Section].

```js
/************************** PLUGINS SECTION *************************/ 
 
/* You may insert any plugins you wish to use here. */ 
/* 
* Plugin: getQueryParam 1.3 - Return query string parameter values 
*/ 
s.getQueryParam=new Function("qp","d","" 
+"vars=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ... 
// 
```

