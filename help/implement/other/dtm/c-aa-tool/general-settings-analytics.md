---
description: Descrizioni dei campi per le impostazioni generali in Dynamic Tag Manager, per la distribuzione di Adobe Analytics.
keywords: Implementazione di Analytics;metodo di implementazione;gestione tag dinamica;dtm;impostazioni generali;conformità ue;set di caratteri;codice valuta;server di tracciamento;ssl tracking server
title: Generale
topic-fix: Developer and implementation
uuid: 93008719-6fb6-4e39-9a75-c937fe3247b9
exl-id: f63e83bf-be87-4ea2-ba04-5c152e5d16d3
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 18%

---

# Generale

Descrizioni dei campi per le impostazioni generali in DTM, per la distribuzione di Adobe Analytics.

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
   <td colname="col1"> <p>Abilita la conformità UE per <span class="keyword"> Adobe Analytics </span> </p> </td> 
   <td colname="col2"> <p> Abilita o disabilita il tracciamento in base al cookie di privacy UE. </p> <p>Quando viene caricata una pagina, il sistema controlla se è impostato un cookie chiamato <span class="filepath"> sat_track </span> (o il nome del cookie personalizzato specificato nella pagina <span class="wintitle"> Modifica proprietà </span>). Prendi in considerazione le seguenti informazioni: </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> Se il cookie non esiste o se il cookie esiste ed è impostato su un valore diverso da <span class="term"> true </span>, il caricamento dello strumento viene ignorato quando questa impostazione è abilitata. Ciò significa che non verrà applicata alcuna parte di una regola che utilizza lo strumento. </p> <p>Se una regola dispone di analisi con conformità UE su e codice di terze parti e il cookie è impostato su <span class="term"> false </span>, il codice di terze parti continua a essere eseguito. Tuttavia, le variabili di analisi non saranno impostate. </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> Se il cookie esiste ma è impostato su <span class="term"> true </span>, lo strumento viene caricato normalmente. </li> 
    </ul> <p>Sei responsabile di impostare il cookie <span class="filepath"> sat_track </span> (o personalizzato con nome) su <span class="term"> false </span> se un visitatore rinuncia. Puoi eseguire questa operazione utilizzando un codice personalizzato: </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"false"); 
     </code> </p> <p> È inoltre necessario disporre di un meccanismo per impostare tale cookie su <span class="term"> true </span> se si desidera che un visitatore possa effettuare il consenso in un secondo momento: </p> <p> 
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
   <td colname="col2"> <p>Il dominio in cui vengono scritti la richiesta di immagini e il cookie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server di tracciamento SSL </p> </td> 
   <td colname="col2"> <p>Il dominio in cui vengono scritti la richiesta di immagini e il cookie. Utilizzato per pagine sicure. Se non sono definiti, i dati SSL vanno su <span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Centro dati </p> </td> 
   <td colname="col2"> <p>Il centro dati di Adobe utilizzato per la raccolta dati. </p> </td> 
  </tr> 
 </tbody> 
</table>
