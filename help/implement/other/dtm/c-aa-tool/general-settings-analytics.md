---
description: Descrizioni dei campi per le impostazioni Generali in Gestione tag dinamica, per la distribuzione  Adobe Analytics.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;general settings;eu compliance;character set;currency code;tracking server;ssl tracking server
title: Generale
topic: Developer and implementation
uuid: 93008719-6fb6-4e39-9a75-c937fe3247b9
translation-type: tm+mt
source-git-commit: 0d699a50a764d9ea76771118c7cc083fb46cefe9
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 19%

---


# Generale

Descrizioni dei campi per le impostazioni Generali in Gestione dinamica dei tag, per la distribuzione  Adobe Analytics.

**[!UICONTROL *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL General]**

<table id="table_DD8DA303698041D296DD5DB080AF7971"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Enable EU compliance for <span class="keyword"> Adobe Analytics </span> </p> </td> 
   <td colname="col2"> <p> Abilita o disabilita il tracciamento in base al cookie di privacy UE. </p> <p>When a page is loaded, the system checks to see if a cookie called <span class="filepath"> sat_track </span> is set (or the custom cookie name specified on the <span class="wintitle"> Edit Property </span> page). Prendi in considerazione le seguenti informazioni: </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> If the cookie does not exist or if the cookie exists and is set to anything but <span class="term"> true </span>, the loading of the tool is skipped when this setting is enabled. Ciò significa che non verrà applicata alcuna parte di una regola che utilizza lo strumento. </p> <p>If a rule has analytics with EU compliance on and third-party code, and the cookie is set to <span class="term"> false </span>, the third-party code still runs. Tuttavia, le variabili di analisi non saranno impostate. </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> If the cookie exists but it is set to <span class="term"> true </span>, the tool loads normally. </li> 
    </ul> <p>You are responsible for setting the <span class="filepath"> sat_track </span> (or custom named) cookie to <span class="term"> false </span> if a visitor opts out. Puoi eseguire questa operazione utilizzando un codice personalizzato: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"false"); 
     </code> </p> <p> You must also have a mechanism to set that cookie to <span class="term"> true </span> if you want a visitor to be able to opt in later: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"true"); 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Set di caratteri </p> </td> 
   <td colname="col2"> <p>Visualizza i set di codifica dei caratteri disponibili. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice della valuta </p> </td> 
   <td colname="col2"> <p>Visualizza i codici valuta supportati per la selezione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tracking Server </p> </td> 
   <td colname="col2"> <p>Il dominio in cui vengono scritti la richiesta di immagine e il cookie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server di tracciamento SSL </p> </td> 
   <td colname="col2"> <p>Il dominio in cui vengono scritti la richiesta di immagine e il cookie. Utilizzato per pagine sicure. Se non è definito, i dati SSL vanno al <span class="term"> server di tracciamento </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Centro dati </p> </td> 
   <td colname="col2"> <p>Il centro dati del Adobe  utilizzato per la raccolta dei dati. </p> </td> 
  </tr> 
 </tbody> 
</table>

