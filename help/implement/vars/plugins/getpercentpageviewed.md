---
title: getPercentPageViewed
description: Recupera la percentuale della pagina visualizzata dal visitatore.
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: 77192bdec509fed0b2a7c49112b7b430ff677a3c
workflow-type: tm+mt
source-wordcount: '892'
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
/* Adobe Consulting Plugin: getPercentPageViewed v5.0.1 */
function getPercentPageViewed(pid,ch){var n=pid,r=ch;function p(){if(window.ppvID){var a=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),b=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,d=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+b,f=Math.min(Math.round(d/a*100),100),l=Math.floor(d/b);b=Math.floor(a/b);var c="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||1==window.ppvChange&&window.cookieRead("s_tp")&&a!=window.cookieRead("s_tp")){(decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",d);if(window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");c=window.cookieRead("s_ppv");var h=-1<c.indexOf(",")?c.split(","):[];c=h[0]?h[0]:"";h=h[3]?h[3]:"";var q=window.cookieRead("s_ips");c=c+","+Math.round(h/a*100)+","+Math.round(q/a*100)+","+h+","+l}window.cookieWrite("s_tp",a)}else c=window.cookieRead("s_ppv");var k=c&&-1<c.indexOf(",")?c.split(",",6):[];a=0<k.length?k[0]:encodeURIComponent(window.ppvID);h=1<k.length?parseInt(k[1]):f;q=2<k.length?parseInt(k[2]):f;var t=3<k.length?parseInt(k[3]):d,u=4<k.length?parseInt(k[4]):l;k=5<k.length?parseInt(k[5]):b;0<f&&(c=a+","+(f>h?f:h)+","+q+","+(d>t?d:t)+","+(l>u?l:u)+","+(b>k?b:k));window.cookieWrite("s_ppv",c)}}if("-v"===n)return{plugin:"getPercentPageViewed",version:"5.0.1"};var m=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof m&&(m.contextData.getPercentPageViewed="5.0.1");window.pageName="undefined"!==typeof m&&m.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,d){if("string"===typeof a){var f=window.location.hostname,l=window.location.hostname.split(".").length-1;if(f&&!/^[0-9.]+$/.test(f)){l=2<l?l:2;var c=f.lastIndexOf(".");if(0<=c){for(;0<=c&&1<l;)c=f.lastIndexOf(".",c-1),l--;c=0<c?f.substring(c):f}}g=c;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var h=new Date;h.setTime(h.getTime()+6E4*d)}else h=d;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+h.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,d=b.indexOf(" "+a+"="),f=0>d?d:b.indexOf(";",d);return(a=0>d?"":decodeURIComponent(b.substring(d+2+a.length,0>f?b.length:f)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};var e=window.cookieRead("s_ppv");e=-1<e.indexOf(",")?e.split(","):[];n=n?n:window.pageName?window.pageName:document.location.href;e[0]=decodeURIComponent(e[0]);window.ppvChange="undefined"===typeof r||1==r?!0:!1;"undefined"!==typeof m&&m.linkType&&"o"===m.linkType||(window.ppvID&&window.ppvID===n||(window.ppvID=n,window.cookieWrite("s_ppv",""),p()),window.p_fo("s_gppvLoad")&&window.addEventListener&&(window.addEventListener("load",p,!1),window.addEventListener("click",p,!1),window.addEventListener("scroll",p,!1)),this._ppvPreviousPage=e[0]?e[0]:"",this._ppvHighestPercentViewed=e[1]?e[1]:"",this._ppvInitialPercentViewed=e[2]?e[2]:"",this._ppvHighestPixelsSeen=e[3]?e[3]:"",this._ppvFoldsSeen=e[4]?e[4]:"",this._ppvFoldsAvailable=e[5]?e[5]:"")};
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
  s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed + " | foldsSeen=" + s._ppvFoldsSeen + " | foldsAvailable=" + s._ppvFoldsAvailable;
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

### 5.0.1 (22 giugno 2021)

* È stato risolto un problema a causa del quale alcuni caratteri speciali causavano l’interruzione del plug-in.

### 5.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### v4.0 (7 ottobre 2019)

* Aggiunte soluzioni `s._ppvFoldsSeen` e `s._ppvFoldsAvailable`

### v3.01 (13 agosto 2018)

* È stato risolto un problema per le pagine che hanno più oggetti AppMeasurement in una pagina

### v3.0 (13 aprile 2018)

* Rilascio a punti (ricompilato, dimensioni del codice più piccole)
* Il plug-in ora crea variabili da assegnare alle variabili di Adobe Analytics anziché valori restituiti
