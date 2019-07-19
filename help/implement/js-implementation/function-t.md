---
description: La funzione s. t () consente di compilare tutte le variabili definite sulla pagina in una richiesta di immagine e di inviarle ai nostri server.
keywords: track; Implementazione di Analytics; tracciamento pagina; pagina di tracciamento
seo-description: La funzione s. t () consente di compilare tutte le variabili definite sulla pagina in una richiesta di immagine e di inviarle ai nostri server.
seo-title: Funzione s. t () - Tracciamento pagina
solution: Analytics
subtopic: Funzioni
title: Funzione s. t () - Tracciamento pagina
topic: Sviluppatore e implementazione
uuid: 67696 e 46-1 e 0 d -4200-bfad -4217 d 1023948
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Funzione s. t () - Tracciamento pagina

La funzione s. t () consente di compilare tutte le variabili definite sulla pagina in una richiesta di immagine e di inviarle ai nostri server.

## Properties of the Function {#section_DB1F3E216DCD4E12AE42BBDCD25B9626}

* Removing the [!UICONTROL s.t()] call prevents any data from reaching [!DNL Analytics]. Multiple [!UICONTROL s.t()] calls fires multiple image requests (doubling the reported traffic on your site).

* If you wish to fire more than one image request on a single page load, using the [!UICONTROL s.tl()] function is recommended.
* Triggering this function always increases [!UICONTROL pageviews]and always include the [!UICONTROL s.pageName] variable.

## Implementazione {#section_F75C7BD4A8954CD5BE066C6B88A4A01C}

Upon generating code within the [!UICONTROL code manager], you are given the following at the bottom of the page code:

```js
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" /></noscript> 
```

Ogni riga di codice ha uno scopo specifico:

```js
var s_code=s.t();if(s_code)document.write(s_code)//-->
```

Questa riga di codice corrisponde all'attivazione della funzione Javascript. The [!UICONTROL s_code] variable and it's accompanying document.write method is for browsers that don't support image objects (Netscape browsers prior to version 3 and Internet Explorer prior to version 4; estimated less than .5% of all internet users).

```js
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img  
src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" />
```

For any additional questions about the [!UICONTROL s.t()] function, contact your organization's Account Manager. Possono organizzare una riunione con un consulente di implementazione Adobe, che può fornire assistenza.
