---
title: getTimeParting
description: Misura il tempo in cui viene eseguita un’azione specifica.
feature: Variables
exl-id: 3fab36c8-a006-405a-9ef1-2547c2b36b0d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 6%

---

# Plug-in di Adobe: getTimeParting

{{plug-in}}

Il `getTimeParting` Il plug-in consente di acquisire i dettagli del momento in cui si verifica un’attività misurabile sul sito. Questo plug-in è utile quando desideri suddividere le metriche in base a qualsiasi divisione di tempo ripetibile in un determinato intervallo di date. Ad esempio, puoi confrontare i tassi di conversione tra due giorni diversi della settimana, ad esempio tutte le domeniche e tutti i giovedì. Puoi anche confrontare periodi della giornata, ad esempio tutte le mattine rispetto a tutte le sere.

Analysis Workspace fornisce dimensioni predefinite simili, formattate in modo leggermente diverso rispetto a questo plug-in. Consulta [dimensioni suddivise in base al tempo](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) nella guida utente Analizza per ulteriori informazioni. Alcune organizzazioni ritengono che le dimensioni predefinite di Analysis Workspace siano sufficienti.

>[!IMPORTANT]
>
>La versione 4.0+ di questo plug-in è significativamente diversa dalle versioni precedenti. L’Adobe consiglia vivamente di implementare questo plug-in &quot;da zero&quot;. Il codice che fa riferimento al plug-in precedente alla versione 4.0 non è compatibile con la versione corrente del plug-in.

## Installare il plug-in utilizzando l’estensione Web SDK

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Web SDK.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Clic **[!UICONTROL Tags]** a sinistra, fai clic sulla proprietà tag desiderata.
1. Clic **[!UICONTROL Extensions]** a sinistra, quindi fai clic su **[!UICONTROL Catalog]** scheda
1. Individuare e installare **[!UICONTROL Common Web SDK Plugins]** estensione.
1. Clic **[!UICONTROL Data Elements]** a sinistra, quindi fai clic sull’elemento dati desiderato.
1. Imposta il nome dell’elemento dati desiderato con la seguente configurazione:
   * Estensione: Common Web SDK Plugins
   * Elemento dati: `getTimeParting`
1. Imposta il `Time Zone` parametro a destra.
1. Salva e pubblica le modifiche apportate all’elemento dati.

## Installare manualmente il plug-in implementando Web SDK

Questo plug-in non è ancora supportato per l’utilizzo in un’implementazione manuale dell’SDK per web.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sul pulsante [!UICONTROL Catalog] pulsante
1. Installare e pubblicare [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Initialize Plug-ins&quot; (Inizializza plug-in) con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Library Loaded (Page Top)
1. Aggiungi un’azione alla regola precedente con la seguente configurazione:
   * Estensione: Common Analytics Plugins
   * Tipo azione: inizializzare getTimeParting
1. Salva e pubblica le modifiche apportate alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sulla scheda **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi [!UICONTROL Configure tracking using custom code] Pannello a soffietto, che mostra [!UICONTROL Open Editor] pulsante.
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file di AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento di Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta ad Adobe nella risoluzione di eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.3 (No Prerequisites Needed) */
function getTimeParting(t){var c=t;if("-v"===t)return{plugin:"getTimeParting",version:"6.3"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getTimeParting="6.3");c=document.documentMode?void 0:c||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:c,minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getTimeParting` La funzione utilizza l&#39;argomento seguente:

**`t`** (Facoltativo ma consigliato, stringa): nome del fuso orario in cui convertire l’ora locale del visitatore.  Ora UTC/GMT predefinita. Consulta [Elenco dei fusi orari del database TZ](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) su Wikipedia per un elenco completo dei valori validi.

I valori validi comuni includono:

* `"America/New_York"` per l’ora orientale
* `"America/Chicago"` per l’ora centrale
* `"America/Denver"` per fuso occidentale
* `"America/Los_Angeles"` per l’ora Pacifico

Quando si richiama questa funzione, viene restituita una stringa contenente i seguenti elementi delimitati da una barra verticale (`|`):

* L&#39;anno corrente
* Il mese corrente
* Il giorno del mese
* Il giorno della settimana
* Ora corrente (AM/PM)

## Esempi

```js
// Use the following code if the visitor resides in Paris, France
s.eVar8 = getTimeParting("Europe/Paris");

// Use the following code if the visitor resides in San Jose, California
s.eVar17 = getTimeParting("America/Los_Angeles");

// Use the following code if the visitor resides in Ghana.
// Note that Ghana is in GMT time, the default time zone that the plug-in uses with no argument
s.eVar22 = getTimeParting();

// Internet Explorer only returns the visitor's local time. Use this conditional statement to accommodate IE visitors
if(!document.documentMode) s.eVar39 = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";

// Given a visitor from Denver Colorado visits a site on August 31, 2020 at 9:15 AM
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"
s.eVar10 = getTimeParting("Europe/Athens");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"
s.eVar11 = getTimeParting("America/Nome");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"
s.eVar12 = getTimeParting("Asia/Calcutta");

// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
s.eVar13 = getTimeParting("Australia/Sydney");
```

## Cronologia versioni

### 6.3 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 6.2 (5 novembre 2019)

* Correzioni di piccoli bug
* Dimensione totale del codice ridotta

### 6.1 (26 novembre 2018)

* Correzione per i browser Internet Explorer. Possono restituire l’ora, ma solo nell’ora locale del visitatore.

### 6.0 (14 agosto 2018)

* Riscrittura completa per soddisfare gli standard internazionali. Ora converte in modo appropriato l&#39;ora legale e tutti i fusi orari.

### 5.0 (17 aprile 2018)

* Versione punto (ricompilato, con codice di dimensioni inferiori)
* È stata eliminata la necessità di `tpDST` , poiché le date di inizio/fine dell&#39;ora legale vengono rilevate automaticamente

>[!CAUTION]
>
>Le versioni precedenti di questo plug-in non includevano tutti gli anni a venire. Se utilizzi una versione precedente di questo plug-in, Adobe consiglia vivamente di eseguire l’aggiornamento alla versione più recente per evitare errori JavaScript e perdite di dati. Se l&#39;aggiornamento di questo plug-in non è fattibile, verificare che `s._tpdst` nel codice del plug-in contiene gli anni appropriati per il futuro.

### 4.0 (22 agosto 2016)

* Fornisce una nuova soluzione e ora include informazioni su anno, mese e data.
