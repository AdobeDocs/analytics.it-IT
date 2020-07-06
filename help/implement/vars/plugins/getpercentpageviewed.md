---
title: getPercentPageViewed
description: Recuperate la percentuale della pagina visualizzata dal visitatore.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 0%

---


# Plug-in Adobe: getPercentPageViewed

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getPercentPageViewed` plug-in misura l&#39;attività di scorrimento di un visitatore per vedere la quantità di pagina visualizzata prima di passare a un&#39;altra pagina. Questo plug-in non è necessario se le pagine sono piccole in altezza o se non si desidera misurare l&#39;attività di scorrimento.

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
/* Adobe Consulting Plugin: getPercentPageViewed v4.0 w/handlePPVevents helper function (Requires p_fo plug-in) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange="undefined"===typeof ch||!0==ch?!0:!1;if("undefined"=== typeof s.linkType||"o"!==s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()), s.p_fo("s_gppvLoad") &&window.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1)),s._ppvPreviousPage=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:"",s._ppvFoldsSeen=a[4]?a[4]:"",s._ppvFoldsAvailable=a[5]?a[5]:""};

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v4.0 Plugin) */
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,g=s_c_il.length;c<g;c++)if(s_c_il[c]&& (s_c_il[c].getPercentPageViewed||s_c_il[c].getPreviousPageActivity)){var s=s_c_il[c];break}if(s&&s.ppvID){var f=Math.max (Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight, document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),h= window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;c=(window.pageYOffset|| window.document.documentElement.scrollTop||window.document.body.scrollTop)+h;g=Math.min(Math.round(c/f*100),100);var k=Math.floor(c/h);h=Math.floor(f/h);var d="";if(!s.c_r("s_tp")||s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID) ||1==s.ppvChange&&s.c_r("s_tp")&&f!=s.c_r("s_tp")){(s.unescape(s.c_r("s_ppv").split(",")[0])!==s.ppvID||s.p_fo(s.ppvID+"1"))&&s.c_w("s_ips",c);if(s.c_r("s_tp")&&s.unescape(s.c_r("s_ppv").split(",")[0])===s.ppvID){s.c_r("s_tp");d=s.c_r("s_ppv");var e=-1< d.indexOf(",")?d.split(","):[];d=e[0]?e[0]:"";e=e[3]?e[3]:"";var l=s.c_r("s_ips");d=d+","+Math.round(e/f*100)+","+Math.round(l/ f*100)+","+e+","+k}s.c_w("s_tp",f)}else d=s.c_r("s_ppv");var b=d&&-1<d.indexOf(",")?d.split(",",6):[];f=0<b.length?b[0]: escape(s.ppvID);e=1<b.length?parseInt(b[1]):g;l=2<b.length?parseInt(b[2]):g;var m=3<b.length?parseInt(b[3]):c,n=4<b.length? parseInt(b[4]):k;b=5<b.length?parseInt(b[5]):h;0<g&&(d=f+","+(g>e?g:e)+","+l+","+(c>m?c:m)+","+(k>n?k:n)+","+(h>b?h:b)); s.c_w("s_ppv",d)}}};

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getPercentPageViewed` metodo utilizza i seguenti argomenti:

* **`pid`** (facoltativo, stringa):  Un identificatore basato sulla pagina può essere correlato alle percentuali fornite dalle misurazioni del plug-in.  Il valore predefinito è la `pageName` variabile.
* **`ch`** (facoltativo, booleano):  Impostate questo valore su `false` (o `0`) se non desiderate che il plug-in tenga conto di eventuali modifiche apportate alle dimensioni di una pagina dopo il caricamento iniziale. Se omesso, l&#39;argomento verrà impostato per impostazione predefinita su `true`. Nella maggior parte dei casi, Adobe consiglia di omettere questo argomento.

La chiamata di questo metodo non restituisce nulla; imposta invece le seguenti variabili:

* `s._ppvPreviousPage`: Nome della pagina visualizzata precedente. Le misure di scorrimento finale per la pagina corrente sono disponibili solo dopo il caricamento di una nuova pagina.
* `s._ppvHighestPercentViewed`: La percentuale più alta della pagina precedente visualizzata dal visitatore (in altezza). Il punto più avanzato su cui il visitatore ha eseguito lo scorrimento verso il basso sulla pagina precedente.
* `s._ppvInitialPercentViewed`: Percentuale della pagina precedente visibile al primo caricamento della pagina precedente.
* `s._ppvHighestPixelsSeen`: Il numero massimo di pixel totali visti (in altezza) dal visitatore che ha fatto scorrere la pagina precedente.
* `s._ppvFoldsSeen`: Il numero più alto di &quot;pieghe di pagina&quot; raggiunto quando il visitatore ha fatto scorrere la pagina precedente. Questa variabile include la piega &quot;inizio pagina&quot;.
* `s._ppvFoldsAvailable`: Il numero totale di &quot;pieghe di pagina&quot; disponibili per scorrere verso il basso sulla pagina precedente.

Assegnare una o più di queste variabili alle eVar per visualizzare i dati delle dimensioni nei report.

Questo plug-in crea un cookie first-party denominato `s_ppv` che contiene i valori indicati sopra. Scade alla fine della sessione del browser.

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

* Determina se s.pageName è impostato e, in tal caso, il codice eseguirà la funzione getPercentPageViewed
* Quando viene eseguita la funzione getPercentPageViewed, verranno create le variabili descritte nella sezione &quot;Restituisce&quot; precedente
* Se le variabili &quot;Restituisce&quot; sono state impostate correttamente:
   * Il codice imposta s.prop1 uguale al valore di s._ppvPreviousPage (ovvero il valore precedente di s.pageName o la pagina precedente)
   * Il codice imposta anche s.prop2 uguale alla percentuale più alta visualizzata della pagina precedente e alla percentuale iniziale visualizzata della pagina precedente, insieme al numero di cartelle raggiunte dal visitatore e al numero di cartelle disponibili

**Nota**:  Se un’intera pagina viene visualizzata al primo caricamento, sia la percentuale massima visualizzata che la percentuale iniziale visualizzata saranno uguali a 100, sia le cartelle visualizzate che le cartelle disponibili saranno uguali a 1.   Quando un&#39;intera pagina NON è visibile quando viene caricata per la prima volta ma il visitatore non scorre mai verso il basso prima di passare alla pagina successiva, sia la percentuale più alta visualizzata che la percentuale iniziale visualizzata saranno uguali allo stesso valore.

### Esempio n. 2

Supponete che s.prop5 sia stato impostato per acquisire un &quot;tipo di pagina&quot; con rollup anziché l’intero nome della pagina.

Il codice seguente determina se s.prop5 è stato impostato e, in tal caso, ne memorizzerà il valore come &quot;pagina precedente&quot; in modo da correlarlo con le dimensioni Visualizzazione percentuale più alta e Percentuale iniziale visualizzata.  Il valore sarà comunque memorizzato nella variabile s._ppvPreviousPage, ma può essere trattato come se fosse il tipo di pagina precedente invece del nome di pagina precedente.

```js
if(s.prop5) s.getPercentPageViewed(s.prop5);
if(s._ppvPreviousPage)
{
  s.prop1 = s._ppvPreviousPage;
  s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}
```

## Cronologia versioni

### v4.0 (7 ottobre 2019)

* Aggiunte `s._ppvFoldsSeen` e `s._ppvFoldsAvailable` soluzioni

### v3.01 (13 agosto 2018)

* È stato risolto un problema per le pagine con più oggetti AppMeasurement in una pagina

### v3.0 (13 aprile 2018)

* Rilascio punto (ricompilato, dimensioni del codice più piccole)
* Il plug-in ora crea variabili da assegnare alle variabili Adobe  Analytics invece dei valori restituiti
