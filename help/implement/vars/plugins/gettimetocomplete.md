---
title: getTimeToComplete
description: Misura il tempo necessario per completare un'attività.
translation-type: tm+mt
source-git-commit: 37a3a44053260d9cdb2a3797e07f6d34592abc1f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 1%

---


# Plug-in di Adobe: getTimeToComplete

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getTimeToComplete` tiene traccia del tempo impiegato dall&#39;utente per completare un processo su un sito. L&#39;orologio inizia quando viene chiamata l&#39;azione `start` e termina quando viene chiamata l&#39;azione `stop` . Adobe consiglia di utilizzare questo plug-in se sul sito è presente un flusso di lavoro che richiede un po&#39; di tempo per il completamento e desideri sapere quanto tempo impiegano i visitatori per completarlo. Non è necessario utilizzare questo plug-in se il flusso di lavoro sul sito richiede un breve periodo di tempo (meno di 3 secondi) perché la granularità è limitata solo al secondo completo.

## Installare il plug-in utilizzando l’estensione Adobe Experience Platform Launch

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza getTimeToComplete
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato di Launch

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Espandi il [!UICONTROL Configure tracking using custom code] pannello a soffietto, che mostra il pulsante [!UICONTROL Open Editor] .
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

Il metodo `getTimeToComplete` utilizza i seguenti argomenti:

* **`sos`** (facoltativo, stringa): Impostare su  `"start"` quando si desidera avviare il timer. Impostare su `"stop"` per arrestare il timer. Predefinito su `"start"`.
* **`cn`** (facoltativo, stringa): Nome del cookie da memorizzare l&#39;ora di inizio. Predefinito su `"s_gttc"`.
* **`exp`** (facoltativo, numero intero): Il numero di giorni di scadenza del cookie (e del timer). Il valore predefinito è `0`, che rappresenta la fine della sessione del browser.

Una chiamata a questo metodo restituisce una stringa contenente il numero di giorni, ore, minuti e/o secondi necessari tra l&#39;azione `"start"` e `"stop"`.

## Chiamate di esempio

### Esempio n. 1

Utilizza queste chiamate per determinare l&#39;intervallo di tempo tra l&#39;avvio del processo di pagamento da parte di un visitatore e il momento in cui effettua un acquisto.

Avvia il timer quando il visitatore avvia il pagamento:

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Arresta il timer quando il visitatore effettua l’acquisto e imposta prop1 sulla differenza di tempo tra stop e start:

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 acquisirà il tempo necessario per completare il processo di acquisto

### Esempio n. 2

Se desideri che siano in esecuzione più timer contemporaneamente (per misurare processi diversi), dovrai impostare manualmente l’argomento cookie cn.  Ad esempio, se desideri misurare il tempo necessario per il completamento di un acquisto, imposta il seguente codice..

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...ma se desideri anche misurare (allo stesso tempo) il tempo necessario per compilare un modulo di registrazione, esegui anche il seguente codice:

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

Nel secondo esempio, event1 è destinato a catturare l&#39;inizio di un processo di registrazione che potrebbe richiedere fino a 7 giorni per essere completato, per qualsiasi motivo, e event2 è destinato a catturare il completamento della registrazione.  s.prop2 acquisirà il tempo necessario per completare il processo di registrazione

## Cronologia versioni

### 4.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 3.1 (30 settembre 2019)

* È stata aggiunta una logica che richiede un valore di &quot;start&quot; o &quot;stop&quot; nel primo argomento.  Tutti gli altri valori passati impediscono l&#39;esecuzione del plug-in.
* Il plug-in `inList 2.0` è stato aggiornato a `inList 2.1`.

### 3.0 (23 agosto 2018)

* È stato aggiornato il plug-in `formatTime v1.0` in `formatTime v1.1`.

### 3.0 (17 aprile 2018)

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).
* Correzioni di bug minori.

### 2.0 giugno 21, 2016)

* È stata eliminata la dipendenza dal plug-in `p_fo` .
* È stata aggiunta la compatibilità con H-code e AppMeasurement.
* È stata aggiunta la registrazione della console.
