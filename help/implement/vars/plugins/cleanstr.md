---
title: cleanStr
description: Rimuovi o sostituisci tutti i caratteri non necessari da una stringa.
feature: Appmeasurement Implementation
exl-id: d699dcd4-5e0a-40d3-b345-e5b1a077d393
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 8%

---

# Plug-in Adobe: cleanStr

{{plug-in}}

Il plug-in `cleanStr` rimuove o sostituisce tutti i caratteri non necessari da una stringa, inclusi i caratteri tag di HTML, gli spazi vuoti aggiuntivi, le tabulazioni e i ritorni a capo/nuova riga. Sostituisce inoltre le virgolette singole a sinistra/destra con le virgolette singole rette (`'`). Adobe consiglia di utilizzare questo plug-in se desideri rimuovere i caratteri non necessari dai valori delle variabili e la funzione &quot;Testo pulito&quot; in Raccolta dati di Adobe Experience Platform non soddisfa le tue esigenze di implementazione. Questo plug-in non è necessario se i dati raccolti non contengono caratteri superflui o se è sufficiente la funzione &quot;Testo pulito&quot; in Raccolta dati di Adobe Experience Platform.

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
   * Tipo azione: inizializzare cleanStr
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
/* Adobe Consulting Plugin: cleanStr v2.0 (No Prerequisites Required) */
function cleanStr(str){var a=str;if("-v"===a)return{plugin:"cleanStr",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}"undefined"!==typeof b&&(b.contextData.cleanStr="2.0");if("string"===typeof a){a=a.replace(/<\/?[^>]+(>|$)/g,"");a=a.trim();a=a.replace(/[\u2018\u2019\u201A]/g,"'");a=a.replace(/\t+/g,"");for(a=a.replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `cleanStr` utilizza i seguenti argomenti:

* **`str`** (obbligatorio, stringa): valore per cui si desidera eliminare la codifica HTML, spazi vuoti aggiuntivi, tabulazioni o altri caratteri non necessari.

La funzione restituisce il valore dell&#39;argomento `str` con tutti i caratteri non necessari rimossi.

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
