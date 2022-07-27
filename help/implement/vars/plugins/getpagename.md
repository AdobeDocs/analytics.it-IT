---
title: getPageName
description: Crea un pageName di facile lettura dal percorso del sito Web corrente.
feature: Variables
exl-id: a3aaeb5d-65cd-45c1-88bb-f3c0efaff110
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 1%

---

# Plug-in di Adobe: getPageName

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

La `getPageName` Il plug-in crea una versione formattata semplice e intuitiva dell’URL corrente. Adobe consiglia di utilizzare questo plug-in se desideri [`pageName`](../page-vars/pagename.md) valore facile da impostare e comprendere nel reporting. Questo plug-in non è necessario se disponi già di una struttura di denominazione per `pageName` , ad esempio attraverso un livello dati. Viene utilizzato al meglio quando non si dispone di un&#39;altra soluzione per impostare `pageName` variabile.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize getPageName
1. Save and publish the changes to the rule.-->

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `getPageName` La funzione utilizza i seguenti argomenti:

* **`si`** (facoltativo, stringa): Un ID inserito all&#39;inizio della stringa che rappresenta l&#39;ID del sito. Questo valore può essere un ID numerico o un nome descrittivo. Se non è impostato, viene impostato automaticamente sul dominio corrente.
* **`qv`** (facoltativo, stringa): Elenco delimitato da virgole di parametri della stringa di query che, se trovati nell’URL, vengono aggiunti alla stringa
* **`hv`** (facoltativo, stringa): Elenco di parametri delimitati da virgole trovati nell’hash dell’URL che, se trovato nell’URL, vengono aggiunti alla stringa
* **`de`** (facoltativo, stringa): Il delimitatore per suddividere singole parti della stringa. Impostazione predefinita di una tubazione (`|`).

La funzione restituisce una stringa contenente una versione in formato descrittivo dell&#39;URL. Questa stringa viene generalmente assegnata alla `pageName` , ma può essere utilizzato anche in altre variabili.

## Esempi

```js
// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "mail.example.com|mail|u|0".
s.pageName = getPageName();

// Given the URL https://mail.example.com/mail/u/0/#inbox, sets the page variable to "example|mail|u|0".
s.pageName = getPageName("example");

// Given the URL https://www.example.com/, sets the page variable to "www.example.com|home".
// When the code runs on a URL that does not contain a path, it always adds the value of "home" to the end of the return value.
s.pageName = getPageName();

// Given the URL https://www.example.com/, sets the page variable to "example|home".
s.pageName = getPageName("example","","","|");

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "www.example.com|en|booking|room-booking.html".
s.pageName = getPageName();

// Given the URL https://www.example.com/en/booking/room-booking.html?cid=1235#/step2&arrive=05-26&depart=05-27&numGuests=2
// Sets the page variable to "example: en: booking: room-booking.html: cid=1235: arrive=05-26: numGuests=2"
s.pageName = getPageName("example","cid","arrive,numGuests",": ");
```

## Aggiornamento da versioni precedenti

Versione 4.0+ del `getPageName` il plug-in non dipende dall&#39;esistenza dell&#39;oggetto AppMeasurement di Adobe Analytics (ovvero `s` oggetto). Se esegui l&#39;aggiornamento a questa versione, cambia il codice che chiama il plug-in rimuovendo eventuali istanze del `s` oggetto della chiamata . Ad esempio, modifica `s.getPageName();` a `getPageName();`.

## Cronologia versioni

### 4.2 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 4.1 (17 settembre 2019)

* Il valore del delimitatore predefinito è stato modificato in un carattere di barra verticale (da due punti + spazio).

### 4.0 (22 maggio 2018)

* Rianalisi/riscrittura completa del plug-in
