---
title: manageVars
description: Modifica i valori di più variabili Analytics alla volta.
feature: Appmeasurement Implementation
exl-id: b80d1c43-7e79-443e-84fb-1f1edffca461
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 5%

---

# Plug-in Adobe: manageVars

{{plug-in}}

Il plug-in `manageVars` consente di manipolare i valori di più variabili di Analytics contemporaneamente. Puoi anche impostare i valori in minuscolo o rimuovere contemporaneamente caratteri non necessari da più valori di variabili. Adobe consiglia di utilizzare questo plug-in per pulire il valore di più variabili contemporaneamente.

## Installare il plug-in utilizzando l’estensione Web SDK o Web SDK

Questo plug-in non è ancora supportato per l&#39;utilizzo in Web SDK.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Initialize Plug-ins&quot; (Inizializza plug-in) con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Library Loaded (Page Top)
1. Aggiungi un’azione alla regola precedente con la seguente configurazione:
   * Estensione: Common Analytics Plugins
   * Tipo azione: inizializza manageVars
1. Salva e pubblica le modifiche apportate alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandere il pannello a soffietto [!UICONTROL Configure tracking using custom code], che mostra il pulsante [!UICONTROL Open Editor].
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copiare e incollare il codice seguente in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta Adobe a risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: manageVars v3.0 (Requires AppMeasurement) */
function manageVars(cb,l,il){var g=cb,c=l,d=il;if("-v"===g)return{plugin:"manageVars",version:"3.0"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof f){f.contextData.manageVars="3.0";f.blankVars=function(a){this[a]&&(0>a.indexOf("contextData")?this[a]="":(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]="")))};f.lowerCaseVars=function(a){this[a]&&("events"!==a&&-1===a.indexOf("contextData")?(this[a]=this[a].toString(),0!==this[a].indexOf("D=")&&(this[a]=this[a].toLowerCase())):-1<a.indexOf("contextData")&&(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=this.contextData[a].toString().toLowerCase())))};f.cleanStr=function(a){function b(a){if("string"===typeof a){for(a=a.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g,"'").replace(/\t+/g,"").replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}this[a]&&"function"===typeof b&&(0>a.indexOf("contextData")?this[a]=b(this[a]):(a=a.substring(a.indexOf(".")+1),this.contextData[a]&&(this.contextData[a]=b(this.contextData[a].toString()))))};f.pt=function(a,b,c,d){if(a&&this[c]){a=a.split(b||",");b=a.length;for(var e,f=0;f<b;f++)if(e=this[c](a[f],d))return e}};if(!f[g])return!1;c=c||"";d=d||!0;var b,e="pageName,purchaseID,channel,server,pageType,campaign,state,zip,events,products,transactionID";for(b=1;76>b;b++)e+=",prop"+b;for(b=1;251>b;b++)e+=",eVar"+b;for(b=1;6>b;b++)e+=",hier"+b;for(b=1;4>b;b++)e+=",list"+b;for(b in f.contextData)e+=",contextData."+b;if(c){if(1==d)e=c.replace("['",".").replace("']","");else if(0==d){c=c.split(",");d=e.split(",");e="";for(x in c)for(y in-1<c[x].indexOf("contextData")&&(c[x]="contextData."+c[x].split("'")[1]),d)c[x]===d[y]&&(d[y]="");for(y in d)e+=d[y]?","+d[y]:""}f.pt(e,",",g,0);return!0}return""===c&&d?(f.pt(e,",",g,0),!0):!1}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `manageVars` utilizza i seguenti argomenti:

* **`cb`** (obbligatorio, stringa): nome di una funzione di callback utilizzata dal plug-in per manipolare le variabili di Analytics. È possibile utilizzare una funzione di Adobe come `cleanStr` o una funzione personalizzata.
* **`l`** (facoltativo, stringa): elenco delimitato da virgole di variabili di Analytics che si desidera modificare. Se non viene impostato, viene impostato automaticamente su TUTTE le variabili di Adobe Analytics, tra cui:
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
   * Tutte le variabili elenco
   * Tutte le variabili di dati di contesto
* **`Il`** (facoltativo, booleano): impostare su `false` se si desidera *escludere* l&#39;elenco di variabili dichiarate nell&#39;argomento `l` anziché includerle. Predefinito su `true`.

La chiamata di questa funzione non restituisce alcun risultato. Cambia invece i valori delle variabili di Analytics in base alla funzione di callback desiderata.

## Esempio di chiamate

### Esempio di #1

Il seguente codice...

```js
manageVars("lowerCaseVars");
```

...modifica in minuscolo i valori di tutte le variabili descritte in precedenza.  L’unica eccezione è rappresentata dalla variabile degli eventi, in quanto alcuni degli eventi (ad esempio, scAdd, scCheckout e così via) sono sensibili all’uso di maiuscole e minuscole e non devono essere convertiti in minuscole

### Esempio di #2

Il seguente codice...

```js
manageVars("lowerCaseVars", "events", false);
```

...essenzialmente produce lo stesso risultato del primo esempio, poiché la variabile degli eventi non è in minuscolo per impostazione predefinita.

### Esempio di #3

Il seguente codice...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...cambierà (ad esempio, in minuscolo) solo i valori di eVar1, eVar2, eVar3 ed list2

### Esempio di #4

Il seguente codice...

```js
manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...cambierà (ad es. in minuscolo) i valori di tutte le variabili descritte in precedenza ECCETTO eVar1, eVar2, eVar3 ed list2

### Esempio di #5

Il seguente codice...

```js
manageVars("cleanStr");
```

...modifica i valori di tutte le variabili descritte in precedenza, comprese le variabili di eventi.  In particolare, la funzione di callback cleanStr esegue le seguenti operazioni sul valore di ciascuna variabile:

* Rimuove la codifica HTML
* Rimuove gli spazi vuoti trovati all’inizio e alla fine del valore
* Sostituisce le virgolette singole sinistra/destra con una virgoletta singola diritta (`'`)
* Sostituisce i caratteri di tabulazione, i caratteri di nuova riga e i caratteri di ritorno a capo con spazi
* Sostituisce tutti gli spazi doppi (o tripli, ecc.) con spazi singoli

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.1 (14 gennaio 2019)

* Correzione di bug per i browser Internet Explorer 11.
* Modifiche per `s.cleanStr`, che ora utilizza la funzione regolare `cleanStr`.

### 2.0 (7 maggio 2018)

* Rilascio del punto (inclusa la rianalisi/riscrittura completa del plug-in)
* Aggiunta funzione di callback `cleanStr`
