---
title: getTimeParting
description: Misura il momento in cui avviene un’azione specifica.
translation-type: tm+mt
source-git-commit: 97778ee83cd44eaf2d14dd3e6891612eb99744a9
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---


# Plug-in di Adobe: getTimeParting

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getTimeParting` ti consente di acquisire i dettagli del momento in cui si verifica un’attività misurabile sul tuo sito. Questo plug-in è utile quando desideri suddividere le metriche in base a una suddivisione ripetibile del tempo su un determinato intervallo di date. Ad esempio, puoi confrontare i tassi di conversione tra due giorni della settimana diversi, ad esempio tutti i giorni della domenica rispetto a tutti i giovedì. Puoi anche confrontare i periodi del giorno, ad esempio tutte le mattine rispetto a tutte le serate.

Analysis Workspace fornisce dimensioni predefinite simili e formattate in modo leggermente diverso rispetto a questo plug-in. Per ulteriori informazioni, consulta [Suddividere le dimensioni in base al tempo](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) nella guida utente Analisi . Alcune organizzazioni ritengono sufficienti le dimensioni predefinite di Analysis Workspace.

>[!IMPORTANT]
>
>La versione 4.0+ di questo plug-in è molto diversa dalle versioni precedenti. L&#39;Adobe consiglia vivamente di implementare questo plug-in &quot;da zero&quot;. Il codice che fa riferimento al plug-in prima della versione 4.0 non è compatibile con la versione corrente di questo plug-in.

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
   * Tipo azione: Inizializza getTimeParting
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
/* Adobe Consulting Plugin: getTimeParting v6.3 (No Prerequisites Needed) */
function getTimeParting(t){var c=t;if("-v"===t)return{plugin:"getTimeParting",version:"6.3"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getTimeParting="6.3");c=document.documentMode?void 0:c||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:c,minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getTimeParting` utilizza il seguente argomento:

**`t`** (Facoltativo ma consigliato, stringa): Nome del fuso orario in cui convertire l’ora locale del visitatore.  Impostazione predefinita per l’ora UTC/GMT. Per un elenco completo dei valori validi, vedere [Elenco dei fusi orari del database TZ](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) su Wikipedia.

I valori validi comuni includono:

* `"America/New_York"` per l&#39;ora orientale
* `"America/Chicago"` per l&#39;ora centrale
* `"America/Denver"` per l&#39;ora di montagna
* `"America/Los_Angeles"` per l&#39;ora del Pacifico

Quando si chiama questo metodo, viene restituita una stringa contenente i seguenti elementi delimitati da una tubazione (`|`):

* L&#39;anno in corso
* Il mese in corso
* Il giorno del mese
* Il giorno della settimana
* Ora attuale (AM/PM)

## Chiamate di esempio

### Esempi per specifici fusi orari

Utilizza il seguente codice di esempio se il cliente è a Parigi, Francia:

```js
s.eVarX = getTimeParting("Europe/Paris");
```

Se il cliente si trova a San Jose, California:

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

Se il cliente si trova nel paese africano del Ghana:

```js
s.eVarX = getTimeParting();
```

Il Ghana si trova entro il fuso orario UTC/GMT. Questo esempio mostra che non è necessario alcun argomento plug-in per UTC/GMT.

### Contabilità dei browser Internet Explorer

Utilizza il seguente esempio se desideri escludere la suddivisione del tempo tra i dati dei visitatori di Internet Explorer. Il valore restituito dai browser IE è solo nell’ora locale del visitatore.

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Risultati delle chiamate

Considera uno scenario in cui un visitatore di Denver Colorado visita un sito il 31 agosto 2020 alle 9:15.

```js
s.eVar10 = getTimeParting("Europe/Athens");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"

s.eVar11 = getTimeParting("America/Nome");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"

s.eVar12 = getTimeParting("Asia/Calcutta");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"

s.eVar13 = getTimeParting("Australia/Sydney");
// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
```

## Cronologia versioni

### 6.3 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 6.2 (5 novembre 2019)

* Correzioni di piccoli bug
* Dimensione complessiva del codice ridotta

### 6.1 (26 novembre 2018)

* Correzione per i browser Internet Explorer. Possono restituire l’ora, ma solo nell’ora locale del visitatore.

### 6.0 (14 agosto 2018)

* Riscrittura completa per soddisfare gli standard internazionali. Ora converte in modo appropriato il risparmio di luce diurna e tutti i fusi orari.

### 5.0 (17 aprile 2018)

* Versione punto (ricompilato, dimensioni del codice più piccole)
* È stata rimossa la necessità del parametro `tpDST`, poiché le date di inizio/fine del risparmio di luce ora vengono rilevate automaticamente

>[!CAUTION]
>
>Le versioni precedenti di questo plug-in non erano compatibili per tutti gli anni futuri. Se utilizzi una versione precedente di questo plug-in, Adobe consiglia vivamente di effettuare l’aggiornamento alla versione più recente per evitare errori JavaScript e perdita di dati. Se l&#39;aggiornamento di questo plug-in non è possibile, assicurati che la variabile `s._tpdst` nel codice del plug-in contenga gli anni appropriati in futuro.

### 4.0 (22 agosto 2016)

* Offre una soluzione nuova e include ora informazioni su anno, mese e data.
