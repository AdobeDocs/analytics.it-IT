---
description: Misura l'attività di scorrimento di un visitatore per vedere la quantità di pagina visualizzata prima di passare a un'altra pagina. Questo plug-in consente di determinare il volume di contenuto visualizzato dagli utenti in medie, in modo da ottimizzare le lunghezze di pagina e i layout in base ai comportamenti utente.
keywords: Implementazione di Analytics
seo-description: Misura l'attività di scorrimento di un visitatore per vedere la quantità di pagina visualizzata prima di passare a un'altra pagina. Questo plug-in consente di determinare il volume di contenuto visualizzato dagli utenti in medie, in modo da ottimizzare le lunghezze di pagina e i layout in base ai comportamenti utente.
seo-title: Getpercentpageviewed
solution: Analytics
subtopic: Plug-in
title: Getpercentpageviewed
topic: Sviluppatore e implementazione
uuid: 1751 dcdb -699 f -4 bd 1-8 bcb -5 e 62 fa 24896 a
translation-type: tm+mt
source-git-commit: f9912a0da5930be965e4d249f3d2c1891cfd6ed6

---


# Getpercentpageviewed

Il plug-plugin getpercentpageviewed misura l'attività di scorrimento di un visitatore per vedere la quantità di pagina visualizzata dal visitatore prima di passare a un'altra pagina.

>[!NOTE]
>Non è necessario utilizzare il plug-plugin getpercentpagevisualizzato se le pagine Web sono di dimensioni ridotte e non è necessario misurare il livello di scorrimento verso il basso dei visitatori. Inoltre, se desiderate misurare l'attività di scorrimento solo sulle pagine di uscita, non potete utilizzare questo plug-in.

## Prerequisiti

Per eseguire il plug-plugin getpercentpageviewed, devi avere appmeasurement e il plugin handleppvevents.

## Implementazione

To implement this plugin, copy and paste the code to anywhere within the **[!UICONTROL Plugins]** section of the [!DNL AppMeasurement] file.

>[!NOTE]
>L'aggiunta di commenti/numeri di versione del codice al file appmeasurement aiuta Adobe Consulting a risolvere eventuali problemi di implementazione potenziali.

You can run the `getPercentPageViewed` function as needed within the doPlugins function (see example calls below.)

## Argomenti da trasmettere

| Argomento | Definizione |
|---|---|
| pid (facoltativo, stringa) | Identificatore di pagina correlato alle percentuali fornite dalle misure del plug-in. Per impostazione predefinita, viene utilizzata la variabile Analytics pagename o l'URL se la variabile pagename non è impostata |
| ch (facoltativo, booleano) | " True "è il valore consigliato/predefinito per questo argomento. Impostate questa opzione come «false» se non desiderate che il plug-plugin tenga conto delle modifiche apportate alle dimensioni di una pagina dopo il caricamento iniziale, a causa del codice SPA, HTML dinamico, ecc. |

## Restituisce

Il plug-plugin getpercentpageviewed non restituisce alcun valore. ma imposta le seguenti variabili all'interno dell'oggetto appmeasurement:

* `s._ppvPreviousPage`: Il nome della pagina precedente visualizzata (poiché le misure finali non sono disponibili fino a quando viene caricata una nuova pagina).
* `s._ppvHighestPercentViewed`: La percentuale più alta della pagina precedente visualizzata dal visitatore (in altezza). ossia il punto più lungo che il visitatore scorre verso il basso sulla pagina precedente.
* `s._ppvInitialPercentViewed`: Percentuale della pagina precedente che era visibile al primo caricamento della pagina precedente.
* `s._ppvHighestPixelSeen`: Il numero massimo di pixel totali visualizzati (in altezza) quando il visitatore scorre verso il basso la pagina precedente.

## Cookie

The getPercentPageViewed plugin creates a cookie, called `s_ppv`, that is passed from page to page. Il contenuto del cookie contiene i valori inseriti nelle quattro variabili descritte sopra e scade alla fine della sessione.

## Esempio di chiamate

**Esempio di chiamata 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

Esempio di codice sopra:
* Determina se s. pagename è impostato e, in tal caso, il codice eseguirà la funzione getpercentpageviewed.
* When the `getPercentPageViewed` function runs, it creates the variables described in the "Returns" section above.
* Se le variabili «Restituisce» sono state impostate correttamente:

   * The code sets s.prop1 equal to the value of `s._ppvPreviousPag`e (i.e. the previous value of `s.pageName`, or the previous page.)
   * Il codice imposta anche s. prop 2 uguale alla percentuale massima visualizzata della pagina precedente e alla percentuale iniziale visualizzata della pagina precedente.

>[!NOTE]
>Se un'intera pagina è visibile quando viene caricata per la prima volta, sia la percentuale massima visualizzata sia quelle visualizzate saranno uguali a 100. Tuttavia, se un'intera pagina non è visibile quando viene caricata per la prima volta, ma il visitatore non scorre mai la pagina prima di passare alla pagina successiva, sia la percentuale più alta visualizzata sia quelle visualizzate saranno uguali allo stesso valore.

**Esempio di chiamata 2**

Supponiamo che s. prop 5 sia stato impostato per acquisire un "tipo di pagina", piuttosto che l'intero nome della pagina.

Il codice seguente determina se è stato impostato s. prop 5 e, in tal caso, memorizza il suo valore come «pagina precedente» in modo che rientri con le dimensioni visualizzate e quelle iniziali visualizzate. The value is still stored in the `s._ppvPreviousPage` variable but can be treated as if it were the previous page type instead of the previous page name.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## Sostituzione oggetto S

Quando create un'istanza dell'oggetto della libreria appmeasurement principale con un nome diverso da "s", modificate la parte seguente del codice plug-plugin da questa stringa:

`s.getPercentPageViewed=function(pid,ch)`

a questo scopo:

`[objectname].getPercentPageViewed=function(pid,ch)`

## Codice da distribuire

Plugins Section: Add the following code to the area of the `s_code.js` file labeled PLUGINS SECTION. Non apportate modifiche a questa parte del codice plug-in.

```
/******************************************* BEGIN CODE TO DEPLOY *******************************************/ 
/* Adobe Consulting Plugin: getPercentPageViewed v3.01 w/handlePPVevents helper function (Requires AppMeasurement and p_fo plugin) */
s.getPercentPageViewed=function(pid,ch){var s=this,a=s.c_r("s_ppv");a=-1<a.indexOf(",")?a.split(","):[];a[0]=s.unescape(a[0]); 
pid=pid?pid:s.pageName?s.pageName:document.location.href;s.ppvChange=ch?ch:!0;if("undefined"===typeof s.linkType||"o"!==
s.linkType)s.ppvID&&s.ppvID===pid||(s.ppvID=pid,s.c_w("s_ppv",""),s.handlePPVevents()),s.p_fo("s_gppvLoad")&&window
.addEventListener&&(window.addEventListener("load",s.handlePPVevents,!1),window.addEventListener("click",s.handlePPVevents, !1),window.addEventListener("scroll",s.handlePPVevents,!1),window.addEventListener("resize",s.handlePPVevents,!1)),s._ppvPreviousPage
=a[0]?a[0]:"",s._ppvHighestPercentViewed=a[1]?a[1]:"",s._ppvInitialPercentViewed=a[2]?a[2]:"",s._ppvHighestPixelsSeen=a[3]?a[3]:""}; 

/* Adobe Consulting Plugin: handlePPVevents helper function (for getPercentPageViewed v3.01 Plugin) */ 
s.handlePPVevents=function(){if("undefined"!==typeof s_c_il){for(var c=0,d=s_c_il.length;c<d;c++)if(s_c_il[c]&&s_c_il[c].getPercentPageViewed){var a=s_c_il[c];break}if(a&&a.ppvID){var f=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.
body.clientHeight,document.documentElement.clientHeight));c=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+(window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight);d=Math.min(Math.round
(c/f*100),100);var e="";!a.c_r("s_tp")||a.unescape(a.c_r("s_ppv").split(",")[0])!==a.ppvID||1==a.ppvChange&&
a.c_r("s_tp")&&f!= a.c_r("s_tp")?(a.c_w("s_tp",f),a.c_w("s_ppv","")):e=a.c_r("s_ppv");var b=e&&-1<e.indexOf(",")?e.split(",",4):[];f=0<b.length?b[0]:escape(a.ppvID);var g=1<b.length?parseInt(b[1]):d,h=2<b.length?parseInt(b[2]):d;b=3<b.length?parseInt(b[3]):c;0<d&&(e=f+","+(d>g?d:g)+","+h+","+(c>b?c:b));a.c_w("s_ppv",e)}}}; 

/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 (Requires AppMeasurement) */ 
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0}; 
/******************************************** END CODE TO DEPLOY ********************************************/
```
