---
title: getVisitDuration
description: Tieni traccia di quanto tempo un visitatore è stato sul sito finora.
translation-type: tm+mt
source-git-commit: ca8e563118dcc74dfa718bd203db295faf4e9aa6
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 1%

---


# Plug-in di Adobe: getVisitDuration

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getVisitDuration` tiene traccia del tempo in minuti trascorso sul sito fino a quel momento. Adobe consiglia di utilizzare questo plug-in se si desidera tenere traccia del tempo cumulativo sul sito fino a quel momento, o per tenere traccia del tempo necessario per eseguire un&#39;attività. Questo plug-in non tiene traccia del periodo di tempo tra gli eventi; se desideri utilizzare questa funzionalità, utilizza il plug-in [`getTimeBetweenEvents`](gettimebetweenevents.md) .

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
   * Tipo azione: Inizializza getVisitDuration
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
/* Adobe Consulting Plugin: getVisitDuration v2.1 */
function getVisitDuration(){if(arguments&&"-v"===arguments[0])return{plugin:"getVisitDuration",version:"2.1"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getVisitDuration="2.1");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};d=(new Date).getTime();var k=cookieRead("s_dur"),a=0;if(isNaN(k)||18E5<d-k)k=d;a=d-k;cookieWrite("s_dur",k+"",30);if(0===a)return"first hit of visit";a=Math.floor(a/6E4);return 0===a?"less than a minute":1===a?"1 minute":a+" minutes"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getVisitDuration` non utilizza argomenti. Restituisce uno dei seguenti valori:

* `"first hit of visit"`
* `"less than a minute"`
* `"1 minute"`
* `"[x] minutes"` (dove  `[x]` è il numero di minuti trascorsi dall’arrivo del visitatore sul sito)

Questo plug-in crea un cookie di prime parti denominato `"s_dur"`, corrispondente al numero di millisecondi trascorsi dall&#39;arrivo del visitatore sul sito. Il cookie scade dopo 30 minuti di inattività.

## Chiamate di esempio

### Esempio n. 1

Codice seguente...

```js
s.eVar10 = s.getVisitDuration();
```

...imposterà sempre eVar10 uguale al numero di minuti passati da quando il visitatore è atterrato sul sito

### Esempio n. 3

Codice seguente...

```js
if(s.inList(s.events, "purchase")) s.eVar10 = s.getVisitDuration();
```

...utilizza il plug-in inList per verificare se la variabile eventi contiene l&#39;evento di acquisto.  In tal caso, eVar10 verrà impostato come numero di minuti tra l’inizio della visita e l’ora di acquisto del visitatore.

### Esempio n. 2

Codice seguente...

```js
s.prop10 = s.getVisitDuration();
```

...imposta sempre prop10 uguale al numero di minuti passati da quando il visitatore è atterrato sul sito.  Questo sarà utile se prop10 ha abilitato il percorso.  L’aggiunta della metrica &quot;uscite&quot; al rapporto prop10 mostra un rapporto dettagliato &quot;grafico a dispersione&quot; sul tempo impiegato da una visita nei minuti precedenti all’uscita del sito da parte del visitatore.

## Cronologia versioni

### 2.1 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.0 (2 maggio 2018)

* Rilascio a punto (rianalisi/riscrittura completa del plug-in).
