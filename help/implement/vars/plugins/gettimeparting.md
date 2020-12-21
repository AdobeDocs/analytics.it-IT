---
title: getTimeParting
description: Misurare il tempo in cui avviene un'azione specifica.
translation-type: tm+mt
source-git-commit: c56891495b610ae14b0341e6a8e64edd115ae105
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%

---


#  plug-in di Adobe: getTimeParting

>[!IMPORTANT]
>
>Questo plug-in è fornito da  Adobe Consulting come una cortesia per aiutarvi a ottenere più valore da  Adobe Analytics. &#39;Assistenza clienti di Adobe non fornisce supporto con questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il plug-in `getTimeParting` consente di acquisire i dettagli del momento in cui si svolge un&#39;attività misurabile sul sito. Questo plug-in è utile per suddividere le metriche in base a una suddivisione ripetibile del tempo in un dato intervallo di date. Ad esempio, è possibile confrontare i tassi di conversione tra due giorni diversi della settimana, ad esempio tutti i giorni di domenica rispetto a tutti i giovedì. È inoltre possibile confrontare i periodi del giorno, ad esempio tutte le mattine rispetto a tutte le serate.

 Analysis Workspace fornisce dimensioni simili e pronte all&#39;uso, formattate in modo leggermente diverso rispetto a questo plug-in. Per ulteriori informazioni, vedere [suddivisione delle dimensioni](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) nella guida utente Analisi. Alcune organizzazioni ritengono che  dimensioni pronte all&#39;uso di Analysis Workspace siano sufficienti.

>[!IMPORTANT]
>
>La versione 4.0+ di questo plug-in è notevolmente diversa dalle versioni precedenti.  Adobe consiglia vivamente di implementare questo plug-in &quot;da zero&quot;. Il codice che fa riferimento al plug-in prima della versione 4.0 non è compatibile con la versione corrente del plug-in.

>[!IMPORTANT]
>
>Le versioni precedenti di questo plug-in non erano compatibili con tutti gli anni futuri. Se utilizzate una versione precedente di questo plug-in,  Adobe consiglia vivamente di effettuare l&#39;aggiornamento alla versione più recente per evitare errori JavaScript e perdita di dati. Se l&#39;aggiornamento di questo plug-in non è possibile, accertatevi che la variabile `s._tpdst` nel codice del plug-in contenga gli anni appropriati in futuro. Questa variabile non è presente o necessaria nell&#39;ultima versione del plug-in.

## Installare il plug-in utilizzando l&#39;estensione Adobe Experience Platform Launch 

 Adobe offre un&#39;estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installare e pubblicare l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo avete già fatto, create una regola con l&#39;etichetta &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (Page Top)
1. Aggiungete un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Initialize getTimeParting
1. Salvate e pubblicate le modifiche alla regola.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics .
1. Espandere il [!UICONTROL Configure tracking using custom code] Accordion, che mostra il pulsante [!UICONTROL Open Editor].
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche all&#39;estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento di Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenendo i commenti e i numeri di versione del codice nell’implementazione,  Adobe può risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il metodo `getTimeParting` utilizza il seguente argomento:

**`t`** (Stringa opzionale ma consigliata): Nome del fuso orario in cui convertire l’ora locale del visitatore.  Il valore predefinito è UTC/GMT. Per un elenco completo dei valori validi, vedere [Elenco dei fusi orari del database TZ](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) su Wikipedia.

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

Il Ghana si trova entro il fuso orario UTC/GMT. Questo esempio mostra che non è necessario alcun argomento plug-in per UTC/GMT.

### Contabilità dei browser Internet Explorer

Per escludere la suddivisione in base al tempo dei dati dai visitatori di Internet Explorer, utilizzate il seguente esempio. Il valore restituito dai browser IE è solo nell&#39;ora locale del visitatore.

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Risultati delle chiamate

Considerate uno scenario in cui un visitatore da Denver Colorado visita un sito il 31 agosto 2020 alle 9:15.

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

### 6.2 (5 novembre 2019)

* Correzioni di bug di piccole dimensioni
* Dimensioni complessive del codice ridotte

### 6.1 (26 novembre 2018)

* Correzione per i browser Internet Explorer. Possono restituire l’ora, ma solo nell’ora locale del visitatore.

### 6.0 (14 agosto 2018)

* Riscrittura completa per soddisfare gli standard internazionali. Ora converte in modo appropriato il risparmio di luce diurna e tutti i fusi orari.

### 5.0 (17 aprile 2018)

* Rilascio punto (ricompilato, dimensioni del codice più piccole)
* È stata rimossa la necessità del parametro `tpDST`, dal momento che le date di inizio/fine dei risparmi di giorno ora vengono rilevate automaticamente

### 4.0 (22 agosto 2016)

* Offre una soluzione completamente nuova che ora include informazioni su anno, mese e data.
