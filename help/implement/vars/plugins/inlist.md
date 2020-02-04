---
title: inList
description: Verificare se un valore è contenuto in un altro valore delimitato da caratteri.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Plug-in Adobe:inList

> [!IMPORTANT] Questo plug-in è fornito da Adobe Consulting come servizio di cortesia per trarre maggior valore dall&#39;utilizzo di Adobe Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `inList` plug-in consente di verificare se un valore esiste già all&#39;interno di una stringa delimitata o di un oggetto matrice JavaScript. Molti altri plug-in dipendono dal `inList` funzionamento del plug-in. Questo plug-in fornisce un vantaggio distinto rispetto al metodo JavaScript `indexOf()` in cui non corrisponde a stringhe parziali. Ad esempio, se avete utilizzato questo plug-in per verificare la presenza `"event2"`, non corrisponderà a una stringa contenente `"event25"`. Questo plug-in non è necessario se non è necessario verificare la presenza di valori in stringhe o array delimitati o se si desidera utilizzare una propria `indexOf()` logica.

## Installare il plug-in utilizzando l&#39;estensione Adobe Experience Platform Launch

Adobe offre un’estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installare e pubblicare l’ [!UICONTROL Common Analytics Plugins] estensione
1. Per qualsiasi regola di avvio in cui desiderate utilizzare il plug-in, aggiungete un’azione con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Initialize addProductEvar
1. Salvataggio e pubblicazione delle modifiche alla regola

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe Analytics.
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche all&#39;estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo che è stata creata l&#39;istanza dell&#39;oggetto di tracciamento di Analytics (tramite `s_gi`). La conservazione di commenti e numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `inList` metodo utilizza i seguenti argomenti:

* **`lv`**(obbligatorio, stringa o array): Un elenco delimitato di valori o un oggetto matrice JavaScript da cercare
* **`vtc`**(obbligatorio, stringa): Il valore da cercare
* **`d`**(facoltativo, stringa): Il delimitatore utilizzato per separare i singoli valori nell&#39;`lv`argomento. Il valore predefinito è una virgola (`,`) se non è impostato.
* **`cc`**(facoltativo, booleano): Se impostato su`true`, viene effettuato un controllo con distinzione tra maiuscole e minuscole. Se impostato su`false`o omesso, viene effettuato un controllo senza distinzione tra maiuscole e minuscole. Il valore predefinito è`false`.

La chiamata di questo metodo restituisce `true` se trova una corrispondenza e `false` se non trova una corrispondenza.

## Chiamate di esempio

### Esempio n. 1

Se viene mostrato...

```js
s.events="event22,event24";
```

...e viene eseguito il codice seguente...

```js
if(s.inList(s.events,"event22"))
```

...l&#39;istruzione if condizionale sarà true

### Esempio n. 2

Se viene mostrato...

```js
s.events="event22,event24";
```

...e viene eseguito il codice seguente...

```js
if(s.inList(s.events,"event2"))
```

...l&#39;istruzione if condizionale sarà false perché la chiamata inList non ha effettuato una corrispondenza esatta tra event2 e nessuno dei valori delimitati in s.events

### Esempio n. 3

Se viene mostrato...

```js
s.events="event22,event24";
```

...e viene eseguito il codice seguente...

```js
if(!s.inList(s.events,"event23"))
```

...l&#39;istruzione if condizionale sarà true perché la chiamata inList non ha effettuato una corrispondenza esatta tra event23 e nessuno dei valori delimitati in s.events (notate l&#39;operatore &quot;NOT&quot; all&#39;inizio della chiamata alla variabile inList).

### Esempio n. 4

Se viene mostrato...

```js
s.events = "event22,event23";
```

...e viene eseguito il codice seguente...

```js
if(s.inList(s.events,"EVenT23","",1))
```

...l&#39;istruzione if condizionale sarà false.  Anche se questo esempio non è pratico, dimostra la necessità di prestare attenzione quando si utilizza il flag sensibile alle maiuscole/minuscole.

### Esempio n. 5

Se viene mostrato...

```js
s.linkTrackVars = "events,eVar1";
```

...e viene eseguito il codice seguente...

```js
if(s.inList(s.linkTrackVars,"eVar1","|"))
```

...l&#39;istruzione if condizionale sarà false.  Il valore dell&#39;argomento d passato nella chiamata (ovvero &quot;|&quot;) presuppone che i singoli valori in s.linkTrackVars siano delimitati da un carattere di barra verticale, mentre in realtà i valori sono delimitati da una virgola.  In questo caso, il plug-in tenta di effettuare una corrispondenza tra l’intero valore di s.linkTrackVars (ovvero &quot;events,eVar1&quot;) e il valore da cercare (es. &quot;eVar1&quot;).

## Cronologia versioni

### v2.1 (26 settembre 2019)

* Aggiunta l&#39;opzione per evitare che l&#39; `cc` argomento sia un valore booleano. Ad esempio, `1` è un valore case check valido.

### v2.0 (17 aprile 2018)

* Rilascio punto (ricompilato, dimensioni del codice più piccole).

### v1.01 (27 settembre 2017)

* Codice ottimizzato per ridurre le dimensioni

### v1.0 (2009)

* Versione iniziale.


