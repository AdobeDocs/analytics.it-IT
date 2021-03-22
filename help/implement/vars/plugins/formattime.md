---
title: formatTime
description: Converti un numero di secondi nel suo equivalente in minuti, ore, ecc.
translation-type: tm+mt
source-git-commit: 56b21b6acb948c478d7b2a29c3e8375a8fe77ce2
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 0%

---


# Plug-in di Adobe: formatTime

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `formatTime` consente di prendere un numero qualsiasi di secondi e di presentarli in un formato a blocchi, arrotondati al valore di riferimento desiderato. Adobe consiglia di utilizzare questo plug-in se desideri acquisire un valore di tempo in secondi e convertirlo in un formato di bucket (ad esempio minuti, giorni o settimane). Questo plug-in non è necessario se non desideri eseguire il bucket di valori basati su secondi in un formato arrotondato al tempo.

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
   * Tipo azione: Inizializza formatTime
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
/* Adobe Consulting Plugin: formatTime v2.0 */
function formatTime(ns,tf,bml){var f=ns,d=tf,e=bml;function h(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(arguments&&"-v"===arguments[0])return{plugin:"formatTime",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.formatTime="2.0");if(!("undefined"===typeof f||isNaN(f)||0>Number(f))){b="";if("string"===typeof d&&"d"===d||("string"!==typeof d||!h("h,m,s",d))&&86400<=f){var c=86400;var g="days";b=isNaN(e)?1:c/(e*c)}else"string"===typeof d&&"h"===d||("string"!==typeof d||!h("m,s",d))&&3600<=f?(c=3600,g="hours",b=isNaN(e)?4:c/(e*c)):"string"===typeof d&&"m"===d||("string"!==typeof d||!h("s",d))&&60<=f?(c=60,g="minutes",b=isNaN(e)?2:c/(e*c)):(c=1,g="seconds",b=isNaN(e)?.2:c/e);b=Math.round(f*b/c)/b+" "+g;0===b.indexOf("1 ")&&(b=b.substring(0,b.length-1));return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `formatTime` utilizza i seguenti argomenti:

* **`ns`** (obbligatorio, numero intero): Il numero di secondi di conversione o di formattazione
* **`tf`** (facoltativo, stringa): il tipo di formato in cui restituire i secondi in; impostazioni predefinite in secondi
   * Imposta su `"d"` se desideri che il tempo in giorni (arrotondato al valore di riferimento di 1/4 giorni più vicino per impostazione predefinita)
   * Imposta su `"h"` se desideri che il tempo sia espresso in ore (arrotondato per impostazione predefinita al valore di riferimento di 1/4 ore più vicino)
   * Imposta su `"m"` se desideri che il tempo in minuti (arrotondato al valore di riferimento di 1/2 minuti più vicino per impostazione predefinita)
   * Imposta su `"s"` se desideri il tempo in secondi (arrotondato per impostazione predefinita al valore di riferimento di 5 secondi più vicino)
* **`bml`** (facoltativo, numero): Lunghezza dei parametri di arrotondamento. Valori predefiniti per i benchmark elencati nell&#39;argomento `tf`

Il metodo restituisce il numero di secondi formattati utilizzando l&#39;unità specificata nell&#39;argomento `tf`. Se l&#39;argomento `tf` non è impostato:

* Qualsiasi valore inferiore a un minuto viene arrotondato al valore di riferimento più vicino di 5 secondi
* Qualsiasi valore compreso tra un minuto e un&#39;ora viene arrotondato al valore di riferimento più vicino di 1/2 minuti
* Qualsiasi valore compreso tra un&#39;ora e un giorno viene arrotondato al valore di riferimento di trimestre più vicino
* Qualsiasi valore maggiore di un giorno viene arrotondato al valore di riferimento del giorno più vicino

## Esempi

### Esempio n. 1

Codice seguente...

```js
s.eVar1 = s.formatTime(38242);
```

...imposta s.eVar1 su &quot;10.5 ore&quot;

L&#39;argomento trasmesso in - 38242 secondi - è uguale a 10 ore, 37 minuti e 22 secondi.  Poiché l’argomento tf non è impostato in questa chiamata e il numero di secondi trascorsi è compreso tra un’ora e un giorno, il plug-in restituirà il numero di secondi convertiti al valore di riferimento di trimestre più vicino.

### Esempio n. 2

Codice seguente...

```js
s.eVar1 = s.formatTime(38250);
```

...imposta s.eVar1 su &quot;10.75 ore&quot;
L&#39;argomento trasmesso in - 38250 secondi - è uguale a 10 ore, 37 minuti e 30 secondi.  Arrotondando il numero di secondi passati al valore di riferimento di trimestre più vicino in questo caso, imposta il valore finale a 10,75 ore

### Esempio n. 2

Codice seguente...

```js
s.eVar1 = s.formatTime(38242, "m");
```

...imposta s.eVar1 su &quot;637,5 minuti&quot;

In questo caso, l&#39;argomento &quot;m&quot; costringe il plug-in a convertire i secondi al valore di riferimento di ½ minuto più vicino

### Esempio n. 4

Codice seguente...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...imposta s.eVar1 su &quot;640 minuti&quot;

Il valore dell&#39;argomento tf (&quot;m&quot;) forza il plug-in a convertire i secondi in minuti, ma anche il valore dell&#39;argomento bml (20) forza il plug-in a arrotondare la conversione dei minuti al valore di riferimento più vicino di 20 minuti.

### Esempio n. 5

Codice seguente...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...imposta s.eVar1 su &quot;126 secondi&quot;, che è il valore di riferimento più vicino a 2 secondi a 125 secondi

### Esempio n. 6

Codice seguente...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...imposta s.eVar1 su &quot;3 minutes&quot;, che è il valore di riferimento di 3 minuti più vicino a 125 secondi

### Esempio n. 7

Codice seguente...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...imposta s.eVar1 su &quot;2,4 minuti&quot;, corrispondente al valore di riferimento più vicino di 2/5 minuti (ad es. da 0,4 = 2/5) a 145 secondi

## Cronologia versioni

### 2.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 1.1 (21 maggio 2018)

* È stato aggiunto l’argomento `bml` per consentire una maggiore flessibilità nell’arrotondamento.

### 1.0 (15 aprile 2018)

* Versione iniziale.
