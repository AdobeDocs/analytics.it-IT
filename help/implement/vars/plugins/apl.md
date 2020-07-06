---
title: apl (appendToList)
description: Aggiungere valori alle variabili che supportano più valori.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 1%

---


# Plug-in Adobe: apl (appendToList)

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `apl` plug-in consente di aggiungere in modo sicuro nuovi valori a variabili delimitate da elenchi, come [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md)e altri.

* Se il valore che si desidera aggiungere non esiste nella variabile, il codice aggiunge il valore alla fine della stringa.
* Se il valore che si desidera aggiungere esiste già nella variabile, questo plug-in non modifica il valore. Questa funzione consente all’implementazione di evitare valori duplicati.
* Se la variabile a cui si desidera aggiungere è vuota, il plug-in imposta la variabile sul nuovo valore.

Adobe consiglia di utilizzare questo plug-in se si desidera aggiungere nuovi valori alle variabili esistenti che contengono una stringa di valori delimitati. Questo plug-in non è necessario se si preferisce concatenare stringhe per variabili contenenti valori delimitati.

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
   * Tipo azione: Inizializza APL (Aggiungi A Elenco)
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
/* Adobe Consulting Plugin: apl (appendToList) v3.2 (Requires inList v2.0 or higher) */
s.apl=function(lv,vta,d1,d2,cc){if(!lv||"string"===typeof lv){if("undefined"===typeof this.inList||"string"!==typeof vta||""===vta)return lv;d1=d1||",";d2=d2||d1;1==d2&&(d2=d1,cc||(cc=1));2==d2&&1!=cc&&(d2=d1);vta=vta.split(",");for(var g=vta.length,e=0;e<g;e++)this.inList(lv,vta[e],d1,cc)||(lv=lv?lv+d2+vta[e]:vta[e])}return lv};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `apl` metodo utilizza i seguenti argomenti:

* **`lv`** (obbligatorio, stringa): Variabile che contiene un elenco delimitato di elementi a cui aggiungere un nuovo valore
* **`vta`** (obbligatorio, stringa): Elenco delimitato da virgole dei nuovi valori da aggiungere al valore dell&#39; `lv` argomento.
* **`d1`** (facoltativo, stringa): Il delimitatore utilizzato per separare i singoli valori già contenuti nell&#39; `lv` argomento.  Il valore predefinito è una virgola (`,`) se non è impostato.
* **`d2`** (facoltativo, stringa): Il delimitatore di output. Il valore predefinito è lo stesso di quando `d1` non è impostato.
* **`cc`** (facoltativo, booleano): Flag che indica se viene utilizzata una verifica con distinzione tra maiuscole e minuscole. Se `true`il controllo di duplicazione è sensibile alle maiuscole/minuscole. Se `false` non è impostato, il controllo di duplicazione non fa distinzione tra maiuscole e minuscole. Il valore predefinito è `false`.

Il `apl` metodo restituisce il valore dell&#39; `lv` argomento più eventuali valori non duplicati nell&#39; `vta` argomento.

## Chiamate di esempio

### Esempio n. 1

Se viene mostrato...

```js
s.events = "event22,event24";
```

...e viene eseguito il codice seguente...

```js
s.events = s.apl(s.events, "event23");
```

... il valore finale di s.events sarà:

```js
s.events = "event22,event24,event23";
```

### Esempio n. 2

Se viene mostrato...

```js
s.events = "event22,event23";
```

...e viene eseguito il codice seguente...

```js
s.events = s.apl(s.events, "event23");
```

... il valore finale di s.events sarà comunque:

```js
s.events = "event22,event23";
```

In questo esempio, la chiamata apl non ha apportato modifiche a s.events in quanto s.events conteneva già &quot;event23&quot;

### Esempio n. 3

Se viene mostrato...

```js
s.events = ""; //blank value
```

...e viene eseguito il codice seguente...

```js
s.events = s.apl(s.events, "event23");
```

... il valore finale di s.events sarà...

```js
s.events = "event23";
```

### Esempio n. 4

Se viene mostrato...

```js
s.prop4 = "hello|people";
```

...e viene eseguito il codice seguente...

```js
s.eVar5 = s.apl(s.prop4, "today", "|");
```

... il valore finale di s.prop4 sarà ancora...

```js
s.prop4 = "hello|people";
```

...ma il valore finale di s.eVar5 sarà

```js
s.eVar5 = "hello|people|today";
```

Tenere presente che il plug-in restituisce solo un valore; non reimposta necessariamente la variabile passata attraverso l&#39;argomento lv.

### Esempio n. 5

Se viene mostrato...

```js
s.prop4 = "hello|people";
```

...e viene eseguito il codice seguente...

```js
s.prop4 = s.apl(s.prop4, "today");
```

... il valore finale di s.prop4 sarà...

```js
s.prop4 = "hello|people,today";
```

Assicuratevi di mantenere il delimitatore coerente tra ciò che è presente nel valore dell&#39;argomento lv e ciò che è contenuto negli argomenti d1/d2

### Esempio n. 6

Se viene mostrato...

```js
s.events = "event22,event23";
```

...e viene eseguito il codice seguente...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

... il valore finale di s.events sarà:

```js
s.events = "event22,event23,EVentT23";
```

Anche se questo esempio non è pratico, dimostra la necessità di prestare attenzione quando si utilizza il flag sensibile alle maiuscole/minuscole.

### Esempio n. 7

Se viene mostrato...

```js
s.events = "event22,event23";
```

...e viene eseguito il codice seguente...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

... il valore finale di s.events sarà:

```js
s.events = "event22,event23,event24,event25");
```

Il plug-in non aggiungerà &quot;event23&quot; a s.events perché esiste già in s.events.  Tuttavia, aggiungerà a s.events sia event24 che event25 perché nessuno dei due era contenuto in precedenza in s.events.

### Esempio n. 8

Se viene mostrato...

```js
s.linkTrackVars = "events,eVar1";
```

...e viene eseguito il codice seguente...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

... il valore finale di s.linkTrackVars sarà:

```js
s.linkTrackVars = "events,eVar1,campaign";
```

Gli ultimi tre argomenti (vale a dire &quot;,&quot;, &quot;,&quot;, false) alla fine di questa chiamata apl non sono necessari ma non &quot;fanno male a nulla&quot; perché vengono impostati in quanto corrispondono ai valori dell&#39;argomento predefinito.

### Esempio n. 9

Se viene mostrato...

```js
s.events = "event22,event24";
```

...e viene eseguito il codice seguente...

```js
s.apl(s.events, "event23");
```

... il valore finale di s.events sarà comunque:

```js
s.events = "event22,event24";
```

L&#39;esecuzione del plug-in da sola (senza assegnare il valore restituito a una variabile) in realtà non &quot;reimposta&quot; la variabile passata attraverso l&#39;argomento lv.

### Esempio n. 10

Se viene mostrato...

```js
s.list2 = "casesensitivevalue|casesensitiveValue"
```

...e viene eseguito il codice seguente...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

... il valore finale di s.list2 sarà:

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

Poiché i due argomenti di delimitazione sono diversi, il valore passato sarà delimitato dal primo argomento di delimitazione (&quot;|&quot;) e quindi unito dal secondo argomento di delimitazione (&quot;-&quot;)

## Cronologia versioni

### 3.2 (25 settembre 2019)

* Risolti problemi di compatibilità con `apl` le chiamate che utilizzavano versioni precedenti del plug-in
* Sono stati rimossi gli avvisi sulla console per ridurre le dimensioni
* Aggiunto `inList 2.1`

### 3.1 (22 aprile 2018)

* `d2` argomento ora per impostazione predefinita viene impostato il valore dell&#39; `d1` argomento quando non è impostato

### 3.0 (16 aprile 2018)

* Rianalisi/riscrittura completa del plug-in
* È stato aggiunto il controllo avanzato degli errori
* L&#39; `vta` argomento ora accetta più valori alla volta
* È stato aggiunto l&#39; `d2` argomento per formattare il valore restituito
* L&#39; `cc` argomento è stato modificato in booleano

### 2.5 (18 febbraio 2016)

* Ora utilizza il `inList` metodo di elaborazione del confronto

### 2.0 (26 gennaio 2016)

* `d` (Delimitatore) ora facoltativo (impostazione predefinita: una virgola)
* `u` (Flag di distinzione tra maiuscole e minuscole) ora è facoltativo (impostazione predefinita: senza distinzione tra maiuscole e minuscole)
* Indipendentemente dall&#39;argomento `u` (flag di sensibilità alle maiuscole/minuscole), il plug-in non aggiunge più un valore a un elenco se il valore esiste già nell&#39;elenco