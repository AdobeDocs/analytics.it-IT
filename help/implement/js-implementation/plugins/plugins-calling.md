---
description: I plug-in JavaScript vengono in genere chiamati dalla funzione doPlugins, che viene eseguita quando la funzione t() viene chiamata nel codice da incollare.
keywords: Analytics Implementation
solution: Analytics
subtopic: Plug-ins
title: Chiamata dei plug-in con la funzione doPlugins
topic: Developer and implementation
uuid: 95dd01de-8136-4ec9-aac9-4a3d5371b839
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Chiamata dei plug-in con la funzione doPlugins

I plug-in JavaScript vengono in genere chiamati dalla funzione doPlugins, che viene eseguita quando la funzione t() viene chiamata nel codice da incollare.

Di conseguenza, se impostate una variabile nella *`doPlugins`* funzione, potete sovrascrivere una variabile impostata nella pagina HTML. L'unica volta che la *`doPlugins`* funzione non viene chiamata è quando la [!UICONTROL usePlugins] variabile è impostata su 'false'.

## Esempio di codice {#section_6940FD16F2E94753A1C39694D0CF5FBA}

L'esempio di codice riportato di seguito illustra l'aspetto della *`doPlugins`* funzione nel file JavaScript:

AppMeasurement per JavaScript:

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
}
```

Codice H:

```js
/* Plugin Config */ 
s.usePlugins=true 
function s_doPlugins(s) { 
 /* Add calls to plugins here */ 
} 
s.doPlugins=s_doPlugins
```

> [!NOTE] Il codice H e le versioni precedenti utilizzano una sintassi diversa per supportare alcuni browser molto vecchi (come IE 4 e 5).

## Ridenominazione della funzione doPlugins {#section_70B7D58E057B48058E25907AB3726725}

La *`doPlugins`* funzione viene in genere chiamata *`s_doPlugins`*. In alcune circostanze, (in genere quando più versioni di codice possono essere visualizzate su una sola pagina) il nome della *`doPlugins`* funzione può essere modificato. Se è necessario rinominare la *`doPlugins`* funzione standard per evitare conflitti, assicurarsi che *`doPlugins`* sia assegnato il nome corretto, come illustrato nell'esempio seguente.

```js
/* Plugin Config */ 
s_mc.usePlugins=true 
function s_mc_doPlugins(s_mc) { 
 /* Add calls to plugins here */ 
} 
s_mc.doPlugins=s_mc_doPlugins 
```

## Utilizzo di doPlugins {#section_FA5D901CC5214D54BCD08AB77BED7925}

La *`doPlugins`* funzione fornisce un modo semplice per assegnare valori predefiniti alle variabili o per acquisire valori da qualsiasi [!UICONTROL query string parameters] pagina del sito. L'utilizzo *`doPlugins`* è spesso più semplice che compilare i valori nella pagina HTML, perché è necessario aggiornare solo un file. Tenere presente che le modifiche al file JavaScript non sono sempre immediate. I visitatori del sito spesso utilizzano versioni memorizzate nella cache del file JavaScript. Ciò significa che gli aggiornamenti al file potrebbero non essere applicati a tutti i visitatori per un massimo di un mese dopo la modifica.

L'esempio seguente mostra come è possibile utilizzare la *`doPlugins`* funzione per impostare un valore predefinito per una variabile e ottenere un valore dalla stringa di query.

```js
/* Plugin Config */ 
s.usePlugins=true 
s.doPlugins=function(s) { 
 /* Add calls to plugins here */ 
 // if prop1 doesn't have a value, set it to "Default Value" 
 if(!s.prop1) 
s.prop1="Default Value" 
 
 // if campaign doesn't have a value, get cid from the query string 
 if(!s.campaign) 
s.campaign=s.getQueryParam('cid'); 
 
// Note: The code to read query parameters is different for  
// Appmeasurement for JavaScript since a plug-in is not required: 
// s.campaign=s.Util.getQueryParam('cid'); 
} 
```

## Plug-in installati {#section_C5494347D85940A78670032199787CD0}

Per verificare se un plug-in è incluso nel file JavaScript ed è pronto per l'uso, consultare il [!UICONTROL Plugins Section] file JavaScript. L'esempio seguente mostra la [!UICONTROL getQueryParam] funzione.

```js
/************************** PLUGINS SECTION *************************/ 
/* You may insert any plugins you wish to use here.                 */ 
/* 
 * Plugin: getQueryParam 1.3 - Return query string parameter values 
 */ 
s.getQueryParam=new Function("qp","d","" 
+"var s=this,v='',i,t;d=d?d:'';while(qp){i=qp.indexOf(',');i=i<0?qp.l" 
// 
// ... more code below ...
// 
```

