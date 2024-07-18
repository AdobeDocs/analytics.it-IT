---
title: inList
description: Verifica se un valore è contenuto in un altro valore delimitato da caratteri.
feature: Variables
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 7%

---

# Plug-in di Adobe: inList

{{plug-in}}

Il plug-in `inList` consente di verificare se esiste già un valore all&#39;interno di una stringa delimitata o di un oggetto array JavaScript. Diversi altri plug-in dipendono dal plug-in `inList` per funzionare. Questo plug-in offre un vantaggio netto rispetto al metodo JavaScript `indexOf()`, in cui non corrisponde a stringhe parziali. Se ad esempio si è utilizzato questo plug-in per verificare la presenza di `"event2"`, non verrà trovata alcuna corrispondenza con una stringa contenente `"event25"`. Questo plug-in non è necessario se non è necessario verificare la presenza di valori in stringhe o matrici delimitate o se si desidera utilizzare una logica `indexOf()` personalizzata.

## Installare il plug-in utilizzando l’estensione Web SDK o Web SDK

Questo plug-in non è ancora supportato per l’utilizzo nell’SDK per web.

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
   * Tipo azione: Inizializza inList
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

Copiare e incollare il codice seguente in qualsiasi punto del file di AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento di Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta ad Adobe nella risoluzione di eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `inList` restituisce un valore booleano a seconda dei suoi input. Vengono utilizzati i seguenti argomenti:

* **`lv`** (obbligatorio, stringa o array): elenco delimitato di valori o oggetto array JavaScript da cercare
* **`vtc`** (obbligatorio, stringa): valore da cercare
* **`d`** (facoltativo, stringa): delimitatore utilizzato per separare i singoli valori nell&#39;argomento `lv`. Impostazione predefinita: virgola (`,`) se non impostata.
* **`cc`** (facoltativo, booleano): se è impostato su `true` o `1`, viene eseguita una verifica con distinzione tra maiuscole e minuscole. Se è impostato su `false` o viene omesso, viene eseguito un controllo senza distinzione tra maiuscole e minuscole. Predefinito su `false`.

La chiamata di questa funzione restituisce `true` se trova una corrispondenza e `false` se non trova una corrispondenza.

## Esempi

```js
// Returns true
s.events = "event22,event24";
if(inList(s.events,"event22")) {
    // Code will execute
}

// Returns false because event2 is not an exact match in the string
s.events = "event22,event24";
if(inList(s.events,"event2")) {
    // Code will not execute
}

// Returns true because of the NOT operator
s.events = "event22,event24";
if(!inList(s.events,"event23")) {
    // Code will execute
}

// Returns false because of the case-sensitive check
s.events = "event22,event23";
if(inList(s.events,"EVenT23","",true)) {
    // Code will not execute
}

// Returns false because of a mismatched delimiter, treating "events,eVar1" as a single value
s.linkTrackVars = "events,eVar1";
if(inList(s.linkTrackVars,"eVar1","|")) {
    // Code will not execute
}
```

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### v2.1 (26 settembre 2019)

* È stata aggiunta l&#39;opzione affinché l&#39;argomento `cc` non sia booleano. `1`, ad esempio, è un valore di verifica maiuscole/minuscole valido.

### v2.0 (17 aprile 2018)

* Versione a punti (ricompilata, con codice di dimensioni inferiori).

### v1.01 (27 settembre 2017)

* Codice ottimizzato per ridurre le dimensioni

### v1.0 (2009)

* Versione iniziale.
