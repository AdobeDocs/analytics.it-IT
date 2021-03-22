---
title: manageVars
description: Modifica i valori di più di una variabile Analytics alla volta.
translation-type: tm+mt
source-git-commit: 93a2dc1b265c92468722ebc2e3656db55d63547c
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 1%

---


# Plug-in di Adobe: manageVars

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `manageVars` ti consente di manipolare i valori di più variabili di Analytics contemporaneamente. È inoltre possibile impostare i valori in lettere minuscole o rimuovere allo stesso tempo caratteri non necessari da più valori di variabili. Adobe consiglia di utilizzare questo plug-in per pulire il valore di più variabili alla volta.

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
   * Tipo azione: Inizializza manageVars
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
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `manageVars` utilizza i seguenti argomenti:

* **`cb`** (obbligatorio, stringa): Nome di una funzione di callback utilizzata dal plug-in per manipolare le variabili di Analytics. È possibile utilizzare una funzione di Adobe come `cleanStr` o una funzione personalizzata.
* **`l`** (facoltativo, stringa): Elenco delimitato da virgole delle variabili di Analytics da manipolare. Se non è impostato, viene impostata l’impostazione predefinita a TUTTE le variabili Adobe Analytics, che includono:
   * `pageName`
   * `purchaseID`
   * `channel`
   * `server`
   * `pageType`
   * `campaign`
   * `state`
   * `zip`
   * `events`
   * `products`
   * `transactionID`
   * Tutte le proprietà
   * Tutte le eVar
   * Tutte le variabili della gerarchia
   * Tutte le variabili dell’elenco
   * Tutte le variabili di dati di contesto
* **`Il`** (facoltativo, booleano): Imposta su  `false` se desideri  ** escludere l’elenco delle variabili dichiarate nell’ `l` argomento anziché includerle. Predefinito su `true`.

La chiamata di questo metodo non restituisce alcun risultato. Cambia invece i valori delle variabili di Analytics in base alla funzione di callback desiderata.

## Chiamate di esempio

### Esempio n. 1

Codice seguente...

```js
s.manageVars("lowerCaseVars");
```

...cambia i valori di tutte le variabili descritte sopra in versioni minuscole.  L&#39;unica eccezione a questo è la variabile degli eventi, come alcuni degli eventi (ad esempio scAdd, scCheckout, ecc.) sono sensibili all’uso di maiuscole e minuscole e non devono essere minuscole

### Esempio n. 2

Codice seguente...

```js
s.manageVars("lowerCaseVars", "events", false);
```

...essenzialmente produce lo stesso risultato esatto del primo esempio, in quanto la variabile degli eventi non viene ridotta per impostazione predefinita.

### Esempio n. 3

Codice seguente...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...cambierà (ad esempio minuscolo) solo i valori di eVar1, eVar2, eVar3 e list2

### Esempio n. 4

Codice seguente...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...cambierà (ad esempio in minuscolo) i valori di tutte le variabili descritte in precedenza ECCETTO per eVar1, eVar2, eVar3 e list2

### Esempio n. 5

Codice seguente...

```js
s.manageVars("cleanStr");
```

...cambia i valori di tutte le variabili descritte in precedenza, comprese le variabili degli eventi.  In particolare, la funzione di callback cleanStr effettua le seguenti operazioni sul valore di ciascuna variabile:

* Rimuove la codifica HTML
* Rimuove gli spazi bianchi trovati all’inizio e alla fine del valore
* Sostituisce le virgolette singole sinistra/destra (ad es. &quot;) con una quotazione semplice (&quot;)
* Sostituisce caratteri di tabulazione, caratteri di nuova riga e caratteri di ritorno a capo con spazi.
* Sostituisce tutti i valori doppi (o triple, ecc.) spazi con spazi singoli

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.1 (14 gennaio 2019)

* Correzione di bug per i browser Internet Explorer 11.
* Modifiche per `s.cleanStr`, che ora utilizza la normale funzione `cleanStr`.

### 2.0 (7 maggio 2018)

* Rilascio in punti (compresa la reanalisi/riscrittura completa del plug-in)
* È stata aggiunta la funzione di callback `cleanStr`
