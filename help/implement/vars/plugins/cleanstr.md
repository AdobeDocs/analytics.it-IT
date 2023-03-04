---
title: cleanStr
description: Rimuovi o sostituisci tutti i caratteri non necessari da una stringa.
feature: Variables
exl-id: d699dcd4-5e0a-40d3-b345-e5b1a077d393
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 6%

---

# Plug-in Adobe: cleanStr

{{plug-in}}

Il `cleanStr` il plug-in rimuove o sostituisce tutti i caratteri non necessari da una stringa, inclusi i caratteri HTML tag, gli spazi vuoti aggiuntivi, le tabulazioni e i ritorni a capo o a nuova riga. Sostituisce inoltre le virgolette singole sinistra/destra (`‘` e `’`) con virgolette semplici (`'`). L’Adobe consiglia di utilizzare questo plug-in se desideri rimuovere i caratteri non necessari dai valori delle variabili e la funzione &quot;Testo pulito&quot; in Raccolta dati di Adobe Experience Platform non soddisfa le tue esigenze di implementazione. Questo plug-in non è necessario se i dati raccolti non contengono caratteri superflui o se è sufficiente la funzione &quot;Testo pulito&quot; in Raccolta dati di Adobe Experience Platform.

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
    * Action Type: Initialize cleanStr
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
/* Adobe Consulting Plugin: cleanStr v2.0 (No Prerequisites Required) */
function cleanStr(str){var a=str;if("-v"===a)return{plugin:"cleanStr",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}"undefined"!==typeof b&&(b.contextData.cleanStr="2.0");if("string"===typeof a){a=a.replace(/<\/?[^>]+(>|$)/g,"");a=a.trim();a=a.replace(/[\u2018\u2019\u201A]/g,"'");a=a.replace(/\t+/g,"");for(a=a.replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `cleanStr` La funzione utilizza i seguenti argomenti:

* **`str`** (obbligatorio, stringa): valore per il quale si desidera eliminare la codifica HTML, spazi vuoti aggiuntivi, tabulazioni o altri caratteri non necessari.

La funzione restituisce il valore della proprietà `str` con tutti i caratteri non necessari rimossi.

## Esempi

```js
// Returns the value "this is a messystring". Note that both tabs and extra spaces are present in the original string.
// Multiple spaces are reduced to one, while tabs are omitted entirely.
s.eVar1 = "  this  is a      messy  string    ";
s.eVar1 = cleanStr(s.eVar1)

// This function call does not do anything because the code does not assign the returned value to a variable.
s.eVar1 = "  this  is a      messy  string    ";
cleanStr(s.eVar1);
```

## Cronologia versioni

### 2.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 1.0 (15 aprile 2018)

* Versione iniziale.
