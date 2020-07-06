---
title: getVisitNum
description: Monitora il numero di visita corrente di un visitatore.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 0%

---


# Plug-in Adobe: getVisitNum

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getVisitNum` plug-in restituisce il numero di visita per tutti i visitatori che arrivano sul sito entro il numero desiderato di giorni.  Analysis Workspace offre una dimensione &quot;Visit Number&quot; che fornisce funzionalità simili. Adobe consiglia di utilizzare questo plug-in se desiderate maggiore controllo sulla modalità di incremento del numero di visita. Questo plug-in non è necessario se la dimensione integrata &quot;Visit Number&quot; in  Analysis Workspace è sufficiente per le esigenze di reporting.

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
   * Tipo azione: Initialize getVisitNum
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
/* Adobe Consulting Plugin: getVisitNum v4.11 (Requires endOfDatePeriod plug-in) */
s.getVisitNum=function(rp,erp){var s=this,c=function(rp){return isNaN(rp)?!1:(parseFloat(rp)|0)===parseFloat(rp)};rp=rp?rp:365;erp= "undefined"!==typeof erp?!!erp:c(rp)?!0:!1;var e=(new Date).getTime(),b=endOfDatePeriod(rp);if(s.c_r("s_vnc"+rp))var g=s.c_r("s_vnc"+rp).split("&vn="),d=g[1];if(s.c_r("s_ivc"))return d?(b.setTime(e+18E5),s.c_w("s_ivc",!0,b),d):"unknown visit number";if("undefined"!==typeof d)return d++,c=erp&&c(rp)?e+864E5*rp:g[0],b.setTime(c),s.c_w("s_vnc"+rp,c+"&vn="+d,b),b.setTime(e+ 18E5),s.c_w("s_ivc",!0,b),d;c=c(rp)?e+864E5*rp:endOfDatePeriod(rp).getTime();s.c_w("s_vnc"+rp,c+"&vn=1",b);b.setTime(e+18E5); s.c_w("s_ivc",!0,b);return"1"};

/* Adobe Consulting Plugin: endOfDatePeriod v1.1 */
var endOfDatePeriod=function(dp){var a=new Date,b=isNaN(dp)?0:Math.floor(dp);a.setHours(23);a.setMinutes(59);a.setSeconds(59); "w"===dp&&(b=6-a.getDay());if("m"===dp){b=a.getMonth()+1;var d=a.getFullYear();b=(new Date(d?d:1970,b?b:1,0)).getDate()-a.getDate()}a.setDate(a.getDate()+b);"y"===dp&&(a.setMonth(11),a.setDate(31));return a};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getVisitNum` metodo utilizza i seguenti argomenti:

* **`rp`** (facoltativo, numero intero OR stringa): Il numero di giorni prima del ripristino del contatore del numero di visita.  Il valore predefinito è `365` se non è impostato.
   * Quando questo argomento è `"w"`, il contatore si azzera alla fine della settimana (questo sabato alle 11:59)
   * Quando questo argomento è `"m"`impostato, il contatore viene ripristinato alla fine del mese (l&#39;ultimo giorno del mese)
   * Quando questo argomento è `"y"`, il contatore reimposta alla fine dell&#39;anno (31 dicembre)
* **`erp`** (facoltativo, booleano): Quando l&#39; `rp` argomento è un numero, questo argomento determina se la scadenza del numero di visita deve essere estesa. Se impostato su `true`, gli hit successivi al sito reimpostano il contatore dei numeri di visita. Se impostato su `false`, gli hit successivi al sito non si estendono quando il contatore dei numeri di visita viene ripristinato. Il valore predefinito è `true`. Questo argomento non è valido quando l&#39; `rp` argomento è una stringa.

Il numero della visita aumenta ogni volta che il visitatore ritorna al sito dopo 30 minuti di inattività. Se si chiama questo metodo, viene restituito un numero intero che rappresenta il numero di visita corrente del visitatore.

Questo plug-in imposta un cookie di prime parti denominato `"s_vnc[LENGTH]"` dove `[LENGTH]` è il valore passato nell&#39; `rp` argomento. For example, `"s_vncw"`, `"s_vncm"`, or `"s_vnc365"`. Il valore del cookie è una combinazione di una marca temporale Unix che rappresenta il momento in cui il contatore delle visite viene reimpostato, come fine settimana, fine mese o dopo 365 giorni di inattività. Contiene anche il numero della visita corrente. Questo plug-in imposta un altro cookie denominato `"s_ivc"` che viene impostato su `true` e scade dopo 30 minuti di inattività.

## Chiamate di esempio

### Esempio n. 1

Per un visitatore che non è stato sul sito negli ultimi 365 giorni, il codice seguente imposta s.prop1 uguale al valore 1:

```js
s.prop1=s.getVisitNum();
```

### Esempio n. 2

Per un visitatore che ritorna al sito entro 364 giorni dalla sua prima visita, il codice seguente imposta s.prop1 uguale a 2:

```js
s.prop1=s.getVisitNum(365);
```

Se il visitatore torna sul sito entro 364 giorni dalla sua seconda visita, il codice seguente imposta s.prop1 uguale a 3:

```js
s.prop1=s.getVisitNum(365);
```

### Esempio n. 3

Per un visitatore che ritorna sul sito entro 179 giorni dalla sua prima visita, il codice seguente imposta s.prop1 uguale a 2:

```js
s.prop1=s.getVisitNum(180,false);
```

Tuttavia, se il visitatore torna sul sito 1 o più giorni dopo la sua seconda visita, il codice seguente imposta s.prop1 uguale a 1:

```js
s.prop1=s.getVisitNum(180,false);
```

Quando il secondo argomento della chiamata è uguale a falso, la routine che determina quando il numero della visita deve essere &quot;reimpostato&quot; su 1 farà così &quot;x&quot; numero di giorni - in questo esempio, 365 giorni - dopo la prima visita del visitatore al sito.

Quando il secondo argomento è uguale a true (o non è impostato affatto), il plug-in reimposta il numero della visita a 1 solo dopo &quot;x&quot; numero di giorni - di nuovo, in questo esempio, 365 giorni - di inattività del visitatore.

### Esempio n. 4

Per tutti i visitatori che arrivano sul sito per la prima volta durante la settimana corrente - a partire da domenica - il seguente codice imposta s.prop1 uguale a 1:

```js
s.prop1=s.getVisitNum("w");
```

### Esempio n. 5

Per tutti i visitatori che arrivano sul sito per la prima volta durante il mese corrente - a partire dal primo giorno di ogni mese - il codice seguente imposta s.prop1 uguale a 1:

```js
s.prop1=s.getVisitNum("m");
```

Tenete presente che il plug-in getVisitNum non prende in considerazione i calendari basati sulla vendita al dettaglio (ad esempio 4-5-4, 4-4-5, ecc.)

### Esempio n. 6

Per tutti i visitatori che arrivano sul sito per la prima volta durante l&#39;anno corrente - a partire dal 1 gennaio - il codice seguente imposta s.prop1 uguale a 1:

```js
s.prop1=s.getVisitNum("y");
```

### Esempio n. 7

Se desideri tenere traccia del numero di visita di un visitatore per la settimana, del numero di visita di un visitatore per il mese e del numero di visita di un visitatore per l&#39;anno, il tutto all&#39;interno  variabili Analytics diverse, devi usare un codice che assomigli a quanto segue:

```js
s.prop1=s.getVisitNum("w");
s.prop2=s.getVisitNum("m");
s.prop3=s.getVisitNum("y");
```

In questo caso, il plug-in creerà tre diversi cookie - uno per ciascuno dei diversi periodi di tempo - per tenere traccia del singolo numero di visita per periodo di tempo.

## Cronologia versioni

### 4.11 (30 settembre 2019)

* È stato risolto un problema per il quale l&#39; `erp` argomento era impostato esplicitamente su `false`.

### 4.1 (21 maggio 2018)

* È stato aggiornato il `endOfDatePeriod` plug-in alla versione 1.1.

### 4.0 (17 aprile 2018)

* Rilascio punto (ricompilato, dimensioni del codice più piccole).
* Sono stati rimossi gli argomenti dei cookie poiché il plug-in ora genera dinamicamente i cookie in base all&#39; `rp` argomento)

### 3.0 (5 giugno 2016)

* Completa revisione
* Combinate tutte le soluzioni precedenti disponibili in varie versioni del `getVisitNum` plug-in.
