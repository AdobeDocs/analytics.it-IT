---
title: manageVars
description: Modificate i valori di più  variabile Analytics alla volta.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 1%

---


# Plug-in Adobe: manageVars

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `manageVars` plug-in consente di manipolare i valori di più variabili Analytics  contemporaneamente. È inoltre possibile impostare i valori in lettere minuscole o rimuovere allo stesso tempo i caratteri non necessari da più valori di variabili. Adobe consiglia di utilizzare questo plug-in se si desidera eliminare il valore di più variabili alla volta.

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
   * Tipo azione: Initialize manageVars
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
/* Adobe Consulting Plugin: manageVars v2.1 (Requires pt plug-in and other necessary callback plug-ins) */
s.manageVars=function(cb,l,il){var s=this;if(!s[cb])return!1;l=l||"";il=il||!0;var a,d="pageName,purchaseID,channel,server, pageType,campaign,state,zip,events,products,transactionID";for(a=1;76>a;a++)d+=",prop"+a;for(a=1;251>a;a++)d+=",eVar"+a;for(a=1;6>a;a++)d+=",hier"+a;for(a=1;4>a;a++)d+=",list"+a;for(a in s.contextData)d+=",contextData."+a;if(l){if(1==il)d=l.replace("['", ".").replace("']","");else if(0==il){l=l.split(",");il=d.split(",");d="";for(x in l)for(y in-1<l[x].indexOf("contextData")&& (l[x]="contextData."+l[x].split("'")[1]),il)l[x]===il[y]&&(il[y]="");for(y in il)d+=il[y]?","+il[y]:""}s.pt(d,",",cb,0);return!0} return""===l&&il?(s.pt(d,",",cb,0),!0):!1};

/* Adobe Consulting Plugin: lowerCaseVars for manageVars (Requires manageVars plug-in) */
s.lowerCaseVars=function(v){var s=this;s[v]&&("events"!==v&&-1===v.indexOf("contextData")?(s[v]=s[v].toString(),0!== s[v].indexOf("D=")&&(s[v]=s[v].toLowerCase())):-1<v.indexOf("contextData")&&(v=v.substring(v.indexOf(".")+1),s.contextData[v]&& (s.contextData[v]=s.contextData[v].toString().toLowerCase())))};

/* Adobe Consulting Plugin: cleanStr for manageVars (Requires manageVars and cleanStr plug-ins) */
s.cleanStr=function(v){var s=this;s[v]&&"function"!==typeof cleanStr&&(0>v.indexOf("contextData")?s[v]=cleanStr(s[v]): (v=v.substring(v.indexOf(".")+1),s.contextData[v]&&(s.contextData[v]=cleanStr(s.contextData[v].toString()))))};

/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"").trim().replace(/[\u2018\u2019\u201A]/g, "'").replace(/\t+/g,"").replace(/[\n\r]/g," ");for(;-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};

/* Adobe Consulting Plugin: pt v2.01 */
s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `manageVars` metodo utilizza i seguenti argomenti:

* **`cb`** (obbligatorio, stringa): Nome di una funzione di callback utilizzata dal plug-in per manipolare le variabili Analytics . È possibile utilizzare una funzione Adobe come `cleanStr` o una funzione personalizzata.
* **`l`** (facoltativo, stringa): Elenco delimitato da virgole  variabili Analytics da manipolare. Se non è impostato, il valore predefinito è Tutte le variabili Adobe  Analytics, che include:
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
   * Tutte le variabili dei dati di contesto
* **`Il`** (facoltativo, booleano): Impostare su `false` se si desidera *escludere* l&#39;elenco delle variabili dichiarate nell&#39; `l` argomento invece di includerle. Il valore predefinito è `true`.

Se si chiama questo metodo, non viene restituito alcun valore. ma modifica i valori  variabili Analytics in base alla funzione di callback desiderata.

## Chiamate di esempio

### Esempio n. 1

Codice seguente...

```js
s.manageVars("lowerCaseVars");
```

...modifica i valori di tutte le variabili sopra descritte in versioni minuscole.  L&#39;unica eccezione a questo è la variabile degli eventi, come alcuni degli eventi (ad esempio scAdd, scCheckout, ecc.) sono sensibili alle maiuscole/minuscole e non devono essere minuscole

### Esempio n. 2

Codice seguente...

```js
s.manageVars("lowerCaseVars", "events", false);
```

...genera essenzialmente lo stesso risultato del primo esempio, in quanto la variabile degli eventi non viene ridotta per impostazione predefinita.

### Esempio n. 3

Codice seguente...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2");
```

...cambierà (ad esempio, in lettere minuscole) solo i valori di eVar1, eVar2, eVar3 e list2

### Esempio n. 4

Codice seguente...

```js
s.manageVars("lowerCaseVars", "eVar1,eVar2,eVar3,list2", false);
```

...cambierà (ad es. in lettere minuscole) i valori di tutte le variabili descritte in precedenza ECCEPT per eVar1, eVar2, eVar3 e list2

### Esempio n. 5

Codice seguente...

```js
s.manageVars("cleanStr");
```

...modifica i valori di tutte le variabili descritte in precedenza, incluse quelle relative agli eventi.  In particolare, la funzione di callback cleanStr esegue le seguenti operazioni sul valore di ciascuna variabile:

* Rimuove la codifica HTML
* Rimuove gli spazi bianchi rilevati all&#39;inizio e alla fine del valore
* Sostituisce le virgolette singole sinistre/destre (ad es. &quot;) con una singola quotazione semplice (&#39;)
* Sostituisce caratteri di tabulazione, caratteri di nuova riga e caratteri di ritorno a capo con spazi.
* Sostituisce tutti i valori double (o triple, ecc.) spazi con spazi singoli

## Cronologia versioni

### 2.1 (14 gennaio 2019)

* Correzione dei bug per i browser Internet Explorer 11.
* Modifiche per `s.cleanStr`, che ora utilizza la `cleanStr` funzione regolare.

### 2.0 (7 maggio 2018)

* Rilascio punto (compresa la riscrittura completa del plug-in)
* Funzione `cleanStr` di callback aggiunta
