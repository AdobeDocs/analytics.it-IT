---
title: getQueryParam
description: Estrarre il valore del parametro di una stringa di query dell'URL.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 1%

---


# Plug-in Adobe: getQueryParam

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getQueryParam` plug-in consente di estrarre il valore di qualsiasi parametro di stringa di query contenuto in un URL. È utile per estrarre i codici campagna, sia interni che esterni, dagli URL delle pagine di destinazione. È inoltre utile per estrarre i termini di ricerca o altri parametri di stringa di query.

Questo plug-in fornisce funzioni affidabili nell’analisi di URL complessi, inclusi hash e URL contenenti più parametri di stringa di query. Se è necessario solo un parametro di stringa di query semplice, Adobe consiglia di utilizzare le funzionalità dei parametri URL in Launch o il [`Util.getQueryParam()`](../functions/util-getqueryparam.md) metodo incluso in AppMeasurement.

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
   * Tipo azione: Initialize getQueryParam
1. Salvate e pubblicate le modifiche alla regola.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe  Analytics.
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche nell’estensione Analytics .

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v3.3 (Requires pt plug-in) */
s.getQueryParam=function(qsp,de,url){var g=this,e="",k=function(b,de){de=de.split("?").join("&");de=de.split("#").join("&");var d=de.indexOf("&"),url="";b&&(-1<d||de.indexOf("=")>d)&&(d=de.substring(d+1),url=g.pt(d,"&","gpval",b));return url};qsp=qsp.split(",");var l=qsp.length;g.gpval=function(de,b){if(de){var d=de.split("="),url=d[0];d=d[1]?d[1]:!0;if(b.toLowerCase() ==url.toLowerCase())return"boolean"===typeof d?d:this.unescape(d)}return""};de=de?de:"";url=(url?url:g.pageURL?g.pageURL: location.href)+"";if((4<de.length||-1<de.indexOf("="))&&url&&4>url.length){var b=de;de=url;url=b}for(var h=0;h<l;h++)b=k(qsp[h],url) ,"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,e+=e?de+b:b):e=""===e?b:e+(de+b);return e};

/* Adobe Consulting Plugin: pt v2.01 */ 
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getQueryParam` metodo utilizza i seguenti argomenti:

* **`qsp`** (obbligatorio): Elenco delimitato da virgole di parametri di stringa query da cercare all’interno dell’URL. Non fa distinzione tra maiuscole e minuscole.
* **`de`** (facoltativo): Il delimitatore da utilizzare se più parametri di stringa di query corrispondono. Il valore predefinito è una stringa vuota.
* **`url`** (facoltativo): Un URL personalizzato, una stringa o una variabile da cui estrarre i valori dei parametri della stringa di query. Il valore predefinito è `window.location`.

La chiamata di questo metodo restituisce un valore in base agli argomenti di cui sopra e all’URL:

* Se non viene trovato un parametro di stringa di query corrispondente, il metodo restituisce una stringa vuota.
* Se viene trovato un parametro di stringa di query corrispondente, il metodo restituisce il valore del parametro della stringa di query.
* Se viene trovato un parametro di stringa di query corrispondente ma il valore è vuoto, il metodo restituisce `true`.
* Se vengono trovati più parametri di stringa di query corrispondenti, il metodo restituisce una stringa con ogni valore di parametro delimitato dalla stringa nell&#39; `de` argomento.

## Chiamate di esempio

### Esempio n. 1

Se l’URL corrente è il seguente:

```js
http://www.abc123.com/?cid=trackingcode1
```

Il codice seguente imposta s.campaign su &quot;trackingcode1&quot;:

```js
s.campaign=s.getQueryParam('cid');
```

### Esempio n. 2

Se l’URL corrente è il seguente:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

Il codice seguente imposta s.campaign su &quot;trackingcode1:123456&quot;:

```js
s.campaign=s.getQueryParam('cid,ecid',':');
```

### Esempio n. 3

Se l’URL corrente è il seguente:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456
```

Il codice seguente imposta s.campaign su &quot;trackingcode1123456&quot;:

```js
s.campaign=s.getQueryParam('cid,ecid');
```

### Esempio n. 4

Se l’URL corrente è il seguente:

```js
http://www.abc123.com/?cid=trackingcode1&ecid=123456#location
```

Il codice seguente imposta s.campaign su &quot;123456&quot;:

```js
s.campaign=s.getQueryParam('ecid');
```

### Esempio n. 5

Se l’URL corrente è il seguente:

```js
http://www.abc123.com/#location&cid=trackingcode1&ecid=123456
```

Il codice seguente imposta s.campaign su &quot;123456&quot;

```js
s.campaign=s.getQueryParam('ecid');
```

**Nota:** Il plug-in sostituisce l&#39;URL del carattere hash del controllo con un punto interrogativo se non esiste un punto interrogativo.  Se l&#39;URL contiene un punto interrogativo che viene prima del carattere hash, il plug-in sostituirà l&#39;URL del carattere hash di Check con una e commerciale;

### Esempio n. 6

Se l&#39;URL corrente è il seguente...

```js
http://www.abc123.com/
```

...e se la variabile s.testURL è impostata come segue:

```js
s.testURL="http://www.abc123.com/?cid=trackingcode1&ecid=123456#location&pos=300";
```

Il codice seguente non imposta affatto s.campaign:

```js
s.campaign=s.getQueryParam('cid');
```

Tuttavia, il codice seguente imposta s.campaign su &quot;trackingcode1&quot;:

```js
s.campaign=s.getQueryParam('cid','',s.testURL);
```

**Nota:** il terzo parametro può essere qualsiasi stringa/variabile che il codice utilizzerà per cercare di trovare i parametri della stringa di query in

Il codice seguente imposta s.eVar2 su &quot;123456|trackingcode1|true|300&quot;:

```js
s.eVar2=s.getQueryParam('ecid,cid,location,pos','|',s.testURL);
```

* Il valore 123456 deriva dal parametro ecid nella variabile s.testURL
* Il valore di trackingcode1 deriva dal parametro cid nella variabile s.testURL
* Il valore true deriva dall&#39;esistenza (ma non dal valore) del parametro location dopo il carattere hash nella variabile s.testURL

Il valore 300 deriva dal valore del parametro pos nella variabile s.testURL

## Cronologia versioni

### 3.3 (24 settembre 2019)

* Logica non necessaria per ridurre la dimensione del codice

### 3.2 (15 maggio 2018)

* Spostate `findParameterValue` e `getParameterValue` funzioni nella `getQueryParam` funzione

### 3.1 (10 maggio 2018)

* È stato risolto un problema relativo all&#39;acquisizione di parametri di stringa query senza valore

### 3.0 (16 aprile 2018)

* Rilascio punto (ricompilato, dimensioni del codice più piccole).
* Le funzioni helper rinominate a `findParameterValue` e `getParameterValue` a scopo di leggibilità.
* È stata rimossa la necessità di aggiungere un argomento per trovare i parametri contenuti nell&#39;hash dell&#39;URL

### 2.5 (8 gennaio 2016)

* Compatibile sia con H-code che con AppMeasurement (richiede `s.pt` con AppMeasurement).

### 2.4

* Aggiunto il `h` parametro, che consente al codice di trovare i parametri della stringa di query trovati dopo il carattere hash (`#`)

### 2.3

* È stato risolto un problema di regressione per cui il plug-in funzionava solo quando l&#39;hash era presente dopo il codice di tracciamento

### 2.2

* Ora rimuove i caratteri hash (e tutto il resto dopo) dal valore restituito

### 2.1

* Compatibile con il codice H.10
