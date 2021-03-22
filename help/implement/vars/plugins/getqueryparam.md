---
title: getQueryParam
description: Estrai il valore del parametro della stringa di query di un URL.
translation-type: tm+mt
source-git-commit: 03c3a954c40d17f11f4f80ee3a378fd43948cc5c
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 1%

---


# Plug-in di Adobe: getQueryParam

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getQueryParam` ti consente di estrarre il valore di qualsiasi parametro della stringa di query contenuto in un URL. È utile per estrarre i codici della campagna, sia interni che esterni, dagli URL della pagina di destinazione. È utile anche per l’estrazione dei termini di ricerca o di altri parametri della stringa di query.

Questo plug-in fornisce solide funzioni per l’analisi di URL complessi, tra cui hash e URL contenenti più parametri di stringa di query. Se hai solo esigenze di parametri di stringa di query semplici, Adobe consiglia di utilizzare le funzionalità dei parametri URL in Launch o il metodo [`Util.getQueryParam()`](../functions/util-getqueryparam.md) incluso in AppMeasurement.

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
   * Tipo azione: Inizializza getQueryParam
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato di Launch

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Espandi il [!UICONTROL Configure tracking using custom code] pannello a soffietto, che mostra il pulsante [!UICONTROL Open Editor] .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0 */
function getQueryParam(b,c,d){function h(b,a){a=a.split("?").join("&");a=a.split("#").join("&");var c=a.indexOf("&");if(b&&(-1<c||a.indexOf("=")>c)){c=a.substring(c+1);c=c.split("&");for(var d=0,k=c.length;d<k;d++){var f=c[d].split("="),e=f[1];if(f[0].toLowerCase()===b.toLowerCase())return decodeURIComponent(e||!0)}}}if("-v"===b)return{plugin:"getQueryParam",version:"4.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getQueryParam="4.0");if(b){c=c||"";d=(d||"undefined"!==typeof a&&a.pageURL||location.href)+"";(4<c.length||-1<c.indexOf("="))&&d&&4>d.length&&(a=c,c=d,d=a);a="";for(var g=b.split(","),l=g.length,e=0;e<l;e++)b=h(g[e],d),"string"===typeof b?(b=-1<b.indexOf("#")?b.substring(0,b.indexOf("#")):b,a+=a?c+b:b):a=""===a?b:a+(c+b);return a}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getQueryParam` utilizza i seguenti argomenti:

* **`qsp`** (obbligatorio): Elenco delimitato da virgole dei parametri della stringa di query da cercare all’interno dell’URL. Non fa distinzione tra maiuscole e minuscole.
* **`de`** (facoltativo): Il delimitatore da utilizzare se più parametri della stringa di query corrispondono. Impostazione predefinita di una stringa vuota.
* **`url`** (facoltativo): Un URL personalizzato, una stringa o una variabile da cui estrarre i valori dei parametri della stringa di query. Predefinito su `window.location`.

Una chiamata a questo metodo restituisce un valore a seconda degli argomenti precedenti e dell&#39;URL:

* Se non viene trovato un parametro della stringa di query corrispondente, il metodo restituisce una stringa vuota.
* Se viene trovato un parametro della stringa di query corrispondente, il metodo restituisce il valore del parametro della stringa di query.
* Se viene trovato un parametro della stringa di query corrispondente ma il valore è vuoto, il metodo restituisce `true`.
* Se vengono trovati più parametri di stringa di query corrispondenti, il metodo restituisce una stringa con ogni valore di parametro delimitato dalla stringa nell&#39;argomento `de` .

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

### Esempio n. 3

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

**Nota:** il plug-in sostituisce l&#39;URL del carattere hash di Check con un punto interrogativo se non esiste un punto interrogativo.  Se l&#39;URL contiene un punto interrogativo che viene prima del carattere hash, il plug-in sostituirà l&#39;URL del carattere hash di Check con una e commerciale;

### Esempio n. 6

Se l&#39;URL corrente è il seguente..

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

* Il valore 123456 proviene dal parametro ecid nella variabile s.testURL
* Il valore di trackingcode1 proviene dal parametro cid nella variabile s.testURL
* Il valore true deriva dall&#39;esistenza (ma non dal valore) del parametro di posizione dopo il carattere hash nella variabile s.testURL

Il valore di 300 deriva dal valore del parametro pos nella variabile s.testURL

## Cronologia versioni

### 4.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.
* Sono state rimosse le dipendenze dal plug-in `pt` .

### 3.3 (24 settembre 2019)

* È stata ignorata una logica non necessaria per ridurre la dimensione del codice

### 3.2 (15 maggio 2018)

* Le funzioni `findParameterValue` e `getParameterValue` sono state spostate nella funzione `getQueryParam`

### 3.1 (10 maggio 2018)

* È stato risolto un problema relativo all’acquisizione di parametri di stringa di query senza valore

### 3.0 (16 aprile 2018)

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).
* Le funzioni helper sono state rinominate in `findParameterValue` e `getParameterValue` a scopo di leggibilità.
* È stata rimossa la necessità di aggiungere un argomento per trovare i parametri contenuti nell’hash dell’URL

### 2.5 (8 gennaio 2016)

* Compatibile sia con H-code che con AppMeasurement (richiede `s.pt` con AppMeasurement).

### 2,4

* È stato aggiunto il parametro `h` , che consente al codice di trovare i parametri della stringa di query trovati dopo il carattere hash (`#`)

### 2.3.

* È stato risolto un problema di regressione a causa del quale il plug-in funzionava solo quando l’hash era presente dopo il codice di tracciamento

### 2.2.

* Rimuove ora i caratteri hash (e tutti gli elementi successivi) dal valore restituito

### 2.1

* Compatibile con il codice H.10
