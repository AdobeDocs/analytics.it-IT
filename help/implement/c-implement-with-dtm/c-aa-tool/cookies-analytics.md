---
description: Descrizioni dei campi per le impostazioni globali dei cookie utilizzate per implementare Gestione tag dinamica in Adobe Analytics.
keywords: Gestione tag dinamica; cookie; ID visitatore; namespace del visitatore; periodi di dominio; periodi di dominio fp; id transazione; Durata cookie
seo-description: Descrizioni dei campi per le impostazioni globali dei cookie utilizzate per implementare Gestione tag dinamica in Adobe Analytics.
seo-title: Cookie
solution: Marketing Cloud, Analytics, Gestione tag dinamica
title: Cookie
uuid: 9 c 81 ecbb -0 f 02-4 c 1 a-a 5 a 5-426 cdea 57 f 38
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Cookie

Field descriptions for the Cookies global settings used for deploying [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

**[!UICONTROL  *`Property`*]**&gt;** [! UICONTROL![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Cookies]**

<table id="table_2758C770C91B4025AD74009B360D71F7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ID visitatore </td> 
   <td colname="col2"> <p>Valore univoco che rappresenta un cliente nei sistemi online e offline. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Spazio nomi visitatori </td> 
   <td colname="col2"> <p>Variabile per identificare il dominio con cui sono impostati i cookie. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Periodi di dominio </td> 
   <td colname="col2"> <p>The domain on which the Analytics cookie <code> s_cc</code> and <code> s_sq</code> are set by determining the number of periods in the domain of the page URL. Questa variabile viene utilizzata anche da alcuni plug-in per determinare il dominio corretto per impostare il cookie del plug-in. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Periodi di dominio FP </td> 
   <td colname="col2"> <p>The <span class="term"> fpCookieDomainPeriods</span> variable is for cookies set by JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-ins) that are inherently first-party cookies, even if your implementation uses the third-party <span class="filepath"> 2o7.net</span> or <span class="filepath"> omtrdc.net</span> domains. </p> <p>See <a href="../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00" format="dita" scope="local"> s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID transazione </td> 
   <td colname="col2"> <p>Valore univoco che rappresenta una transazione online che ha generato attività offline. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata cookie </td> 
   <td colname="col2"> <p>Determina la durata di vita di un cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

