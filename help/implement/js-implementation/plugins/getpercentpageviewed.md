---
description: Misura l'attività di scorrimento di un visitatore per vedere la quantità di una pagina visualizzata prima di passare a un'altra pagina. Questo plug-in consente di determinare la quantità di contenuto che gli utenti visualizzano in media, in modo da poter ottimizzare la lunghezza e i layout della pagina in base ai comportamenti degli utenti.
keywords: Implementazione di Analytics
seo-description: Misura l'attività di scorrimento di un visitatore per vedere la quantità di una pagina visualizzata prima di passare a un'altra pagina. Questo plug-in consente di determinare la quantità di contenuto che gli utenti visualizzano in media, in modo da poter ottimizzare la lunghezza e i layout della pagina in base ai comportamenti degli utenti.
seo-title: getPercentPageViewed
solution: Analytics
subtopic: Plug-in
title: getPercentPageViewed
topic: Sviluppatore e implementazione
uuid: 1751dcdb-699f-4bd1-8bcb-5e62fa24896a
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# getPercentPageViewed

Il plug-in getPercentPageViewed misura l'attività di scorrimento di un visitatore per vedere la quantità di pagina visualizzata dal visitatore prima di passare a un'altra pagina.

>[!NOTE]
>Non è necessario utilizzare il plug-in getPercentPageViewed se le pagine Web sono di piccole dimensioni in altezza e non è necessario misurare la distanza di scorrimento dei visitatori verso il basso. Inoltre, se desiderate misurare l'attività di scorrimento solo sulle pagine di uscita, non potete utilizzare questo plug-in.

## Prerequisiti

Per eseguire il plug-in getPercentPageViewed è necessario disporre di AppMeasurement e del plug-in di supporto handlePPVevents.

## Implementazione

Per implementare questo plug-in, copiate e incollate il codice in qualsiasi punto della **[!UICONTROL Plugins]** sezione del [!DNL AppMeasurement] file.

>[!NOTE]
>L'aggiunta dei commenti o dei numeri di versione del codice al file AppMeasurement aiuta Adobe Consulting a risolvere eventuali problemi di implementazione.

È possibile eseguire la `getPercentPageViewed` funzione come necessario all'interno della funzione doPlugins (vedere le chiamate di esempio di seguito).

## Argomenti da trasmettere

| Argomento | Definizione |
|---|---|
| pid (facoltativo, stringa) | Identificatore di pagina associato alle percentuali fornite dalle misure del plug-in. Per impostazione predefinita viene visualizzata la variabile pageName di Analytics o l'URL se la variabile pageName non è impostata |
| ch (facoltativo, booleano) | "True" è il valore consigliato/predefinito per questo argomento. Impostate questo valore su "false" se non desiderate che questo plug-in consideri eventuali modifiche apportate alla dimensione di una pagina dopo il caricamento iniziale, a causa del codice SPA, HTML dinamico, ecc. |

## Restituisce

Il plug-in getPercentPageViewed non restituisce nulla. Imposta invece le seguenti variabili all'interno dell'oggetto AppMeasurement:

* `s._ppvPreviousPage`: Nome della pagina visualizzata precedente (i valori finali non sono disponibili fino al caricamento di una nuova pagina).
* `s._ppvHighestPercentViewed`: La percentuale più alta della pagina precedente visualizzata dal visitatore (in altezza). In altre parole, l'ulteriore punto in cui il visitatore ha fatto scorrere la pagina precedente.
* `s._ppvInitialPercentViewed`: Percentuale della pagina precedente visibile al primo caricamento della pagina precedente.
* `s._ppvHighestPixelSeen`: Il numero massimo di pixel totali visti (in altezza) dal visitatore che ha fatto scorrere la pagina precedente.

## Cookie

Il plug-in getPercentPageViewed crea un cookie, denominato `s_ppv`, che viene passato da una pagina all'altra. Il contenuto del cookie contiene i valori inseriti nelle quattro variabili sopra descritte e scade alla fine della sessione.

## Chiamate di esempio

**Esempio di chiamata 1**

```
if(s.pageName) s.getPercentPageViewed();
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed=" + s._ppvHighestPercentViewed + "initialPercentViewed="s._ppvInitialPercentViewed;
}  
```

Esempio di codice riportato sopra:
* Determina se s.pageName è impostato e, in tal caso, il codice eseguirà la funzione getPercentPageViewed.
* Quando la `getPercentPageViewed` funzione viene eseguita, crea le variabili descritte nella sezione "Restituisce" precedente.
* Se le variabili "Restituisce" sono state impostate correttamente:

   * Il codice imposta s.prop1 uguale al valore di `s._ppvPreviousPag`e (ovvero il valore precedente di `s.pageName`o della pagina precedente).
   * Il codice imposta anche s.prop2 uguale alla percentuale più alta visualizzata della pagina precedente e alla percentuale iniziale visualizzata della pagina precedente.

>[!NOTE]
>Se un’intera pagina è visibile al primo caricamento, sia la percentuale più elevata visualizzata che la percentuale iniziale visualizzata saranno uguali a 100. Tuttavia, se una pagina intera non è visibile al primo caricamento, ma il visitatore non scorre mai verso il basso prima di passare alla pagina successiva, sia la percentuale più alta visualizzata che la percentuale iniziale visualizzata saranno uguali allo stesso valore.

**Esempio di chiamata 2**

Supponete che s.prop5 sia stato impostato per acquisire un "tipo di pagina" con rollup anziché l’intero nome della pagina.

Il codice seguente determina se s.prop5 è stato impostato e, in tal caso, ne memorizza il valore come "pagina precedente" in modo da correlarlo con la percentuale più alta visualizzata e la percentuale iniziale visualizzata. Il valore è ancora memorizzato nella `s._ppvPreviousPage` variabile ma può essere considerato come se fosse il tipo di pagina precedente invece del nome di pagina precedente.

```
if(s._ppvPreviousPage)
{
s.prop1 = s._ppvPreviousPage;
s.prop2 = "highestPercentViewed = " + s._ppvHighestPercentViewed + " | initialPercentViewed=" + s._ppvInitialPercentViewed;
}  
```

## Sostituzione oggetti S

Quando create l'istanza dell'oggetto libreria AppMeasurement principale con un nome diverso da "s", modificate la seguente parte del codice del plug-in da qui:

`s.getPercentPageViewed=function(pid,ch)`

in questo:

`[objectname].getPercentPageViewed=function(pid,ch)`

## Codice da distribuire

Sezione Plugins: Aggiungere il codice seguente all'area del `s_code.js` file con etichetta PLUGINS SECTION. Non apportare modifiche a questa parte del codice plug-in.

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
