---
title: apl (appendToList)
description: Aggiungi valori a variabili che supportano più valori.
translation-type: tm+mt
source-git-commit: d84d53dd237f5bba729c902c8c4980c0288dbbb0
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 1%

---


# Plug-in di Adobe: apl (appendToList)

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `apl` consente di aggiungere in modo sicuro nuovi valori alle variabili delimitate da elenchi, come [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md) e altri.

* Se il valore che desideri aggiungere non esiste nella variabile , il codice aggiunge il valore alla fine della stringa.
* Se il valore che desideri aggiungere esiste già nella variabile , questo plug-in non modifica il valore. Questa funzione consente all’implementazione di evitare valori duplicati.
* Se la variabile da aggiungere è vuota, il plug-in imposta la variabile sul nuovo valore.

Adobe consiglia di utilizzare questo plug-in se desideri aggiungere nuovi valori alle variabili esistenti che contengono una stringa di valori delimitati. Questo plug-in non è necessario se preferisci concatenare stringhe per variabili contenenti valori delimitati.

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
   * Tipo azione: Inizializza APL (Aggiungi All’Elenco)
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
/* Adobe Consulting Plugin: apl (appendToList) v4.0 */
function apl(lv,va,d1,d2,cc){var b=lv,d=va,e=d1,c=d2,g=cc;if("-v"===b)return{plugin:"apl",version:"4.0"};var h=function(){if("undefined"!==typeof window.s_c_il)for(var k=0,b;k<window.s_c_il.length;k++)if(b=window.s_c_il[k],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof h&&(h.contextData.apl="4.0");window.inList=window.inList||function(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1};if(!b||"string"===typeof b){if("string"!==typeof d||""===d)return b;e=e||",";c=c||e;1==c&&(c=e,g||(g=1));2==c&&1!=g&&(c=e);d=d.split(",");h=d.length;for(var f=0;f<h;f++)window.inList(b,d[f],e,g)||(b=b?b+c+d[f]:d[f])}return b};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `apl` utilizza i seguenti argomenti:

* **`lv`** (obbligatorio, stringa): Variabile che contiene un elenco delimitato di elementi a cui aggiungere un nuovo valore
* **`vta`** (obbligatorio, stringa): Elenco delimitato da virgole dei nuovi valori da aggiungere al valore dell’ `lv` argomento.
* **`d1`** (facoltativo, stringa): Il delimitatore utilizzato per separare i singoli valori già contenuti nell’ `lv` argomento.  Se non è impostato, viene impostata automaticamente una virgola (`,`).
* **`d2`** (facoltativo, stringa): Il delimitatore di output. Se non è impostato, restituisce lo stesso valore di `d1`.
* **`cc`** (facoltativo, booleano): Flag che indica se viene utilizzato un controllo con distinzione tra maiuscole e minuscole. Se `true`, il controllo della duplicazione è sensibile a maiuscole e minuscole. Se `false` o non è impostato, il controllo della duplicazione non fa distinzione tra maiuscole e minuscole. Predefinito su `false`.

Il metodo `apl` restituisce il valore dell&#39;argomento `lv` più eventuali valori non duplicati nell&#39;argomento `vta`.

## Chiamate di esempio

### Esempio n. 1

Se viene mostrato...

```js
s.events = "event22,event24";
```

...e viene eseguito il seguente codice...

```js
s.events = s.apl(s.events, "event23");
```

... il valore finale di s.events sarà:

```js
s.events = "event22,event24,event23";
```

### Esempio n. 3

Se viene mostrato...

```js
s.events = "event22,event23";
```

...e viene eseguito il seguente codice...

```js
s.events = s.apl(s.events, "event23");
```

... il valore finale di s.events sarà comunque:

```js
s.events = "event22,event23";
```

In questo esempio, la chiamata apl non ha apportato modifiche a s.events poiché s.events conteneva già &quot;event23&quot;

### Esempio n. 2

Se viene mostrato...

```js
s.events = ""; //blank value
```

...e viene eseguito il seguente codice...

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

...e viene eseguito il seguente codice...

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

Tieni presente che il plug-in restituisce solo un valore; non reimposta necessariamente la variabile passata attraverso l’argomento lv.

### Esempio n. 5

Se viene mostrato...

```js
s.prop4 = "hello|people";
```

...e viene eseguito il seguente codice...

```js
s.prop4 = s.apl(s.prop4, "today");
```

... il valore finale di s.prop4 sarà...

```js
s.prop4 = "hello|people,today";
```

Assicurati di mantenere il delimitatore coerente tra ciò che è nel valore dell&#39;argomento lv e ciò che è negli argomenti d1/d2

### Esempio n. 6

Se viene mostrato...

```js
s.events = "event22,event23";
```

...e viene eseguito il seguente codice...

```js
s.events = s.apl(s.events,"EVenT23", ",", ",", true);
```

... il valore finale di s.events sarà:

```js
s.events = "event22,event23,EVentT23";
```

Anche se questo esempio non è pratico, dimostra la necessità di usare cautela quando si utilizza il flag che distingue tra maiuscole e minuscole.

### Esempio n. 7

Se viene mostrato...

```js
s.events = "event22,event23";
```

...e viene eseguito il seguente codice...

```js
s.events = s.apl(s.events, "event23,event24,event25");
```

... il valore finale di s.events sarà:

```js
s.events = "event22,event23,event24,event25");
```

Il plug-in non aggiungerà &quot;event23&quot; a s.events perché esiste già in s.events.  Tuttavia, aggiungerà sia event24 che event25 a s.events perché nessuno dei due era precedentemente contenuto in s.events.

### Esempio n. 8

Se viene mostrato...

```js
s.linkTrackVars = "events,eVar1";
```

...e viene eseguito il seguente codice...

```js
s.linkTrackVars = s.apl(s.linkTrackVars, "campaign", ",", ",", false);
```

... il valore finale di s.linkTrackVars sarà:

```js
s.linkTrackVars = "events,eVar1,campaign";
```

Gli ultimi tre argomenti (cioè &quot;,&quot;, &quot;,&quot;, false) alla fine di questa chiamata apl non sono necessarie ma non &quot;danneggiano nulla&quot; poiché corrispondono ai valori dell’argomento predefiniti.

### Esempio n. 9

Se viene mostrato...

```js
s.events = "event22,event24";
```

...e viene eseguito il seguente codice...

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

...e viene eseguito il seguente codice...

```js
s.list2 = s.apl(s.list2, "CasESensiTiveValuE", "|", "-", true);
```

... il valore finale di s.list2 sarà:

```js
s.list2 = "casesensitivevalue-casesensitiveValue-CasESensiTiveValuE"
```

Poiché i due argomenti delimitatori sono diversi, il valore passato sarà delimitato dal primo argomento delimitatore (&quot;|&quot;) e quindi unito dal secondo argomento delimitatore (&quot;-&quot;)

## Cronologia versioni

### 4.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 3.2 (25 settembre 2019)

* Sono stati risolti i problemi di compatibilità con le chiamate `apl` che utilizzavano versioni precedenti del plug-in
* Sono stati rimossi gli avvisi della console per ridurre le dimensioni
* Aggiunto `inList 2.1`

### 3.1 (22 aprile 2018)

* `d2` viene ora impostato automaticamente il valore dell&#39; `d1` argomento se non è impostato

### 3.0 (16 aprile 2018)

* Rianalisi/riscrittura completa del plug-in
* È stato aggiunto il controllo avanzato degli errori
* L’argomento `vta` ora accetta più valori contemporaneamente
* È stato aggiunto l’argomento `d2` per formattare il valore restituito
* L’argomento `cc` è stato modificato in booleano

### 2.5 (18 febbraio 2016)

* Ora utilizza il metodo `inList` per l&#39;elaborazione del confronto

### 2.0 (26 gennaio 2016)

* `d` (Delimitatore) argomento ora facoltativo (impostazione predefinita: virgola)
* `u` L’argomento (flag di distinzione tra maiuscole e minuscole) ora è facoltativo (impostazione predefinita, senza distinzione tra maiuscole e minuscole)
* Indipendentemente dall’argomento `u` (flag di distinzione maiuscole/minuscole), il plug-in non aggiunge più un valore a un elenco se il valore esiste già nell’elenco
