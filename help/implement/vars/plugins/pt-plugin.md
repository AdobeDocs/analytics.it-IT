---
title: pt
description: Esegue una funzione su un elenco di variabili.
feature: Variables
exl-id: 2ab24a8e-ced3-43ea-bdb5-7c39810e4102
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 4%

---

# Plug-in di Adobe: pt

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting per aiutarti a ottenere più valore da Adobe Analytics. Adobe L’Assistenza clienti non fornisce supporto con questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di assistenza su questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare un incontro con un consulente per ricevere assistenza.

Il `pt` Il plug-in esegue una funzione o un metodo in un elenco di variabili di Analytics. Ad esempio, puoi eseguire in modo selettivo [`clearVars`](../functions/clearvars.md) su diverse variabili senza chiamare manualmente la funzione ogni volta. Diversi altri plug-in dipendono da questo codice per funzionare correttamente. Questo plug-in non è necessario se non è necessario eseguire una funzione specifica su più variabili Analytics alla volta o se non si utilizzano plug-in dipendenti.

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
    * Action Type: Initialize pt
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
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `pt` La funzione utilizza i seguenti argomenti:

* **`l`** (obbligatorio, stringa): elenco di variabili contenute nella funzione `cf` può essere eseguito su.
* **`de`** (facoltativo, stringa): delimitatore che separa l’elenco di variabili in `l` argomento. Impostazione predefinita: virgola (`,`).
* **`cf`** (obbligatorio, stringa): nome della funzione di callback contenuta nell&#39;oggetto AppMeasurement da chiamare per ciascuna delle variabili contenute nell&#39; `l` argomento.
* **`fa`** (facoltativo, stringa): se la funzione nel campo `cf` L&#39;argomento richiede argomenti aggiuntivi durante l&#39;esecuzione. Includerli qui. Predefinito su `undefined`.

La chiamata di questa funzione restituisce un valore se la funzione di callback (in `cf` ) restituisce un valore.

## Esempio di chiamate

### Esempio di #1

Il codice seguente fa parte del plug-in getQueryParam.  Esegue la funzione helper getParameterValue su ciascuna delle coppie chiave-valore contenute nella stringa di interrogazione dell&#39;URL (fullQueryString).  In altri casi, per estrarre ogni coppia chiave-valore, fullQueryString deve essere delimitato e diviso da un carattere &quot;&amp;&quot; di e commerciale. Il parametro parameterKey fa riferimento al parametro della stringa di query che il plug-in sta specificatamente tentando di estrarre dalla stringa di query

```js
returnValue = pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

La riga precedente è una scelta rapida per l&#39;esecuzione di codice simile al seguente:

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.01 (24 settembre 2019)

* Modifiche minori al codice per ridurre le dimensioni complessive

### 2.0 (17 aprile 2018)

* Versione a punti (ricompilata, con codice di dimensioni inferiori).
* È stato aggiunto il supporto per H-code e AppMeasurement.

### 1.0 (23 settembre 2013)

* Versione iniziale.
