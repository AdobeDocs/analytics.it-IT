---
title: getVisitNum
description: Tieni traccia del numero di visita corrente di un visitatore.
feature: Variables
exl-id: 05b3f57c-7268-4585-a01e-583f462ff8df
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 0%

---

# Plug-in di Adobe: getVisitNum

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

La `getVisitNum` Il plug-in restituisce il numero di visite per tutti i visitatori che accedono al sito entro il numero di giorni desiderato. Analysis Workspace offre una dimensione &quot;Numero visita&quot; che fornisce funzionalità simili. L’Adobe consiglia di utilizzare questo plug-in se desideri un maggiore controllo sulla modalità di incremento del numero di visite. Questo plug-in non è necessario se la dimensione &quot;Numero visita&quot; integrata in Analysis Workspace è sufficiente per le tue esigenze di reporting.

## Installare il plug-in utilizzando l’SDK per web o l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installa e pubblica il [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza getVisitNum
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getVisitNum v4.2 */
function getVisitNum(rp,erp){var a=rp,l=erp;function m(c){return isNaN(c)?!1:(parseFloat(c)|0)===parseFloat(c)}function n(c){var b=new Date,e=isNaN(c)?0:Math.floor(c);b.setHours(23);b.setMinutes(59);b.setSeconds(59);"w"===c&&(e=6-b.getDay());if("m"===c){e=b.getMonth()+1;var a=b.getFullYear();e=(new Date(a?a:1970,e?e:1,0)).getDate()-b.getDate()}b.setDate(b.getDate()+e);"y"===c&&(b.setMonth(11),b.setDate(31));return b}if("-v"===a)return{plugin:"getVisitNum",version:"4.2"};var f=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof f&&(f.contextData.getVisitNum="4.2");window.cookieWrite=window.cookieWrite||function(c,b,e){if("string"===typeof c){var a=window.location.hostname,d=window.location.hostname.split(".").length-1;if(a&&!/^[0-9.]+$/.test(a)){d=2<d?d:2;var h=a.lastIndexOf(".");if(0<=h){for(;0<=h&&1<d;)h=a.lastIndexOf(".",h-1),d--;h=0<h?a.substring(h):a}}g=h;b="undefined"!==typeof b?""+b:"";if(e||""===b)if(""===b&&(e=-60),"number"===typeof e){var f=new Date;f.setTime(f.getTime()+6E4*e)}else f=e;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(e?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:365;l="undefined"!==typeof l?!!l:m(a)?!0:!1;var p=(new Date).getTime();f=n(a);if(window.cookieRead("s_vnc"+a))var d=window.cookieRead("s_vnc"+a).split("&vn="),k=d[1];if(window.cookieRead("s_ivc"))return k?(window.cookieWrite("s_ivc",!0,30),k):"unknown visit number";if("undefined"!==typeof k)return k++,d=l&&m(a)?p+864E5*a:d[0],f.setTime(d),window.cookieWrite("s_vnc"+a,d+"&vn="+k,f),window.cookieWrite("s_ivc",!0,30),k;d=m(a)?p+864E5*a:n(a).getTime();window.cookieWrite("s_vnc"+a,d+"&vn=1",f);window.cookieWrite("s_ivc",!0,30);return"1"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `getVisitNum` La funzione utilizza i seguenti argomenti:

* **`rp`** (facoltativo, stringa OR intera): Il numero di giorni prima della reimpostazione del contatore del numero di visita.  Predefinito su `365` quando non è impostato.
   * Quando questo argomento è `"w"`, il contatore riprende alla fine della settimana (questo sabato alle 11:59)
   * Quando questo argomento è `"m"`, il contatore viene reimpostato alla fine del mese (l’ultimo giorno del mese)
   * Quando questo argomento è `"y"`, il contatore riprende alla fine dell&#39;anno (31 dicembre)
* **`erp`** (facoltativo, booleano): Quando il `rp` argomento è un numero, questo argomento determina se la scadenza del numero di visita deve essere estesa. Se impostato su `true`, gli hit successivi al sito reimpostano il contatore dei numeri di visita. Se impostato su `false`, gli hit successivi al sito non si estendono quando il contatore del numero di visite viene reimpostato. Predefinito su `true`. Questo argomento non è valido quando `rp` argomento è una stringa.

Il numero di visite aumenta ogni volta che il visitatore ritorna al tuo sito dopo 30 minuti di inattività. Una chiamata a questa funzione restituisce un numero intero che rappresenta il numero di visita corrente del visitatore.

Questo plug-in imposta un cookie di prime parti denominato `"s_vnc[LENGTH]"` dove `[LENGTH]` è il valore trasmesso in `rp` argomento. Ad esempio: `"s_vncw"`, `"s_vncm"`oppure `"s_vnc365"`. Il valore del cookie è una combinazione di un timestamp Unix che rappresenta quando il contatore di visite viene reimpostato, come la fine della settimana, la fine del mese o dopo 365 giorni di inattività. Contiene anche il numero della visita corrente. Questo plug-in imposta un altro cookie denominato `"s_ivc"` è impostato su `true` e scade dopo 30 minuti di inattività.

## Esempi

```js
// Sets prop4 to the visit number, storing the value in a cookie that expires in 365 days
// The cookie value is reset only if there are 365+ days of inactivity or the visitor clears their cookies.
s.prop4 = getVisitNum();

// Sets eVar4 to the visit number, storing the value in a cookie that expires in 200 days
// The cookie value is reset only if there are 200+ days of inactivity or the visitor clears their cookies.
s.eVar4 = getVisitNum(200);

// Sets eVar16 to the visit number, storing the value in a cookie that expires in 90 days.
// The cookie value is reset after 90 days, regardless of how many visits that happen in those 90 days.
s.eVar16 = getVisitNum(90,false);

// Track the visit number unique to the week, month, and year, all in separate variables
// The plug-in automatically creates three separate cookies to track these values
s.prop1 = getVisitNum("w");
s.prop2 = getVisitNum("m");
s.prop3 = getVisitNum("y");
```

## Cronologia versioni

### 4.2 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 4.11 (30 settembre 2019)

* È stato risolto un problema che causava la `erp` argomento impostato esplicitamente su `false`.

### 4.1 (21 maggio 2018)

* È stato aggiornato il `endOfDatePeriod` plug-in alla versione 1.1.

### 4.0 (17 aprile 2018)

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).
* Sono stati rimossi gli argomenti dei cookie poiché il plug-in ora genera in modo dinamico i cookie in base ai `rp` argomento)

### 3.0 (5 giugno 2016)

* Revisione completa
* Tutte le soluzioni precedenti disponibili in varie versioni di `getVisitNum` plug-in.
