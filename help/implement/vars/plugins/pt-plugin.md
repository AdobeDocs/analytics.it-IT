---
title: pt
description: Esegue una funzione su un elenco di variabili.
feature: Variables
exl-id: 2ab24a8e-ced3-43ea-bdb5-7c39810e4102
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 6%

---

# Plug-in di Adobe: pt

{{plug-in}}

Il plug-in `pt` esegue una funzione o un metodo in un elenco di variabili di Analytics. È ad esempio possibile eseguire in modo selettivo la funzione [`clearVars`](../functions/clearvars.md) su più variabili senza chiamare manualmente la funzione ogni volta. Diversi altri plug-in dipendono da questo codice per funzionare correttamente. Questo plug-in non è necessario se non è necessario eseguire una funzione specifica su più variabili Analytics alla volta o se non si utilizzano plug-in dipendenti.

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
   * Tipo azione: inizializza pt
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
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `pt` utilizza i seguenti argomenti:

* **`l`** (obbligatorio, stringa): elenco di variabili su cui può essere eseguita la funzione contenuta nell&#39;argomento `cf`.
* **`de`** (facoltativo, stringa): delimitatore che separa l&#39;elenco di variabili nell&#39;argomento `l`. Impostazione predefinita: virgola (`,`).
* **`cf`** (obbligatorio, stringa): nome della funzione di callback contenuta nell&#39;oggetto AppMeasurement da chiamare per ciascuna delle variabili contenute nell&#39;argomento `l`.
* **`fa`** (facoltativo, stringa): se la funzione nell&#39;argomento `cf` richiede argomenti aggiuntivi durante l&#39;esecuzione, includerli qui. Predefinito su `undefined`.

La chiamata di questa funzione restituisce un valore se la funzione di callback (nell&#39;argomento `cf`) restituisce un valore.

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
* È stato aggiunto il supporto sia per il codice H che per l’AppMeasurement.

### 1.0 (23 settembre 2013)

* Versione iniziale.
