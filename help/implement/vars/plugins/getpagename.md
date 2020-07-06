---
title: getPageName
description: Crea un pageName di facile lettura dal percorso del sito Web corrente.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 1%

---


# Plug-in Adobe: getPageName

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getPageName` plug-in crea una versione semplice e intuitiva dell’URL corrente. Adobe consiglia di utilizzare questo plug-in se desiderate un [`pageName`](../page-vars/pagename.md) valore facile da impostare e comprendere nei rapporti. Questo plug-in non è necessario se disponete già di una struttura di denominazione per la `pageName` variabile, ad esempio attraverso un livello dati. È indicato quando non si dispone di un&#39;altra soluzione per impostare la `pageName` variabile.

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
   * Tipo azione: Initialize getPageName
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
/* Adobe Consulting Plugin: getPageName v4.0 */
var getPageName=function(si,qv,hv,de){var c=location.hostname,f=location.pathname.substring(1).split("/"),h=f.length, g=location.search.substring(1).split("&"),l=g.length,k=location.hash.substring(1).split("&"),m=k.length;de=de?de:": ";si=si?si:c;qv= qv?qv:"";hv=hv?hv:"";if(1===h&&""===f[0])si=si+de+"home";else for(c=0;c<h;c++)si=si+de+decodeURIComponent(f[c]); if(qv&&(1!==l||""!== g[0]))for(f=qv.split(","),h=f.length,c=0;c<h;c++)for(qv=0;qv<l;qv++)if(f[c]===g[qv].split("=")[0]){si=si+de+decodeURIComponent(g[qv]);break}if(hv&&(1!==m||""!==k[0]))for(hv=hv.split(","),g=hv.length,c=0;c<g;c++)for(qv=0;qv<m;qv++)if(hv[c]===k[qv].split("=")[0]){si=si+de+decodeURIComponent(k[qv]);break}return si.substring(si.length-de.length)===de?si.substring(0,si.length-de.length):si};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getPageName` metodo utilizza i seguenti argomenti:

* **`si`** (facoltativo, stringa): Un ID inserito all&#39;inizio della stringa che rappresenta l&#39;ID del sito. Questo valore può essere un ID numerico o un nome descrittivo. Se non è impostata, viene impostata automaticamente sul dominio corrente.
* **`qv`** (facoltativo, stringa): Elenco delimitato da virgole di parametri di stringa di query che, se trovati nell’URL, vengono aggiunti alla stringa
* **`hv`** (facoltativo, stringa): Elenco delimitato da virgole di parametri trovati nell’hash dell’URL che, se trovati nell’URL, vengono aggiunti alla stringa
* **`de`** (facoltativo, stringa): Il delimitatore per suddividere singole parti della stringa. Impostazione predefinita di una tubazione (`|`).

Il metodo restituisce una stringa contenente una versione in formato semplice dell&#39;URL. Questa stringa viene in genere assegnata alla `pageName` variabile, ma può essere utilizzata anche in altre variabili.

## Chiamate di esempio

### Esempio n. 1

Se l&#39;URL corrente fosse...

```js
https://mail.google.com/mail/u/0/#inbox
```

...e viene eseguito il codice seguente...

```js
s.pageName = getPageName()
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "mail.google.com|mail|u|0";
```

### Esempio n. 2

Se l&#39;URL corrente fosse...

```js
https://mail.google.com/mail/u/0/#inbox
```

...e viene eseguito il codice seguente...

```js
s.pageName = getPageName("gmail")
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "gmail|mail|u|0";
```

### Esempio n. 3

Se l&#39;URL corrente fosse...

```js
https://www.google.com/
```

...e viene eseguito il codice seguente...

```js
s.pageName = getPageName()
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "www.google.com|home"
```

**Nota**: Quando il codice viene eseguito su un URL che non contiene un percorso, aggiungerà sempre il valore &quot;home&quot; alla fine del valore restituito

### Esempio n. 4

Se l&#39;URL corrente fosse...

```js
https://www.google.com/
```

...e viene eseguito il codice seguente...

```js
s.pageName = getPageName("google","","","|")
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "google|home"
```

### Esempio n. 5

Se l&#39;URL corrente fosse...

```js
https://www.hotelrooms.com/en/booking/room-booking.html?cid=1235#/step2&arrive=2018-05-26&depart=2018-05-27&numGuests=2
```

...e viene eseguito il codice seguente...

```js
s.pageName = getPageName()
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "www.hotelrooms.com|en|booking|room-booking.html"
```

Tuttavia, se invece viene eseguito il codice seguente...

```js
s.pageName = getPageName("hotelrooms","cid","arrive,numGuests",": ")
```

...il valore finale di s.pageName sarà:

```js
s.pageName = "hotelrooms: en: booking: room-booking.html: cid=1235: arrive=2018-05-26: numGuests=2"
```

## Aggiornamento da versioni precedenti

La versione 4.0+ del plug-in getPageName non dipende dall&#39;esistenza dell&#39;oggetto AppMeasurement di Adobe Analytics (ovvero l&#39;oggetto &quot;s&quot;) da eseguire.  Se scegliete di eseguire l&#39;aggiornamento a questa versione, accertatevi di modificare il codice che chiama il plug-in rimuovendo eventuali istanze dell&#39;oggetto &quot;s&quot; dalla chiamata.
Ad esempio, modificare questo valore:

```js
s.pageName = s.getPageName();
```

...in questo:

```js
s.pageName = getPageName();
```

## Cronologia versioni

### 4.1 (17 settembre 2019)

* Il valore del delimitatore predefinito è stato modificato in un carattere di barra verticale (da due punti + spazio).

### 4.0 (22 maggio 2018)

* Rianalisi/riscrittura completa del plug-in
