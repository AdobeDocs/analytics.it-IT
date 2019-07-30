---
description: Analytics offre diverse variabili per la raccolta dei dati di Analytics. Ad esempio, il valore nella variabile pagename è il nome della pagina Web segnalata. In questa sezione sono elencate le variabili supportate da appmeasurement.
keywords: Implementazione di Analytics; variabili di misurazione
seo-description: Analytics offre diverse variabili per la raccolta dei dati di Analytics. Ad esempio, il valore nella variabile pagename è il nome della pagina Web segnalata. In questa sezione sono elencate le variabili supportate da appmeasurement.
seo-title: Panoramica delle variabili
solution: Analytics
subtopic: Variabili
title: Panoramica delle variabili
topic: Sviluppatore e implementazione
uuid: 067 d 0135-572 a -4 a 44-af 9 e -445 d 3 c 4 e 9271
translation-type: tm+mt
source-git-commit: 40e9872126114588961a1e84e6be85bb945050a4

---


# Panoramica delle variabili

Analytics offre diverse variabili per la raccolta dei dati di Analytics. Ad esempio, il valore nella variabile pagename è il nome della pagina Web segnalata. In questa sezione sono elencate le variabili supportate da appmeasurement.

For more information on Page Variables, go [here](/help/implement/js-implementation/c-variables/page-variables.md).
For more information on Configuration Variables, go [here](/help/implement/js-implementation/c-variables/configuration-variables.md).

## How to Set Variables {#section_E52CF9E8FDF74164A1511E0D9D31884D}

AppMeasurement requires that all configuration variables be set before the initial call to the track function, *`t()`*. If configuration variables are set after the call to *`t()`*, unexpected results may occur.

Configuration variables are set inside the *`doPlugins`* function, which is called during the execution of the track function. The specific configuration variable causing this issue is *`trackInlineStats`*, which enables ClickMap data collection. Ciò lascia il modulo clickmap in uno stato indeterminato, il che provoca la successiva aggiunta della stringa "undefined" al beacon di Adobe Analytics, che interessa il codice della valuta.

Per risolvere il problema, sposta tutte le variabili di configurazione sopra la funzione doplugins.

```
/************************** CONFIG SECTION **************************/ 
/* Ensure these variables are correct before deploying */ 
var s_account="[INSERT-REPORT-SUITE-ID-HERE]" 
var s=s_gi(s_account) 
s.trackingServer="[INSERT-TRACKING-SERVER-HERE]" 
s.visitorNamespace="[INSERT-VISITOR-NAMESPACE-HERE]" 
s.charSet="ISO-8859-1" 
s.currencyCode="USD" 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" 
s.linkInternalFilters="javascript:,three,two,one,dev16,.,nike" 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.debugTracking=true 
 
s.usePlugins=true; 
function s_doPlugins(s) { 
    //add your custom plugin code here 
} 
s.doPlugins=s_doPlugins; 
 
/* 
============== DO NOT ALTER ANYTHING BELOW THIS LINE ! =============== 
 
AppMeasurement for JavaScript version: 1.5.3 
Copyright 1996-2016 Adobe, Inc. All Rights Reserved 
More info available at https://www.omniture.com 
*/ 
function AppMeasurement(){var a=this;a.version="1.5.3";var k=window;k.s_c_in||(k.s_c_il=[],k.s_c_in=0);a._il=k.s_c_il;a._in=k.s_c_in;a._il[a._in]=a;k.s_c_in++;a._c="s_c";var q=k.AppMeasurement.zb;q||(q=null);var r=k,n,t;try{for(n=r.parent,t=r.location;n&&n.location&&t&&""+n.location!=""+t&&r.location&&""+n.location!=""+r.location&&n.location.host==t.host;)r=n,n=r.parent}catch(u){}a.ob=function(a){try{console.log(a)}catch(b){}};a.za=function(a){return""+parseInt(a)==""+a};a.replace=function(a,b,d){return!a|| 
0>a.indexOf(b)?a:a.split(b).join(d)};a.escape=function(c){var b,d;if(!c)return c;c=encodeURIComponent(c);for(b=0;7>b;b++)d="+~!*()'".substring(b,b+1),0<=c.indexOf(d)&&(c=a.replace(c,d,"%"+d.charCodeAt(0).toString(16).toUpperCase()));return c};a.unescape=function(c){if(!c)return c;c=0<=c.indexOf("+")?a.replace(c,"+"," "):c;try{return decodeURIComponent(c)}catch(b){}return unescape(c)};a.gb=function(){var c=k.location.hostname,b=a.fpCookieDomainPeriods,d;b||(b=a.cookieDomainPeriods);if(c&&!a.cookieDomain&& 
```

