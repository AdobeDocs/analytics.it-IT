---
title: formatTime
description: Convertire un numero di secondi in minuti, ore, ecc.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---


# Plug-in Adobe: formatTime

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `formatTime` plug-in consente di prendere un numero qualsiasi di secondi e presentarli in un formato fisso, arrotondati al valore di riferimento desiderato. Adobe consiglia di utilizzare questo plug-in per acquisire un valore temporale in secondi e convertirlo in un formato fisso (ad esempio, minuti, giorni o settimane). Questo plug-in non è necessario se non si desidera inserire valori basati sul secondo intervallo in un formato con arrotondamento temporale.

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
   * Tipo azione: Initialize formatTime
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
/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0, ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `formatTime` metodo utilizza i seguenti argomenti:

* **`ns`** (obbligatorio, numero intero): Il numero di secondi per la conversione o il formato
* **`tf`** (facoltativo, stringa): il tipo di formato per restituire i secondi in; impostazione predefinita: secondi
   * Imposta su `"d"` se si desidera l&#39;ora in giorni (arrotondato al valore di riferimento di 1/4 più vicino per impostazione predefinita)
   * Imposta su `"h"` se desideri il tempo in ore (arrotondato al valore di riferimento di 1/4 ore più vicino per impostazione predefinita)
   * Imposta su `"m"` se desideri il tempo in minuti (arrotondato al valore di riferimento di 1/2 minuti più vicino per impostazione predefinita)
   * Imposta su `"s"` se si desidera ottenere il tempo in secondi (arrotondato per impostazione predefinita a 5 secondi più vicino)
* **`bml`** (facoltativo, numero): Lunghezza dei benchmark di arrotondamento. Impostazione predefinita dei parametri di riferimento elencati nell’ `tf` argomento

Il metodo restituisce il numero di secondi formattati utilizzando l&#39;unità specificata nell&#39; `tf` argomento. Se l&#39; `tf` argomento non è impostato:

* Qualsiasi valore inferiore a un minuto viene arrotondato al valore di riferimento di 5 secondi più vicino
* Qualsiasi valore compreso tra un minuto e un&#39;ora viene arrotondato al valore di riferimento più vicino di 1/2 minuti
* Qualsiasi valore compreso tra un&#39;ora e un giorno viene arrotondato al valore di riferimento del trimestre più vicino
* Qualsiasi valore maggiore di un giorno viene arrotondato al valore di riferimento del giorno più vicino

## Esempi

### Esempio n. 1

Codice seguente...

```js
s.eVar1 = s.formatTime(38242);
```

...imposta s.eVar1 su &quot;10.5 hours&quot;

L&#39;argomento passato - 38242 secondi - è uguale a 10 ore, 37 minuti e 22 secondi.  Poiché l&#39;argomento tf non è impostato in questa chiamata e il numero di secondi trascorsi è compreso tra un&#39;ora e un giorno, il plug-in restituirà il numero di secondi convertiti nel parametro di riferimento di trimestre più vicino.

### Esempio n. 2

Codice seguente...

```js
s.eVar1 = s.formatTime(38250);
```

...imposta s.eVar1 su &quot;10.75 hours&quot; L&#39;argomento passato - 38250 secondi - è uguale a 10 ore, 37 minuti e 30 secondi.  L&#39;arrotondamento del numero di secondi passati al valore di riferimento di trimestre più vicino in questo caso imposterà il valore finale su 10,75 ore

### Esempio n. 3

Codice seguente...

```js
s.eVar1 = s.formatTime(38242, "m");
```

...imposta s.eVar1 su &quot;637.5 minuti&quot;

In questo caso, l&#39;argomento &quot;m&quot; forza il plug-in a convertire i secondi al valore di riferimento di ½ minuto più vicino

### Esempio n. 4

Codice seguente...

```js
s.eVar1 = s.formatTime(38242, "m", 20);
```

...imposta s.eVar1 su &quot;640 minuti&quot;

Il valore dell&#39;argomento tf (&quot;m&quot;) forza il plug-in a convertire i secondi in minuti, ma anche il valore dell&#39;argomento bml (20) forza il plug-in a arrotondare la conversione dei minuti al valore di riferimento di 20 minuti più vicino.

### Esempio n. 5

Codice seguente...

```js
s.eVar1 = s.formatTime(125, "s", 2);
```

...imposta s.eVar1 su &quot;126 secondi&quot;, che è il valore di riferimento più vicino di 2 secondi a 125 secondi

### Esempio n. 6

Codice seguente...

```js
s.eVar1 = s.formatTime(125, "m", 3);
```

...imposta s.eVar1 su &quot;3 Minutes&quot;, che è il valore di riferimento di 3 minuti più vicino a 125 secondi

### Esempio n. 7

Codice seguente...

```js
s.eVar1 = s.formatTime(145, "m", .4);
```

...imposta s.eVar1 su &quot;2,4 minuti&quot;, corrispondente al valore di riferimento di 2/5 minuti più vicino (ad es. Da 0,4 = 2/5) a 145 secondi

## Cronologia versioni

### 1.1 (21 maggio 2018)

* È stato aggiunto l’ `bml` argomento per consentire maggiore flessibilità nell’arrotondamento

### 1.0 (15 aprile 2018)

* Versione iniziale.
