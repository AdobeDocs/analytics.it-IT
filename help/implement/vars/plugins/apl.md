---
title: apl (appendToList)
description: Aggiungi valori a variabili che supportano più valori.
feature: Variables
exl-id: 08ca43f4-f2cc-43fb-a8eb-7c9dd237dfba
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 6%

---

# Plug-in di Adobe: apl (appendToList)

{{plug-in}}

La `apl` il plug-in consente di aggiungere in modo sicuro nuovi valori alle variabili delimitate da elenchi, ad esempio [`events`](../page-vars/events/events-overview.md), [`linkTrackVars`](../config-vars/linktrackvars.md), [`list`](../page-vars/list.md)e altri.

* Se il valore che desideri aggiungere non esiste nella variabile , il codice aggiunge il valore alla fine della stringa.
* Se il valore che desideri aggiungere esiste già nella variabile , questo plug-in non modifica il valore. Questa funzione consente all’implementazione di evitare valori duplicati.
* Se la variabile da aggiungere è vuota, il plug-in imposta la variabile sul nuovo valore.

Adobe consiglia di utilizzare questo plug-in se desideri aggiungere nuovi valori alle variabili esistenti che contengono una stringa di valori delimitati. Questo plug-in non è necessario se preferisci concatenare stringhe per variabili contenenti valori delimitati.

## Installare il plug-in utilizzando l’SDK per web o l’estensione SDK per web

Questo plug-in non è ancora supportato per l&#39;utilizzo all&#39;interno dell&#39;SDK per web.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installa e pubblica il [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza APL (Aggiungi All’Elenco)
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
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

La `apl` La funzione utilizza i seguenti argomenti:

* **`lv`** (obbligatorio, stringa): Variabile che contiene un elenco delimitato di elementi a cui aggiungere un nuovo valore
* **`vta`** (obbligatorio, stringa): Elenco delimitato da virgole dei nuovi valori da aggiungere al `lv` valore dell&#39;argomento.
* **`d1`** (facoltativo, stringa): Il delimitatore utilizzato per separare i singoli valori già contenuti nel `lv` argomento.  Impostazione predefinita di una virgola (`,`) quando non è impostato.
* **`d2`** (facoltativo, stringa): Il delimitatore di output. Predefinito allo stesso valore di `d1` quando non è impostato.
* **`cc`** (facoltativo, booleano): Flag che indica se viene utilizzato un controllo con distinzione tra maiuscole e minuscole. Se `true`, il controllo della duplicazione distingue tra maiuscole e minuscole. Se `false` Se non è impostato, il controllo della duplicazione non fa distinzione tra maiuscole e minuscole. Predefinito su `false`.

La `apl` restituisce il valore del `lv` più eventuali valori non duplicati nel `vta` argomento.

## Esempi

```js
// Set the events variable to "event22,event24,event23".
s.events = "event22,event24";
s.events = apl(s.events,"event23");

// The events variable remains unchanged because the apl function does not add duplicate values
s.events = "event22,event23";
s.events = apl(s.events,"event23");

// Set the events variable to "event23" if the events variable is blank
s.events = "";
s.events = apl(s.events,"event23");

// Append a value to eVar5. The value of prop4 remains unchanged.
// The value of eVar5 is "hello|people|today".
s.prop4 = "hello|people";
s.eVar5 = apl(s.prop4, "today", "|");

// Sets prop4 to "hello|people,today". Be mindful of correct delimiters!
s.prop4 = "hello|people";
s.prop4 = apl(s.prop4, "today");

// Sets the events variable to "event22,event23,EVentT23". Be mindful of capitalization when using the cc argument!
s.events = "event22,event23";
s.events = apl(s.events,"EVenT23", ",", ",", true);

// Sets the events variable to "event22,event23,event24,event25".
s.events = "event22,event23";
s.events = apl(s.events, "event23,event24,event25");

// Sets linkTrackVars to "events,eVar1,campaign".
// The last three arguments at the end of this apl call are not necessary because they match the default argument values.
s.linkTrackVars = "events,eVar1";
s.linkTrackVars = apl(s.linkTrackVars, "campaign", ",", ",", false);

// This apl call does not do anything because the code does not assign the returned value to a variable.
s.events = "event22,event24";
apl(s.events, "event23");

// Sets the list2 variable to "apple-APPLE-Apple".
// Since the two delimiter arguments are different, the value passed in is delimited by "|", then joined together by "-".
s.list2 = "apple|APPLE";
s.list2 = apl(s.list2, "Apple", "|", "-", true);

// Sets the list3 variable to "value1,value1,value1" (unchanged).
// Only new values are deduplicated. Existing duplicate values remain.
s.list3 = "value1,value1,value1";
s.list3 = apl(s.list3,"value1");
```

## Cronologia versioni

### 4.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 3.2 (25 settembre 2019)

* Sono stati risolti i problemi di compatibilità con `apl` chiamate che utilizzavano versioni precedenti del plug-in
* Sono stati rimossi gli avvisi della console per ridurre le dimensioni
* Aggiunto `inList 2.1`

### 3.1 (22 aprile 2018)

* `d2` ora viene impostato automaticamente il valore del `d1` argomento non impostato

### 3.0 (16 aprile 2018)

* Rianalisi/riscrittura completa del plug-in
* È stato aggiunto il controllo avanzato degli errori
* La `vta` argomento ora accetta più valori contemporaneamente
* È stato aggiunto il `d2` argomento per formattare il valore restituito
* Modificato il `cc` argomento di un valore booleano

### 2.5 (18 febbraio 2016)

* Ora utilizza il `inList` funzione di elaborazione del confronto

### 2.0 (26 gennaio 2016)

* `d` (Delimitatore) argomento ora facoltativo (impostazione predefinita: virgola)
* `u` L’argomento (flag di distinzione tra maiuscole e minuscole) ora è facoltativo (impostazione predefinita, senza distinzione tra maiuscole e minuscole)
* Indipendentemente dal `u` (Flag per la distinzione tra maiuscole e minuscole), il plug-in non aggiunge più un valore a un elenco se il valore esiste già nell’elenco
