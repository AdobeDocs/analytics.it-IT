---
title: p_fo (solo pagina prima)
description: Assicurati che alcune routine si attivino una sola volta per pagina.
feature: Variables
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 3%

---

# Plug-in di Adobe: p_fo (solo pagina prima)

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting per aiutarti a ottenere più valore da Adobe Analytics. Adobe L’Assistenza clienti non fornisce supporto con questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di assistenza su questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare un incontro con un consulente per ricevere assistenza.

Il `p_fo` Il plug-in è un&#39;utility che verifica l&#39;esistenza di un oggetto JavaScript specifico. Se l&#39;oggetto non esiste, il plug-in crea l&#39;oggetto e restituisce `true`. Se l&#39;oggetto JavaScript esiste già nella pagina, restituisce `false`. Questo plug-in è utile per eseguire il codice esattamente una volta su una pagina. Diversi altri plug-in si basano su questo codice per funzionare. Questo plug-in non è necessario se non sei preoccupato del numero di volte in cui il codice viene eseguito su una pagina o se non utilizzi plug-in dipendenti.

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
    * Action Type: Initialize p_fo
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
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `p_fo` La funzione utilizza i seguenti argomenti:

* **il** (obbligatorio, stringa): nome dell&#39;oggetto JavaScript creato dal plug-in, se l&#39;oggetto non esiste ancora nella pagina.

Se l’oggetto non esiste ancora, questa funzione restituisce `true` e crea l’oggetto. Se l’oggetto esiste già, questa funzione restituisce `false`.

## Esempio di chiamate

### Esempio di #1

Il codice seguente verifica l&#39;esistenza dell&#39;oggetto &quot;myobject&quot; all&#39;interno della pagina.  Se l&#39;oggetto &quot;myobject&quot; non esiste, il codice creerà l&#39;oggetto &quot;myobject&quot; e restituirà il valore true.  Di conseguenza, verrà eseguito il codice all’interno dell’istruzione condizionale (ovvero Console.log(&#39;hello&#39;);).

D&#39;altra parte, se l&#39;oggetto &quot;myobject&quot; esiste già quando viene effettuata la chiamata p_fo, la funzione p_fo restituirà il valore false e, pertanto, l&#39;istruzione condizionale sarà considerata false.  In questo caso, il codice all’interno dell’istruzione condizionale non verrà eseguito.

```js
if(p_fo("myobject"))
{
  console.log("hello");
}
```

**NOTA:** Ogni volta che un nuovo oggetto pagina/DOM viene caricato (o la pagina corrente viene ricaricata), l&#39;oggetto specificato nell&#39;argomento on non esisterà più e pertanto il plug-in p_fo restituirà nuovamente true la prima volta che viene eseguito dopo il completamento del caricamento della pagina.

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.0

* Versione a punti (ricompilata, con codice di dimensioni inferiori).
* Tipo di valore restituito cambiato da intero a booleano

### 1.0

* Versione iniziale.
