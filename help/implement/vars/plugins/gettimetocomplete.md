---
title: getTimeToComplete
description: Misurare il tempo necessario per completare un'attività.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 1%

---


# Plug-in Adobe: getTimeToComplete

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getTimeToComplete` plug-in tiene traccia del tempo impiegato dall&#39;utente per completare un processo in un sito. L&#39;orologio inizia quando l&#39; `start` azione viene chiamata e termina quando l&#39; `stop` azione viene chiamata. Adobe consiglia di utilizzare questo plug-in se sul sito è presente un flusso di lavoro che richiede del tempo per il completamento e desiderate sapere quanto tempo impiegano i visitatori per completarlo. Non è necessario utilizzare questo plug-in se il flusso di lavoro sul sito richiede un breve periodo di tempo (meno di 3 secondi) perché la granularità è limitata solo al secondo completo.

## Installare il plug-in utilizzando l&#39;estensione Lancio del Adobe Experience Platform 

Adobe offre un’estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installare e pubblicare l’ [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo avete già fatto, create una regola con l&#39;etichetta &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (Page Top)
1. Aggiungete un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in Analytics  comuni
   * Tipo azione: Initialize getTimeToComplete
1. Salvate e pubblicate le modifiche alla regola.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe  Analytics.
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche nell’estensione Analytics .

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo che è stata creata un&#39;istanza dell&#39;oggetto di tracciamento Analytics  (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione di commenti e numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeToComplete v3.1 (Requires formatTime and inList plug-ins) */
s.getTimeToComplete=function(sos,cn,exp){sos=sos?sos.toLowerCase():"start";if("stop"===sos||"start"===sos){cn=cn?cn:"s_gttc";exp=exp?exp:0;var s=this,d=s.c_r(cn),e=new Date;if("start"===sos&&!d)s.c_w(cn,e.getTime(),exp?new Date(e.getTime()+864E5*exp):0);else if("stop"===sos&&d)return sos=Math.round((e.getTime()-d)/1E3),s.c_w(cn,"",0),s.formatTime(sos)}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getTimeToComplete` metodo utilizza i seguenti argomenti:

* **`sos`** (facoltativo, stringa): Impostare su `"start"` quando si desidera avviare il timer. Impostare su `"stop"` quando si desidera arrestare il timer. Il valore predefinito è `"start"`.
* **`cn`** (facoltativo, stringa): Nome del cookie in cui memorizzare l&#39;ora di inizio. Il valore predefinito è `"s_gttc"`.
* **`exp`** (facoltativo, numero intero): Il numero di giorni di scadenza del cookie (e del timer). Il valore predefinito è `0`, che rappresenta la fine della sessione del browser.

Se si chiama questo metodo, viene restituita una stringa che contiene il numero di giorni, ore, minuti e/o secondi trascorsi tra l’azione `"start"` e `"stop"` l’azione.

## Chiamate di esempio

### Esempio n. 1

Utilizzate queste chiamate per determinare l&#39;ora tra l&#39;avvio del processo di checkout da parte di un visitatore e la data in cui effettua un acquisto.

Avviate il timer quando il visitatore avvia il checkout:

```js
if(s.events.indexOf("scCheckout") > -1) s.getTimeToComplete("start");
```

Arrestate il timer quando il visitatore effettua l&#39;acquisto e impostate prop1 sulla differenza di tempo tra stop e start:

```js
if(s.events.indexOf("purchase") > -1) s.prop1 = s.getTimeToComplete("stop");
```

s.prop1 acquisirà il tempo necessario per completare il processo di acquisto

### Esempio n. 2

Se si desidera che diversi timer siano in esecuzione contemporaneamente (per misurare diversi processi), sarà necessario impostare manualmente l&#39;argomento cookie cn.  Ad esempio, se desideri misurare il tempo necessario per completare un acquisto, imposta il seguente codice.

```javascript
if(s.inList(s.events, "scCheckout")) s.getTimeToComplete("start", "gttcpurchase");
if(s.inList(s.events, "purchase")) s.prop1 = s.getTimeToComplete("start", "gttcpurchase");
```

...ma se si desidera anche misurare (allo stesso tempo) il tempo necessario per compilare un modulo di registrazione, è necessario eseguire anche il codice seguente:

```js
if(s.inList(s.events, "event1")) s.getTimeToComplete("start", "gttcregister", 7);
if(s.inList(s.events, "event2")) s.prop2 = s.getTimeToComplete("stop", "gttcregister", 7);
```

Nel secondo esempio, event1 è destinato a catturare l&#39;inizio di un processo di registrazione che potrebbe richiedere fino a 7 giorni per essere completato, per qualsiasi motivo, e event2 è destinato a catturare il completamento della registrazione.  s.prop2 acquisirà il tempo necessario per completare il processo di registrazione

## Cronologia versioni

### 3.1 (30 settembre 2019)

* Aggiunta di logica che richiede il valore &quot;start&quot; o &quot;stop&quot; nel primo argomento.  Tutti gli altri valori passati impediscono l&#39;esecuzione del plug-in.
* È stato aggiornato `inList 2.0` il plug-in a `inList 2.1`.

### 3.0 (23 agosto 2018)

* È stato aggiornato il `formatTime v1.0` plug-in in `formatTime v1.1`.

### 3.0 (17 aprile 2018)

* Rilascio punto (ricompilato, dimensioni del codice più piccole).
* Correzioni di bug minori.

### (2.0 giugno 21, 2016)

* È stata eliminata la dipendenza dal `p_fo` plug-in.
* Maggiore compatibilità con H-code e AppMeasurement.
* Aggiunta registrazione console.
