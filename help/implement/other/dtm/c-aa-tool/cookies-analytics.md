---
description: Descrizioni dei campi per le impostazioni globali Cookie utilizzate per distribuire Gestione tag dinamica in  Adobe Analytics.
keywords: Dynamic Tag Management;cookies;visitor id;visitor namespace;domain periods;fp domain periods;transaction id;cookie lifetime
solution: Experience Cloud,Analytics
title: Cookie
uuid: 9c81ecbb-0f02-4c1a-a5a5-426cdea57f38
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 54%

---


# Cookie

Field descriptions for the Cookies global settings used for deploying [!UICONTROL Dynamic Tag Management] in Adobe Analytics.

*`Property`* > Strumento Modifica > Cookie

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
   <td colname="col1"> Spazio nomi visitatore </td> 
   <td colname="col2"> <p>Variabile per identificare il dominio con cui sono impostati i cookie. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> Periodi di dominio </td> 
   <td colname="col2"> <p>Il dominio in cui il cookie di Analytics <code> s_cc</code> e <code> s_sq</code> è impostato determinando il numero di periodi nel dominio dell'URL della pagina. Questa variabile viene utilizzata anche da alcuni plug-in per determinare il dominio corretto per impostare il cookie del plug-in. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Periodi di dominio FP </td> 
   <td colname="col2"> <p>The <span class="term"> fpCookieDomainPeriods</span> variable is for cookies set by JavaScript (<code> s_sq</code>, <code> s_cc</code>, plug-ins) that are inherently first-party cookies, even if your implementation uses the third-party <span class="filepath"> 2o7.net</span> or <span class="filepath"> omtrdc.net</span> domains. </p> <p>Consulta <a href="/help/implement/vars/config-vars/fpcookiedomainperiods.md"  >s.fpCookieDomainPeriods</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID transazione </td> 
   <td colname="col2"> <p>Valore univoco che rappresenta una transazione online che ha generato un'attività offline. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata cookie </td> 
   <td colname="col2"> <p>Determina la durata di vita di un cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

