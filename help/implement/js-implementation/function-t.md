---
description: La funzione s.t() compila tutte le variabili definite in quella pagina in una richiesta di immagine e le invia ai nostri server.
keywords: track;Analytics Implementation;page tracking;track page page
seo-description: La funzione s.t() compila tutte le variabili definite in quella pagina in una richiesta di immagine e le invia ai nostri server.
seo-title: 'Funzione s.t(): tracciamento pagina'
solution: Analytics
subtopic: Funzioni
title: 'Funzione s.t(): tracciamento pagina'
topic: Sviluppatore e implementazione
uuid: 67696e46-1e0d-4200-bfad-4217d1023948
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Funzione s.t(): tracciamento pagina

La funzione s.t() compila tutte le variabili definite in quella pagina in una richiesta di immagine e le invia ai nostri server.

## Proprietà della funzione {#section_DB1F3E216DCD4E12AE42BBDCD25B9626}

* La rimozione della [!UICONTROL s.t()] chiamata impedisce il raggiungimento di eventuali dati [!DNL Analytics]. Più [!UICONTROL s.t()] chiamate attivano più richieste di immagini (raddoppiando il traffico segnalato sul sito).

* Se si desidera attivare più di una richiesta di immagine su un singolo caricamento di pagina, è consigliabile utilizzare la [!UICONTROL s.tl()] funzione .
* L'attivazione di questa funzione aumenta sempre [!UICONTROL pageviews]e include sempre la [!UICONTROL s.pageName] variabile.

## Implementazione {#section_F75C7BD4A8954CD5BE066C6B88A4A01C}

Quando si genera il codice all’interno del [!UICONTROL code manager], nella parte inferiore del codice della pagina vengono riportati i seguenti dati:

```js
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" /></noscript> 
```

Ogni riga di codice ha uno scopo specifico:

```js
var s_code=s.t();if(s_code)document.write(s_code)//-->
```

Questa riga di codice è ciò che attiva la funzione Javascript. La [!UICONTROL s_code] variabile e il relativo metodo document.write sono destinati ai browser che non supportano gli oggetti immagine (browser Netscape prima della versione 3 e Internet Explorer prima della versione 4; meno dello 0,5% di tutti gli utenti di Internet).

```js
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img  
src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" />
```

Per ulteriori domande sulla [!UICONTROL s.t()] funzione, contattare l'Account Manager dell'azienda. Possono organizzare una riunione con un consulente di implementazione Adobe, che può fornire assistenza.
