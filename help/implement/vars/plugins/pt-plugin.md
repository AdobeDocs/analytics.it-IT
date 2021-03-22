---
title: pt
description: Esegue una funzione in un elenco di variabili.
translation-type: tm+mt
source-git-commit: fc7e6953e69cdff7b326705a906687be634d9b5f
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 1%

---


# Plug-in di Adobe: pt

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `pt` esegue una funzione o un metodo in un elenco di variabili di Analytics. Ad esempio, puoi eseguire selettivamente il metodo [`clearVars`](../functions/clearvars.md) su più variabili senza chiamare manualmente ogni volta il metodo . Diversi altri plug-in dipendono da questo codice per essere eseguiti correttamente. Questo plug-in non è necessario se non è necessario eseguire una funzione specifica su più di una variabile Analytics alla volta o se non si utilizzano plug-in dipendenti.

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
   * Tipo azione: Inizializza pt
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
/* Adobe Consulting Plugin: pt v3.0 */
function pt(l,de,cf,fa){var b=l,d=de,f=cf,g=fa;if("-v"===b)return{plugin:"pt",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var c;a<window.s_c_il.length;a++)if(c=window.s_c_il[a],c._c&&"s_c"===c._c){a=c;break a}}a=void 0}if("undefined"!==typeof a&&(a.contextData.pt="3.0",b&&a[f])){b=b.split(d||",");d=b.length;for(var e=0;e<d;e++)if(c=a[f](b[e],g))return c}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `pt` utilizza i seguenti argomenti:

* **`l`** (obbligatorio, stringa): Elenco di variabili su cui può essere eseguita la funzione contenuta nell’ `cf` argomento.
* **`de`** (facoltativo, stringa): Il delimitatore che separa l’elenco di variabili nell’ `l` argomento. Impostazione predefinita di una virgola (`,`).
* **`cf`** (obbligatorio, stringa): Il nome della funzione di callback contenuta nell&#39;oggetto AppMeasurement da chiamare rispetto a ciascuna delle variabili contenute nell&#39; `l` argomento.
* **`fa`** (facoltativo, stringa): Se la funzione nell&#39; `cf` argomento richiede argomenti aggiuntivi durante l&#39;esecuzione, includerli qui. Predefinito su `undefined`.

Una chiamata a questo metodo restituisce un valore se la funzione di callback (nell&#39;argomento `cf` ) restituisce un valore.

## Chiamate di esempio

### Esempio n. 1

Il codice seguente fa parte del plug-in getQueryParam .  Esegue la funzione helper getParameterValue rispetto a ciascuna delle coppie chiave-valore contenute nella stringa query dell&#39;URL (fullQueryString).  In un altro caso, per estrarre ogni coppia chiave-valore, è necessario delimitare fullQueryString e dividerlo con un carattere e commerciale &quot;&amp;&quot;. Il parametroKey si riferisce al parametro della stringa di query che il plug-in sta tentando di estrarre dalla stringa di query

```javascript
returnValue = pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

La riga precedente è una scorciatoia per l’esecuzione del codice che assomiglia a quanto segue:

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = s.getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.01 (24 settembre 2019)

* Modifiche minori del codice per ridurre le dimensioni complessive

### 2.0 (17 aprile 2018)

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).
* È stato aggiunto il supporto per H-code e AppMeasurement.

### 1.0 (23 settembre 2013)

* Versione iniziale.
