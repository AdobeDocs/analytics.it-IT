---
title: inList
description: Verifica se un valore è contenuto in un altro valore delimitato da caratteri.
feature: Variables
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 4%

---

# Plug-in di Adobe: inList

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting per aiutarti a ottenere più valore da Adobe Analytics. Adobe L’Assistenza clienti non fornisce supporto con questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di assistenza su questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare un incontro con un consulente per ricevere assistenza.

Il `inList` Il plug-in consente di verificare se esiste già un valore all’interno di una stringa delimitata o di un oggetto array JavaScript. Diversi altri plug-in dipendono dal `inList` plug-in per funzionare. Questo plug-in offre un vantaggio netto rispetto al metodo JavaScript `indexOf()` dove non corrisponde a stringhe parziali. Ad esempio, se hai utilizzato questo plug-in per verificare `"event2"`, non corrisponderà a una stringa contenente `"event25"`. Questo plug-in non è necessario se non è necessario verificare la presenza di valori in stringhe o matrici delimitate o se si desidera utilizzare un plug-in personalizzato `indexOf()` logica.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize inList
1. Save and publish the changes to the rule.-->

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l&#39;estensione del plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sulla scheda **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi [!UICONTROL Configure tracking using custom code] Pannello a soffietto, che mostra [!UICONTROL Open Editor] pulsante.
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell’istanza dell’oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta ad Adobe nella risoluzione di eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `inList` La funzione restituisce un valore booleano a seconda dei suoi input. Vengono utilizzati i seguenti argomenti:

* **`lv`** (obbligatorio, stringa o array): elenco delimitato di valori o oggetto array JavaScript da cercare
* **`vtc`** (obbligatorio, stringa): valore da cercare
* **`d`** (facoltativo, stringa): delimitatore utilizzato per separare i singoli valori nella `lv` argomento. Impostazione predefinita: virgola (`,`) quando non è impostato.
* **`cc`** (facoltativo, booleano): se impostato su `true` o `1`, viene effettuato un controllo con distinzione tra maiuscole e minuscole. Se impostato su `false` o viene omesso, viene effettuato un controllo senza distinzione tra maiuscole e minuscole. Predefinito su `false`.

La chiamata di questa funzione restituisce `true` se trova una corrispondenza, e `false` se non trova una corrispondenza.

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

* È stata aggiunta l’opzione per `cc` non essere un valore booleano. Ad esempio: `1` è un valore di controllo del caso valido.

### v2.0 (17 aprile 2018)

* Versione a punti (ricompilata, con codice di dimensioni inferiori).

### v1.01 (27 settembre 2017)

* Codice ottimizzato per ridurre le dimensioni

### v1.0 (2009)

* Versione iniziale.
