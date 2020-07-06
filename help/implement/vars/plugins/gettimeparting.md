---
title: getTimeParting
description: Misurare il tempo in cui avviene un'azione specifica.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 0%

---


# Plug-in Adobe: getTimeParting

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getTimeParting` plug-in consente di acquisire i dettagli del momento in cui si svolge qualsiasi attività misurabile sul sito. Questo plug-in è utile per suddividere le metriche in base a una suddivisione ripetibile del tempo in un dato intervallo di date. Ad esempio, è possibile confrontare i tassi di conversione tra due giorni diversi della settimana, ad esempio tutti i giorni di domenica rispetto a tutti i giovedì. È inoltre possibile confrontare i periodi del giorno, ad esempio tutte le mattine rispetto a tutte le serate.

 Analysis Workspace fornisce dimensioni simili e pronte all&#39;uso, formattate in modo leggermente diverso rispetto a questo plug-in. Per ulteriori informazioni, consulta la sezione [Suddivisione delle dimensioni](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) nella guida utente Analisi. Alcune organizzazioni ritengono che  dimensioni pronte all&#39;uso di Analysis Workspace siano sufficienti.

>[IMPORTANTE] versione 4.0+ di questo plug-in è notevolmente diversa rispetto alle versioni precedenti. Adobe consiglia vivamente di implementare questo plug-in &quot;da zero&quot;. Il codice che fa riferimento al plug-in prima della versione 4.0 non è compatibile con la versione corrente del plug-in.

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
   * Tipo azione: Initialize getTimeParting
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
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getTimeParting` metodo utilizza l&#39;argomento seguente:

**`t`** (Stringa opzionale ma consigliata): Nome del fuso orario in cui convertire l’ora locale del visitatore.  Il valore predefinito è UTC/GMT. Consulta [Elenco dei fusi orari](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) del database TZ su Wikipedia per un elenco completo dei valori validi.

I valori validi comuni includono:

* `"America/New_York"` per ora orientale
* `"America/Chicago"` per ora centrale
* `"America/Denver"` per il tempo di montagna
* `"America/Los_Angeles"` per Pacific Time

Se si chiama questo metodo, viene restituita una stringa contenente i seguenti elementi delimitati da una pipe (`|`):

* L&#39;anno in corso
* Il mese corrente
* Il giorno del mese
* Il giorno della settimana
* Ora corrente (AM/PM)

## Chiamate di esempio

### Esempi per specifici fusi orari

Utilizzate il seguente codice di esempio se il client si trova a Parigi, Francia:

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

Il Ghana si trova entro il fuso orario UTC/GMT.  Questo esempio mostra che in tali circostanze non sarà necessario alcun argomento plug-in.

### Contabilità dei browser Internet Explorer

Utilizzate l&#39;esempio seguente per escludere la suddivisione in base al tempo dei dati dai visitatori di Internet Explorer (dal momento che il valore restituito dai browser IE può trovarsi solo nell&#39;ora locale del visitatore)

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Risultati delle chiamate

Se un visitatore di Denver visita un sito il 31 agosto 2020 alle 9:15,

Esecuzione del codice seguente in corso...

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

...imposta s.eVar10 su &quot;year=2020 | mese=agosto | date=31 | day=Friday | time=6:15 PM&quot;

Con il seguente codice...

```js
s.eVar10 = getTimeParting("America/Nome");
```

...imposta s.eVar10 su &quot;year=2020 | mese=agosto | date=31 | day=Friday | time=6:15 AM&quot;

Codice seguente...

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

...imposta s.eVar10 su &quot;year=2020 | mese=agosto | date=31 | day=Friday | time=8:45 PM&quot;

E il seguente codice...

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

...imposta s.eVar10 su &quot;year=2020 | mese=settembre | date=1 | giorno=sabato | time=1:15 AM&quot;

## Cronologia versioni

### 6.2 (5 novembre 2019)

* Correzioni di bug di piccole dimensioni
* Dimensioni complessive del codice ridotte

### 6.1 (26 novembre 2018)

* Correzione per i browser Internet Explorer. Possono restituire l’ora, ma solo nell’ora locale del visitatore.

### 6.0 (14 agosto 2018)

* Riscrittura completa per soddisfare gli standard internazionali. Ora converte in modo appropriato il risparmio di luce diurna e tutti i fusi orari.

### 5.0 (17 aprile 2018)

* Rilascio punto (ricompilato, dimensioni del codice più piccole)
* È stata rimossa la necessità del `tpDST` parametro, dal momento che le date di inizio/fine del risparmio diurno vengono ora rilevate automaticamente

### 4.0 (22 agosto 2016)

* Offre una soluzione completamente nuova che ora include informazioni su anno, mese e data.
