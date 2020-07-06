---
title: pt
description: Esegue una funzione in un elenco di variabili.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 1%

---


# Plug-in Adobe: pt

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `pt` plug-in esegue una funzione o un metodo in un elenco di variabili Analytics . Ad esempio, è possibile eseguire selettivamente il [`clearVars`](../functions/clearvars.md) metodo su più variabili senza chiamare manualmente il metodo ogni volta. Molti altri plug-in dipendono da questo codice per essere eseguiti correttamente. Questo plug-in non è necessario se non è necessario eseguire una funzione specifica su più variabili Analytics  alla volta, oppure se non si utilizzano plug-in dipendenti.

## Installare il plug-in utilizzando l&#39;estensione Lancio del Adobe Experience Platform 

Adobe offre un’estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installare e pubblicare l’ [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo avete già fatto, create una regola con l&#39;etichetta &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (Page Top)
1. Aggiungete un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in Analytics  comuni
   * Tipo azione: Initialize pt
1. Salvate e pubblicate le modifiche alla regola.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe  Analytics.
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche nell’estensione Analytics .

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo che è stata creata un&#39;istanza dell&#39;oggetto di tracciamento Analytics  (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione di commenti e numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `pt` metodo utilizza i seguenti argomenti:

* **`l`** (obbligatorio, stringa): Un elenco di variabili per le quali la funzione contenuta nell&#39; `cf` argomento può essere eseguita.
* **`de`** (facoltativo, stringa): Il delimitatore che separa l&#39;elenco di variabili nell&#39; `l` argomento. Il valore predefinito è una virgola (`,`).
* **`cf`** (obbligatorio, stringa): Il nome della funzione di callback contenuta nell&#39;oggetto AppMeasurement da chiamare rispetto a ciascuna delle variabili contenute nell&#39; `l` argomento.
* **`fa`** (facoltativo, stringa): Se la funzione nell&#39; `cf` argomento richiede argomenti aggiuntivi durante l&#39;esecuzione, includeteli qui. Il valore predefinito è `undefined`.

La chiamata di questo metodo restituisce un valore se la funzione di callback (nell’ `cf` argomento) restituisce un valore.

## Chiamate di esempio

### Esempio n. 1

Il codice seguente fa parte del plug-in getQueryParam.  Esegue la funzione helper getParameterValue rispetto a ciascuna delle coppie chiave-valore contenute nella stringa query dell&#39;URL (fullQueryString).  Nell&#39;altro caso, per estrarre ogni coppia chiave-valore, fullQueryString deve essere delimitato e diviso per una e commerciale &quot;&amp;&quot;. Il parametroKey si riferisce al parametro della stringa di query che il plug-in sta cercando specificamente di estrarre dalla stringa di query

```javascript
returnValue = s.pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

La riga precedente è una scorciatoia per l&#39;esecuzione di codice che assomiglia a quanto segue:

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

### 2.01 (24 settembre 2019)

* Modifiche minori del codice per ridurre le dimensioni complessive

### 2.0 (17 aprile 2018)

* Rilascio punto (ricompilato, dimensioni del codice più piccole).
* È stato aggiunto il supporto sia per il codice H che per AppMeasurement.

### 1.0 (23 settembre 2013)

* Versione iniziale.
