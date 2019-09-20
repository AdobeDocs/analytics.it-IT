---
description: Descrizioni dei campi per le impostazioni globali Cookie utilizzate per distribuire Gestione tag dinamica in Adobe Analytics.
keywords: Gestione tag dinamica;cookie;visitor id;visitor namespace;domain periods;fp domain periods;transaction id;cookie lifetime (ID visitatore;visitatore namespace;dominio Periodi;fp dominio;transazione id;cookie lifetime (durata cookie)
seo-description: Descrizioni dei campi per le impostazioni globali Cookie utilizzate per distribuire Gestione tag dinamica in Adobe Analytics.
seo-title: Cookie
solution: Experience Cloud,Analytics,Gestione tag dinamica
title: Cookie
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Cookie

Descrizioni dei campi per le impostazioni globali dei cookie utilizzate per la distribuzione [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

**[!UICONTROL  *`Property`*]**&gt; **[!UICONTROL![](assets/settings_gear.png)

Modifica strumento]** &gt; **[!UICONTROL Cookies]**

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Visitor ID </td> 
   <td colname="col2"> <p>Valore univoco che rappresenta un cliente sia nei sistemi online che offline. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Spazio dei nomi dei visitatori </td> 
   <td colname="col2"> <p>Variabile per identificare il dominio con cui sono impostati i cookie. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Periodi di dominio </td> 
   <td colname="col2"> <p>The domain on which the Analytics cookie <code> s_cc</code> and <code> s_sq</code> are set by determining the number of periods in the domain of the page URL. Questa variabile viene utilizzata anche da alcuni plug-in per determinare il dominio corretto per impostare il cookie del plug-in. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Periodi di dominio FP </td> 
   <td colname="col2"> <p>La variabile <span class="term"> fpCookieDomainPeriods</span> è per i cookie impostati da JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-in) che sono intrinsecamente cookie di prime parti, anche se l’implementazione utilizza i domini di terze parti <span class="filepath"> 2o7.net</span> o <span class="filepath"> omtrdc.net</span> . </p> <p>Vedere <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID transazione </td> 
   <td colname="col2"> <p>Valore univoco che rappresenta una transazione online che ha generato un'attività offline. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata cookie </td> 
   <td colname="col2"> <p>Determina la durata di un cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

