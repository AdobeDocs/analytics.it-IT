---
title: getPageName
description: Crea un pageName di facile lettura dal percorso del sito Web corrente.
translation-type: tm+mt
source-git-commit: 063da38c105072944a46ec0ab31930623b7974c8
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 1%

---


# Plug-in di Adobe: getPageName

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getPageName` crea una versione formattata semplice e intuitiva dell’URL corrente. Adobe consiglia di utilizzare questo plug-in se desideri un valore [`pageName`](../page-vars/pagename.md) facile da impostare e comprendere nei rapporti. Questo plug-in non è necessario se disponi già di una struttura di denominazione per la variabile `pageName` , ad esempio tramite un livello di dati. Viene utilizzato al meglio quando non hai un&#39;altra soluzione per impostare la variabile `pageName`.

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
   * Tipo azione: Inizializza getPageName
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
/* Adobe Consulting Plugin: getPageName v4.2 */
var getPageName=function(si,qv,hv,de){var a=si,b=qv,f=hv,e=de;if("-v"===a)return{plugin:"getPageName",version:"4.2"};a:{if("undefined"!==typeof window.s_c_il){var d=0;for(var g;d<window.s_c_il.length;d++)if(g=window.s_c_il[d],g._c&&"s_c"===g._c){d=g;break a}}d=void 0}"undefined"!==typeof d&&(d.contextData.getPageName="4.2");var c=location.hostname,h=location.pathname.substring(1).split("/"),l=h.length,k=location.search.substring(1).split("&"),m=k.length;d=location.hash.substring(1).split("&");g=d.length;e=e?e:"|";a=a?a:c;b=b?b:"";f=f?f:"";if(1===l&&""===h[0])a=a+e+"home";else for(c=0;c<l;c++)a=a+e+decodeURIComponent(h[c]);if(b&&(1!==m||""!==k[0]))for(h=b.split(","),l=h.length,c=0;c<l;c++)for(b=0;b<m;b++)if(h[c]===k[b].split("=")[0]){a=a+e+decodeURIComponent(k[b]);break}if(f&&(1!==g||""!==d[0]))for(f=f.split(","),k=f.length,c=0;c<k;c++)for(b=0;b<g;b++)if(f[c]===d[b].split("=")[0]){a=a+e+decodeURIComponent(d[b]);break}return a.substring(a.length-e.length)===e?a.substring(0,a.length-e.length):a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getPageName` utilizza i seguenti argomenti:

* **`si`** (facoltativo, stringa): Un ID inserito all&#39;inizio della stringa che rappresenta l&#39;ID del sito. Questo valore può essere un ID numerico o un nome descrittivo. Se non è impostato, viene impostato automaticamente sul dominio corrente.
* **`qv`** (facoltativo, stringa): Elenco delimitato da virgole di parametri della stringa di query che, se trovati nell’URL, vengono aggiunti alla stringa
* **`hv`** (facoltativo, stringa): Elenco di parametri delimitati da virgole trovati nell’hash dell’URL che, se trovato nell’URL, vengono aggiunti alla stringa
* **`de`** (facoltativo, stringa): Il delimitatore per suddividere singole parti della stringa. Impostazione predefinita di una tubazione (`|`).

Il metodo restituisce una stringa contenente una versione in formato descrittivo dell&#39;URL. Questa stringa viene generalmente assegnata alla variabile `pageName` , ma può essere utilizzata anche in altre variabili.

## Chiamate di esempio

### Esempio n. 1

Se l&#39;URL corrente era..

```js
https://mail.google.com/mail/u/0/#inbox
```

...e viene eseguito il seguente codice...

```js
s.pageName = getPageName()
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "mail.google.com|mail|u|0";
```

### Esempio n. 3

Se l&#39;URL corrente era..

```js
https://mail.google.com/mail/u/0/#inbox
```

...e viene eseguito il seguente codice...

```js
s.pageName = getPageName("gmail")
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "gmail|mail|u|0";
```

### Esempio n. 2

Se l&#39;URL corrente era..

```js
https://www.google.com/
```

...e viene eseguito il seguente codice...

```js
s.pageName = getPageName()
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "www.google.com|home"
```

**Nota**: Quando il codice viene eseguito su un URL che non contiene un percorso, aggiungerà sempre il valore di &quot;home&quot; alla fine del valore restituito

### Esempio n. 4

Se l&#39;URL corrente era..

```js
https://www.google.com/
```

...e viene eseguito il seguente codice...

```js
s.pageName = getPageName("google","","","|")
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "google|home"
```

### Esempio n. 5

Se l&#39;URL corrente era..

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...e viene eseguito il seguente codice...

```js
s.pageName = getPageName()
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

Tuttavia, se viene eseguito il codice seguente...

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## Aggiornamento da versioni precedenti

La versione 4.0+ del plug-in getPageName non dipende dall’esistenza dell’oggetto AppMeasurement di Adobe Analytics (cioè l’oggetto &quot;s&quot;) da eseguire.  Se scegli di eseguire l’aggiornamento a questa versione, assicurati di modificare il codice che chiama il plug-in rimuovendo eventuali istanze dell’oggetto &quot;s&quot; dalla chiamata.
Ad esempio, modificare quanto segue:

```js
s.pageName = s.getPageName();
```

...in questo:

```js
s.pageName = getPageName();
```

## Cronologia versioni

### 4.2 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 4.1 (17 settembre 2019)

* Il valore del delimitatore predefinito è stato modificato in un carattere di barra verticale (da due punti + spazio).

### 4.0 (22 maggio 2018)

* Rianalisi/riscrittura completa del plug-in
