---
description: Analytics fornisce una serie di variabili per raccogliere i dati di Analytics. Ad esempio, il valore nella variabile pageName corrisponde al nome della pagina Web segnalata. In questa sezione sono elencate le variabili supportate da AppMeasurement.
keywords: Analytics Implementation;appmeasurement variables
solution: Analytics
subtopic: Variables
title: Panoramica delle variabili
topic: Developer and implementation
uuid: 067d0135-572a-4a44-af9e-445d3c4e9271
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Panoramica delle variabili

Analytics fornisce una serie di variabili per raccogliere i dati di Analytics. Ad esempio, il valore nella variabile pageName corrisponde al nome della pagina Web segnalata. In questa sezione sono elencate le variabili supportate da AppMeasurement.

Per ulteriori informazioni sulle variabili di pagina, vedere [qui](/help/implement/js-implementation/c-variables/page-variables.md).
Per ulteriori informazioni sulle variabili di configurazione, consulta [qui](/help/implement/js-implementation/c-variables/configuration-variables.md).

## Come impostare le variabili {#section_E52CF9E8FDF74164A1511E0D9D31884D}

AppMeasurement richiede che tutte le variabili di configurazione siano impostate prima della chiamata iniziale alla funzione track, *`t()`*. Se le variabili di configurazione sono impostate dopo la chiamata a *`t()`*, potrebbero verificarsi risultati imprevisti.

Le variabili di configurazione sono impostate all'interno della *`doPlugins`* funzione, che viene chiamata durante l'esecuzione della funzione track. La specifica variabile di configurazione che causa questo problema è *`trackInlineStats`*, che abilita la raccolta dati ClickMap. Questo lascia il modulo ClickMap in uno stato indeterminato, il che comporta la prima chiamata di tracciamento che aggiunge la stringa "undefined" al beacon di Adobe Analytics, influendo sul codice della valuta.

Per risolvere questo problema, spostare tutte le variabili di configurazione sopra la funzione doPlugins.

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

