---
title: getTimeToComplete
description: Misura il tempo necessario per completare un'attività.
feature: Variables
exl-id: 90a93480-3812-49d4-96f0-8eaf5a70ce3c
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 1%

---

# Plug-in di Adobe: getTimeToComplete

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

La `getTimeToComplete` il plug-in tiene traccia del tempo impiegato dall&#39;utente per completare un processo su un sito. Il &quot;clock&quot; inizia quando il `start` viene chiamata e termina quando `stop` viene chiamata l&#39;azione . Adobe consiglia di utilizzare questo plug-in se sul sito è presente un flusso di lavoro che richiede un po&#39; di tempo per il completamento e desideri sapere quanto tempo impiegano i visitatori per completarlo. Non è necessario utilizzare questo plug-in se il flusso di lavoro sul sito richiede un breve periodo di tempo (meno di 3 secondi) perché la granularità è limitata solo al secondo completo.

## Installare il plug-in utilizzando l’SDK per web o l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installa e pubblica il [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza getTimeToComplete
1. Salva e pubblica le modifiche alla regola.

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
/* Adobe Consulting Plugin: getTimeToComplete v4.0 */
function getTimeToComplete(sos,cn,exp,tp){var f=sos,m=cn,l=exp,e=tp;if("-v"===f)return{plugin:"getTimeToComplete",version:"4.0"};var k=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof k&&(k.contextData.getTimeToComplete="4.0");window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var h="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,h="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,h="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,h="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,h="seconds",d=isNaN(d)?.2:b/d);h=Math.round(c*d/b)/d+" "+h;0===h.indexOf("1 ")&&(h=h.substring(0,h.length-1));return h}};window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var e=window.location.hostname,h=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){h=2<h?h:2;var f=e.lastIndexOf(".");if(0<=f){for(;0<=f&&1<h;)f=e.lastIndexOf(".",f-1),h--;f=0<f?e.substring(f):e}}g=f;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""};f=f?f.toLowerCase():"start";if("stop"===f||"start"===f){m=m?m:"s_gttc";e?e="d"===e?864E5:"h"===e?36E5:"s"===e?1E3:6E4:(l=30,e=6E4);l=isNaN(l)?30:l;l*=e;k=cookieRead(m);e=new Date;if("stop"===f&&k)return l=Math.round((e.getTime()-k)/1E3),cookieWrite(m,"",0),formatTime(l);"start"!==f||k?k&&Number(k)<e.getTime()+18E5&&cookieWrite(m,k,30):(f=String(e.getTime()),e.setTime(e.getTime()+l),cookieWrite(m,f,e))}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `getTimeToComplete` La funzione utilizza i seguenti argomenti:

* **`sos`** (facoltativo, stringa): Imposta su `"start"` quando si desidera avviare il timer. Imposta su `"stop"` quando si desidera arrestare il timer. Predefinito su `"start"`.
* **`cn`** (facoltativo, stringa): Nome del cookie da memorizzare l&#39;ora di inizio. Predefinito su `"s_gttc"`.
* **`exp`** (facoltativo, numero intero): Il numero di giorni di scadenza del cookie (e del timer). Predefinito su `0`, che rappresenta la fine della sessione del browser.

Una chiamata a questa funzione restituisce una stringa contenente il numero di giorni, ore, minuti e/o secondi necessari tra il `"start"` e `"stop"` azione.

## Esempi

```js
// Start the timer when the visitor starts the checkout
if(s.events.indexOf("scCheckout") > -1) getTimeToComplete("start");

// Stop the timer when the visitor makes the purchase and set prop1 to the time difference between stop and start
// Sets prop1 to the amount of time it took to complete the purchase process
if(s.events.indexOf("purchase") > -1) s.prop1 = getTimeToComplete("stop");

// Simultaneously track the time it takes to complete a purchase and to fill out a registration form
// Stores each timer in their own respective cookies so they run independently
if(inList(s.events, "scCheckout")) getTimeToComplete("start", "gttcpurchase");
if(inList(s.events, "purchase")) s.prop1 = getTimeToComplete("start", "gttcpurchase");
if(inList(s.events, "event1")) getTimeToComplete("start", "gttcregister", 7);
if(inList(s.events, "event2")) s.prop2 = getTimeToComplete("stop", "gttcregister", 7);
```

## Cronologia versioni

### 4.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 3.1 (30 settembre 2019)

* È stata aggiunta una logica che richiede un valore di &quot;start&quot; o &quot;stop&quot; nel primo argomento.  Tutti gli altri valori passati impediscono l&#39;esecuzione del plug-in.
* Aggiornato `inList 2.0` plug-in a `inList 2.1`.

### 3.0 (23 agosto 2018)

* È stato aggiornato il `formatTime v1.0` plug-in a `formatTime v1.1`.

### 3.0 (17 aprile 2018)

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).
* Correzioni di bug minori.

### 2.0 giugno 21, 2016)

* È stata eliminata la dipendenza dal `p_fo` plug-in.
* È stata aggiunta la compatibilità con H-code e AppMeasurement.
* È stata aggiunta la registrazione della console.
