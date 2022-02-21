---
title: pt
description: Esegue una funzione in un elenco di variabili.
feature: Variables
exl-id: 2ab24a8e-ced3-43ea-bdb5-7c39810e4102
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# Plug-in di Adobe: pt

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

La `pt` Il plug-in esegue una funzione o un metodo in un elenco di variabili di Analytics. Ad esempio, puoi eseguire in modo selettivo il [`clearVars`](../functions/clearvars.md) funziona su più variabili senza chiamare manualmente la funzione ogni volta. Diversi altri plug-in dipendono da questo codice per essere eseguiti correttamente. Questo plug-in non è necessario se non è necessario eseguire una funzione specifica su più di una variabile Analytics alla volta o se non si utilizzano plug-in dipendenti.

## Installare il plug-in utilizzando i tag in Adobe Experience Platform

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installa e pubblica il [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza pt
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
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

La `pt` La funzione utilizza i seguenti argomenti:

* **`l`** (obbligatorio, stringa): Elenco di variabili contenute nella funzione `cf` L&#39;argomento può essere eseguito in base a.
* **`de`** (facoltativo, stringa): Il delimitatore che separa l’elenco delle variabili nel `l` argomento. Impostazione predefinita di una virgola (`,`).
* **`cf`** (obbligatorio, stringa): Nome della funzione di callback contenuta nell&#39;oggetto AppMeasurement da chiamare rispetto a ciascuna delle variabili contenute nel `l` argomento.
* **`fa`** (facoltativo, stringa): Se la funzione in `cf` L&#39;argomento richiede argomenti aggiuntivi quando viene eseguito, includerli qui. Predefinito su `undefined`.

Una chiamata a questa funzione restituisce un valore se la funzione di callback (nel `cf` (argomento) restituisce un valore.

## Chiamate di esempio

### Esempio n. 1

Il codice seguente fa parte del plug-in getQueryParam .  Esegue la funzione helper getParameterValue rispetto a ciascuna delle coppie chiave-valore contenute nella stringa query dell&#39;URL (fullQueryString).  In un altro caso, per estrarre ogni coppia chiave-valore, è necessario delimitare fullQueryString e dividerlo con un carattere e commerciale &quot;&amp;&quot;. Il parametroKey si riferisce al parametro della stringa di query che il plug-in sta tentando di estrarre dalla stringa di query

```js
returnValue = pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

La riga precedente è una scorciatoia per l’esecuzione del codice che assomiglia a quanto segue:

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

* Modifiche minori del codice per ridurre le dimensioni complessive

### 2.0 (17 aprile 2018)

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).
* È stato aggiunto il supporto per H-code e AppMeasurement.

### 1.0 (23 settembre 2013)

* Versione iniziale.
