---
description: I plug-in JavaScript vengono in genere chiamati dalla funzione doPlugins, che viene eseguita quando la funzione t() viene chiamata nel codice da incollare.
keywords: Analytics Implementation
subtopic: Plug-ins
title: Funzione doPlugins
topic: Developer and implementation
uuid: 367d5550-f8e2-477d-8681-18ae9665d699
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Funzione doPlugins

I plug-in JavaScript vengono in genere chiamati dalla funzione doPlugins, che viene eseguita quando la funzione t() viene chiamata nel codice da incollare.

Di conseguenza, se si imposta una variabile nella `doPlugins` funzione, è possibile sovrascrivere una variabile impostata nella pagina HTML. L'unica volta che la `doPlugins` funzione non viene chiamata è quando la *`usePlugins`* variabile è impostata su `false`.

**Esempio di codice**

La `doPlugins` funzione viene in genere chiamata `s_doPlugins`. Tuttavia, in alcune circostanze (in genere quando più versioni di [!DNL Analytics] codice possono essere visualizzate su una sola pagina), è possibile modificare il nome della `doPlugins` funzione. Se è necessario rinominare la `doPlugins` funzione standard per evitare conflitti, assegnare `doPlugins` il nome corretto alla funzione, come illustrato nell'esempio seguente.

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

**Utilizzo di doPlugins**

Questa funzione consente di assegnare valori predefiniti alle variabili o di ricavare valori dai parametri delle stringhe di query su qualsiasi pagina del sito. L'utilizzo `doPlugins` può essere più semplice che compilare i valori nella pagina HTML, perché è necessario aggiornare solo un file. Le modifiche al file JavaScript non sono sempre immediate. I visitatori del sito spesso utilizzano versioni memorizzate nella cache del file JavaScript. Ciò significa che gli aggiornamenti al file potrebbero non essere applicati a tutti i visitatori per un massimo di un mese dopo la modifica.

Gli esempi seguenti mostrano come utilizzare la `doPlugins` funzione per impostare un valore predefinito per una variabile e ottenere un valore dalla stringa di query.

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

Per verificare se un plug-in è incluso nel file JavaScript e pronto per l'uso, consultare il file [!UICONTROL Plugins Section] di JavaScript. L'esempio seguente mostra l'aspetto della `getQueryParam` funzione nel [!UICONTROL Plugins Section].

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

