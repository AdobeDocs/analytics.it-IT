---
description: Questa sezione contiene il codice di esempio per il file JavaScript di base e le pagine del sito.
keywords: Implementazione di Analytics;codice appmeasurement.js;codice di pagina di esempio
seo-description: Questa sezione contiene il codice di esempio per il file JavaScript di base e le pagine del sito.
seo-title: Esempio di codice della pagina e configurazione globale
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Esempio di codice della pagina e configurazione globale
topic: Sviluppatore e implementazione
uuid: e8880d77-172b-42e5-8187-ce371aa9eff9
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Esempio di codice della pagina e configurazione globale

Questa sezione contiene il codice di esempio per il file JavaScript di base e le pagine del sito.

>[!IMPORTANT]
>
>In questo esempio viene utilizzato il servizio ID visitatore, distribuito come parte dell’implementazione [](/help/implement/js-implementation/javascript-implementation-overview.md)JavaScript. Se si abilita il servizio ID visitatore in AppMeasurement prima di includere il file JavaScript API del visitatore in tutte le pagine del sito, potrebbero verificarsi dei conteggi dei visitatori duplicati. Per evitare conteggi duplicati dei visitatori, assicurati di comprendere e seguire il processo descritto in Servizio [ID](/help/implement/js-implementation/c-unique-visitors/visid-service.md)visitatori.

## Esempio di codice AppMeasurement.js {#section_4351543F2D6049218E18B48769D471E2}

>[!IMPORTANT]
>
>Le variabili di configurazione devono essere impostate sopra la *`doPlugins`* funzione.

Per le nuove implementazioni, puoi incollare il seguente codice di configurazione globale all’inizio di AppMeasurement.js per iniziare:

```js
//initialize AppMeasurement 
var s_account="INSERT-RSID-HERE" 
var s=s_gi(s_account) 
 
/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/ 
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE") 
 
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
 
/* uncomment below to use doPlugins */ 
/* s.usePlugins=true 
function s_doPlugins(s) { 
 
// use implementation plug-ins that are defined below 
// in this section. For example, if you copied the append 
// list plug-in code below, you could call: 
// s.events=s.apl(s.events,"event1",",",1); 
 
} 
s.doPlugins=s_doPlugins */ 
 
/* WARNING: Changing any of the below variables will cause drastic 
changes to how your visitor data is collected.  Changes should only be 
made when instructed to do so by your account manager.*/ 
s.trackingServer="INSERT-TRACKING-SERVER-HERE" 
s.trackingServerSecure="INSERT-SECURE-TRACKING-SERVER-HERE" 
 
/************************** PLUGINS SECTION *************************/ 
 
// copy and paste implementation plug-ins here - See "Implementation Plug-ins" @ 
// https://marketing.adobe.com/resources/help/en_US/sc/implement/#Implementation_Plugins 
// Plug-ins can then be used in the s_doPlugins(s) function above  
 
/****************************** MODULES *****************************/ 
 
// copy and paste implementation modules (Media, Integrate) here 
// AppMeasurement_Module_Media.js - Media Module, included in AppMeasurement zip 
// AppMeasurement_Module_Integrate.js - Integrate Module, included in AppMeasurement zip 
 
/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  
```

## Esempio di codice della pagina {#section_042412C29CC249E298F19B2BC2F43CE7}

Per le nuove implementazioni, puoi incollare il seguente codice di pagina subito dopo l’apertura <body> tag sulle pagine da monitorare:

```js
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
var s_code=s.t();if(s_code)document.write(s_code)//--></script>
```

Accertatevi di aver incluso anche un riferimento a `AppMeasurement.js` e `VisitorAPI.js` su ciascuna pagina. Per istruzioni, consultate Implementazione [](/help/implement/js-implementation/javascript-implementation-overview.md) JavaScript.
