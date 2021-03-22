---
title: getPercentPageViewed
description: Recupera la percentuale della pagina visualizzata dal visitatore.
translation-type: tm+mt
source-git-commit: f11ad012756b5d42b1b53483c8688e30b4b79c83
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---


# Plug-in di Adobe: getPercentPageViewed

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getPercentPageViewed` misura l’attività di scorrimento di un visitatore per vedere la quantità di pagina visualizzata prima di passare a un’altra pagina. Questo plug-in non è necessario se le pagine sono di piccole dimensioni o se non desideri misurare l’attività di scorrimento.

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
   * Tipo azione: Inizializza getPercentPageViewed
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato di Launch

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
/* Adobe Consulting Plugin: getPercentPageViewed v5.0 w/handlePPVevents helper function (Requires AppMeasurement and the p_fo plugin) */
function getPercentPageViewed(pid,ch){var l=pid,p=ch;function m(){if(window.ppvID){var c=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,k=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,a=Math.min(Math.round(k/c*100),100),n=Math.floor(k/b);b=Math.floor(c/b);var d="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&c!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",k);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");d=window.cookieRead("s_ppv");var f=-1<d.indexOf(",")?d.split(","):[];d=f[0]?f[0]:"";f=f[3]?f[3]:"";var e=window.cookieRead("s_ips");d=d+","+Math.round(f/c*100)+","+Math.round(e/c*100)+","+f+","+n}window.cookieWrite("s_tp",c)}else d=window.cookieRead("s_ppv");var h=d&&-1<d.indexOf(",")?d.split(",",6):[];c=0<h.length?h[0]:escape(window.ppvID);f=1<h.length?parseInt(h[1]):a;e=2<h.length?parseInt(h[2]):a;var l=3<h.length?parseInt(h[3]):k,m=4<h.length?parseInt(h[4]):n;h=5<h.length?parseInt(h[5]):b;0<a&&(d=c+","+(a>f?a:f)+","+e+","+(k>l?k:l)+","+(n>m?n:m)+","+(b>h?b:h));window.cookieWrite("s_ppv",d)}}if("-v"===l)return{plugin:"getPercentPageViewed",version:"5.0"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPercentPageViewed="5.0");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(c,b,a){if("string"===typeof c){var k=window.location.hostname,e=window.location.hostname.split(".").length-1;if(k&&!/^[0-9.]+$/.test(k)){e=2<e?e:2;var d=k.lastIndexOf(".");if(0<=d){for(;0<=d&&1<e;)d=k.lastIndexOf(".",d-1),e--;d=0<d?k.substring(d):k}}g=d;b="undefined"!==typeof b?""+b:"";if(a||""===b)if(""===b&&(a=-60),"number"===typeof a){var f=new Date;f.setTime(f.getTime()+6E4*a)}else f=a;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(a?" expires="+f.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,c=b.indexOf(" "+a+"="),e=0>c?c:b.indexOf(";",c);return(a=0>c?"":decodeURIComponent(b.substring(c+2+a.length,0>e?b.length:e)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var a=window.cookieRead("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];l=l?l:window.pageName?window.pageName:document.location.href;a[0]=decodeURIComponent(a[0]);window.ppvChange="undefined"===typeof p||1==p?!0:!1;"undefined"!==typeof e&&e.linkType&&"o"===e.linkType||(window.ppvID&&window.ppvID===l||(window.ppvID=l,window.cookieWrite("s_ppv",""),m()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",m,!1),window.addEventListener("click",m,!1),window.addEventListener("scroll",m,!1)),window._ppvPreviousPage=a[0]?a[0]:"",window._ppvHighestPercentViewed=a[1]?a[1]:"",window._ppvInitialPercentViewed=a[2]?a[2]:"",window._ppvHighestPixelsSeen=a[3]?a[3]:"",window._ppvFoldsSeen=a[4]?a[4]:"",window._ppvFoldsAvailable=a[5]?a[5]:"")};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getPercentPageViewed` utilizza i seguenti argomenti:

* **`pid`** (facoltativo, stringa): Un identificatore basato sulla pagina può essere correlato alle percentuali fornite dalle misurazioni del plug-in.  Predefinito per la variabile `pageName`.
* **`ch`** (facoltativo, booleano): Imposta questo su  `false` (o  `0`) se non desideri che il plug-in tenga conto di eventuali modifiche apportate alle dimensioni di una pagina dopo il suo caricamento iniziale. Se omesso, questo argomento viene impostato automaticamente su `true`. L&#39;Adobe consiglia di omettere questo argomento nella maggior parte dei casi.

La chiamata di questo metodo non restituisce alcun risultato; imposta invece le seguenti variabili:

* `s._ppvPreviousPage`: Nome della pagina precedente visualizzata. Le misure di scorrimento finali per la pagina corrente non sono disponibili fino al caricamento di una nuova pagina.
* `s._ppvHighestPercentViewed`: La percentuale più alta della pagina precedente visualizzata dal visitatore (in base all’altezza). Il punto più avanzato su cui il visitatore ha effettuato lo scorrimento nella pagina precedente.
* `s._ppvInitialPercentViewed`: La percentuale della pagina precedente visibile al primo caricamento della pagina precedente.
* `s._ppvHighestPixelsSeen`: Il numero più alto di pixel totali visualizzati (in altezza) mentre il visitatore scorreva verso il basso la pagina precedente.
* `s._ppvFoldsSeen`: Il numero più alto di &quot;pieghe di pagina&quot; raggiunto quando il visitatore ha fatto scorrere la pagina precedente. Questa variabile include la piega &quot;inizio pagina&quot;.
* `s._ppvFoldsAvailable`: Il numero di &quot;pieghe di pagina&quot; totali disponibili per scorrere verso il basso nella pagina precedente.

Assegna una o più di queste variabili a eVar per visualizzare i dati delle dimensioni nei rapporti.

Questo plug-in crea un cookie di prime parti denominato `s_ppv` che contiene i valori sopra indicati. scade alla fine della sessione del browser.

## Chiamate di esempio

### Esempio n. 1

Codice seguente...

```js
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " + | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
}
```

* Determina se s.pageName è impostato e, in tal caso, eseguirà la funzione getPercentPageViewed
* Quando viene eseguita la funzione getPercentPageViewed, vengono create le variabili descritte nella sezione &quot;Restituisce&quot; di cui sopra
* Se le variabili &quot;Restituisce&quot; sono state impostate correttamente:
   * Il codice imposta s.prop1 uguale al valore di s._ppvPreviousPage (ovvero il valore precedente di s.pageName o la pagina precedente)
   * Il codice imposta anche s.prop2 uguale alla percentuale più alta visualizzata della pagina precedente e alla percentuale iniziale visualizzata della pagina precedente, insieme al numero di cartelle raggiunte dal visitatore e al numero di cartelle disponibili

**Nota**: Se un’intera pagina è visibile al primo caricamento, sia la percentuale di visualizzazione più alta che la percentuale di visualizzazione iniziale saranno uguali a 100, sia le pieghe visualizzate che le pieghe disponibili saranno uguali a 1.   Quando un’intera pagina NON è visibile al primo caricamento ma il visitatore non finisce mai per scorrere la pagina prima di passare alla pagina successiva, sia la percentuale più alta visualizzata che la percentuale iniziale visualizzata saranno uguali allo stesso valore.

### Esempio n. 2

Supponiamo che s.prop5 sia stato impostato per acquisire un &quot;tipo di pagina&quot; rollup anziché l’intero nome della pagina.

Il codice seguente determina se s.prop5 è stato impostato e, in tal caso, ne memorizzerà il valore come &quot;pagina precedente&quot; in correlazione con le dimensioni Percentuale più alta visualizzata e Percentuale iniziale visualizzata.  Il valore sarà comunque memorizzato nella variabile s._ppvPreviousPage ma può essere trattato come se fosse il tipo di pagina precedente invece del nome pagina precedente.

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## Cronologia versioni

### 5.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### v4.0 (7 ottobre 2019)

* Aggiunte soluzioni `s._ppvFoldsSeen` e `s._ppvFoldsAvailable`

### v3.01 (13 agosto 2018)

* È stato risolto un problema per le pagine che hanno più oggetti AppMeasurement in una pagina

### v3.0 (13 aprile 2018)

* Rilascio a punti (ricompilato, dimensioni del codice più piccole)
* Il plug-in ora crea variabili da assegnare alle variabili di Adobe Analytics anziché valori restituiti
