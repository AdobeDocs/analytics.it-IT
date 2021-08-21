---
title: inList
description: Controlla se un valore è contenuto in un altro valore delimitato da caratteri.
exl-id: 7eedfd01-2b9a-4fae-a35b-433ca6900f27
source-git-commit: ab078c5da7e0e38ab9f0f941b407cad0b42dd4d1
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 1%

---

# Plug-in di Adobe: inList

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `inList` consente di verificare se un valore esiste già all&#39;interno di una stringa delimitata o di un oggetto array JavaScript. Diversi altri plug-in dipendono dal funzionamento del plug-in `inList` . Questo plug-in fornisce un vantaggio distinto rispetto al metodo JavaScript `indexOf()` in cui non corrisponde a stringhe parziali. Ad esempio, se hai utilizzato questo plug-in per verificare la presenza di `"event2"`, non corrisponderà a una stringa contenente `"event25"`. Questo plug-in non è necessario se non è necessario verificare la presenza di valori in stringhe o array delimitati o se si desidera utilizzare la propria logica `indexOf()`.

## Installare il plug-in utilizzando i tag in Adobe Experience Platform

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza inList
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Espandi il [!UICONTROL Configure tracking using custom code] pannello a soffietto, che mostra il pulsante [!UICONTROL Open Editor] .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: inList v3.0 */
function inList(lv,vtc,d,cc){var b=lv,e=vtc,c=d,f=cc;if("-v"===b)return{plugin:"inList",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var d;a<window.s_c_il.length;a++)if(d=window.s_c_il[a],d._c&&"s_c"===d._c){a=d;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.inList="3.0");if("string"!==typeof e)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==f&&e===b[c]||e.toLowerCase()===b[c].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La funzione `inList` restituisce un valore booleano in base ai relativi input. Utilizza i seguenti argomenti:

* **`lv`** (obbligatorio, stringa o matrice): Un elenco delimitato di valori o un oggetto array JavaScript da cercare
* **`vtc`** (obbligatorio, stringa): Valore da cercare
* **`d`** (facoltativo, stringa): Il delimitatore utilizzato per separare i singoli valori nell’ `lv` argomento. Se non è impostato, viene impostata automaticamente una virgola (`,`).
* **`cc`** (facoltativo, booleano): Se è impostato su  `true` o  `1`, viene effettuato un controllo con distinzione tra maiuscole e minuscole. Se è impostato su `false` o omesso, viene effettuato un controllo senza distinzione tra maiuscole e minuscole. Predefinito su `false`.

Una chiamata a questa funzione restituisce `true` se trova una corrispondenza e `false` se non trova una corrispondenza.

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

* È stata aggiunta l’opzione per l’argomento `cc` che non è booleano. Ad esempio, `1` è un valore di controllo maiuscole/minuscole valido.

### v2.0 (17 aprile 2018)

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).

### v1.01 (27 settembre 2017)

* Codice ottimizzato per ridurre le dimensioni

### v1.0 (2009)

* Versione iniziale.
