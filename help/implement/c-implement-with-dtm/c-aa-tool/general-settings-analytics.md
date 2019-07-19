---
description: Descrizioni dei campi per le impostazioni Generali in Gestione tag dinamica per implementare Adobe Analytics.
keywords: Implementazione di Analytics; metodo di implementazione; gestione tag dinamica; dtm; impostazioni generali; eu compliance; set di caratteri; codice valuta; server di tracciamento; server di tracciamento ssl
seo-description: Descrizioni dei campi per le impostazioni Generali in Gestione tag dinamica per implementare Adobe Analytics.
seo-title: Generale
solution: Analytics
title: Generale
topic: Sviluppatore e implementazione
uuid: 93008719-6 fb 6-4 e 39-9 a 75-c 937 fe 3247 b 9
translation-type: tm+mt
source-git-commit: 49c81e50ff10060ef7a3debe82132d1099e25118

---


# Generale

Descrizioni dei campi per le impostazioni Generali in Gestione dinamica dei tag, per implementare Adobe Analytics.

**[!UICONTROL <Property>]** &gt; ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** &gt; **[!UICONTROL General]**

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
   <td colname="col2"> <p> Abilita o disabilita il tracciamento in base al cookie della privacy dell'Unione Europea. </p> <p>When a page is loaded, the system checks to see if a cookie called <span class="filepath"> sat_track </span> is set (or the custom cookie name specified on the <span class="wintitle"> Edit Property </span> page). Considerate le informazioni seguenti: </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> If the cookie does not exist or if the cookie exists and is set to anything but <span class="term"> true </span>, the loading of the tool is skipped when this setting is enabled. Ciò significa che non verrà applicata alcuna parte di una regola che utilizza lo strumento. </p> <p>If a rule has analytics with EU compliance on and third-party code, and the cookie is set to <span class="term"> false </span>, the third-party code still runs. Tuttavia, le variabili di analisi non saranno impostate. </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> If the cookie exists but it is set to <span class="term"> true </span>, the tool loads normally. </li> 
    </ul> <p>You are responsible for setting the <span class="filepath"> sat_track </span> (or custom named) cookie to <span class="term"> false </span> if a visitor opts out. Puoi eseguire questa operazione utilizzando codice personalizzato: </p> <p> 
     <code>_ satellite. setcookie («sat_ track», &amp; amp; nbsp; «false»); </code>
  </p> <p> You must also have a mechanism to set that cookie to <span class="term"> true </span> if you want a visitor to be able to opt in later: </p> <p> 
     <code>_ satellite. setcookie («sat_ track», &amp; amp; nbsp; «true»); </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Set di caratteri </p> </td> 
   <td colname="col2"> <p>Visualizza i set di codifica caratteri disponibili. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice della valuta </p> </td> 
   <td colname="col2"> <p>Visualizza i codici valuta supportati da selezionare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server di monitoraggio </p> </td> 
   <td colname="col2"> <p>Il dominio in cui viene scritto il cookie e la richiesta immagine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL Tracking Server </p> </td> 
   <td colname="col2"> <p>Il dominio in cui viene scritto il cookie e la richiesta immagine. Utilizzato per le pagine sicure. If not defined, SSL data goes to <span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Centro dati </p> </td> 
   <td colname="col2"> <p>Il centro dati Adobe utilizzato per la raccolta dati. </p> </td> 
  </tr> 
 </tbody> 
</table>

