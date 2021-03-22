---
title: getAndPersistValue
description: Memorizza un valore che può essere recuperato in un secondo momento.
translation-type: tm+mt
source-git-commit: a2970e05abf0d1f963175db6e3554aa0e3034a70
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 1%

---


# Plug-in di Adobe: getAndPersistValue

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getAndPersistValue` ti consente di memorizzare un valore in un cookie che può essere recuperato in un secondo momento durante una visita. Assicura un ruolo simile alla funzione [!UICONTROL Storage duration] in Adobe Experience Platform Launch. Adobe consiglia di utilizzare questo plug-in se desideri mantenere automaticamente una variabile Analytics sullo stesso valore negli hit successivi dopo che la variabile è stata impostata. Questo plug-in non è necessario se la funzione di Launch [!UICONTROL Storage duration] è sufficiente o se non è necessario impostare e mantenere le variabili sullo stesso valore negli hit successivi. La persistenza incorporata degli eVar non richiede l&#39;utilizzo di questo plug-in, in quanto queste variabili persistono lato server per Adobe.

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
   * Tipo azione: Inizializza getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getAndPersist` utilizza i seguenti argomenti:

* **`vtp`** (obbligatorio): Valore da persistere da pagina a pagina
* **`cn`** (facoltativo): Nome del cookie da cui memorizzare il valore. Se questo argomento non è impostato, il cookie è denominato `"s_gapv"`
* **`ex`** (facoltativo): Il numero di giorni prima della scadenza del cookie. Se questo argomento è `0` o non è impostato, il cookie scade alla fine della visita (30 minuti di inattività).

Se la variabile nell&#39;argomento `vtp` è impostata, il plug-in imposta il cookie e restituisce il valore del cookie. Se la variabile nell&#39;argomento `vtp` non è impostata, il plug-in restituisce solo il valore del cookie.

## Esempi

### Esempio n. 1

Il codice seguente imposta eVar21 uguale al valore di &quot;hello&quot;.  Il codice imposta quindi il cookie ev21gapv, che scadrà tra 28 giorni, pari al valore di eVar21 (cioè &quot;hello&quot;).  Il codice imposterà quindi (ri)eVar21 uguale al valore del cookie ev21gapv.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Esempio n. 2

Supponiamo che eVar21 non sia ancora stato impostato sulla pagina corrente ma sia stato impostato su &quot;hello&quot; in una pagina precedente negli ultimi 28 giorni.   Il codice seguente imposta solo eVar21 uguale al valore del cookie ev21gapv (cioè &quot;hello&quot;).  Non reimposta il cookie ev21gapv perché eVar21 non è stato impostato sulla pagina corrente prima della chiamata della funzione.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Esempio n. 3

Supponiamo che eVar21 non sia ancora stato impostato sulla pagina corrente ma sia stato impostato su &quot;hello&quot; in una pagina precedente negli ultimi 28 giorni.  Il codice seguente imposta solo prop35 uguale al valore del cookie ev21gapv (cioè &quot;hello&quot;).  Non verrà impostato eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Esempio n. 4

Il codice seguente imposta eVar21 uguale al valore di &quot;howdy&quot;.  Il codice imposta quindi (o reimposta) il cookie ev21gapv, che scadrà tra 28 giorni, pari al valore di eVar21 (cioè &quot;howdy&quot;).  Il codice imposta quindi prop35 come valore del cookie ev21gapv (cioè &quot;howdy&quot;).

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Esempio n. 5

Supponiamo che s.eVar21 non sia stato impostato su alcuna pagina negli ultimi 28 giorni.  Il codice seguente imposta s.eVar21 come nulla poiché il cookie ev21gapv sarebbe scaduto 28 giorni dopo l’ultima impostazione.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Esempio n. 6

Il codice seguente imposta eVar30 come &quot;shopping&quot;.  Imposta quindi il cookie s_gapv, che scade alla fine della sessione del browser, pari al valore di s.eVar30 (cioè &quot;shopping&quot;).  Imposta quindi s.eVar30 uguale al valore del cookie s_gapv (ovvero la chiamata getAndPersistValue restituisce il valore del cookie s_gapv, che in questo caso è &quot;shopping&quot;).

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

Se s.eVar30 non è impostato su un valore esplicito su qualsiasi pagina aggiuntiva visualizzata durante la sessione ma viene impostata (in doPlugins) tramite il seguente codice..

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30 sarà impostato su &quot;shopping&quot; (ovvero il valore persistente del cookie s_gapv)

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.0 (16 aprile 2018)

* Versione punto (dimensioni del codice più piccole)
* Il passaggio di 0 nell’argomento `ex` ora forza la scadenza dopo 30 minuti di inattività invece della scadenza alla fine della sessione del browser.

### 1.0 (18 gennaio 2016)

* Versione iniziale.
