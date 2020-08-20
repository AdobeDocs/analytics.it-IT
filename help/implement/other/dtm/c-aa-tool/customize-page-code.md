---
description: Utilizzate le descrizioni dei campi in Gestione tag dinamica per personalizzare il codice della pagina durante la distribuzione di Analytics.
keywords: Dynamic Tag Management;customize page code;open editor;execute
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Personalizzare il codice della pagina
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: tm+mt
source-git-commit: 4b6107fe57787e639fb06ef957d6230d1bc45bd1
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%

---


# Personalizzare il codice della pagina

Utilizzate le descrizioni dei campi in Gestione tag dinamica per personalizzare il codice della pagina durante la distribuzione di Analytics.

**[!UICONTROL `Property`]** > **[!UICONTROL Edit Tool]** ![](assets/settings_gear.png) > **[!UICONTROL Customize Page Code]**

<table id="table_A4676A5FEE814DF9A05DA0E56F8B4C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Open Editor </p> </td> 
   <td colname="col2"> <p>Puoi inserire qualsiasi chiamata JavaScript che deve essere attivata prima della <code> s.t()</code> chiamata finale, contenuta nella <code> s_code</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Execute </p> </td> 
   <td colname="col2"> <p> <b>Prima delle impostazioni</b>dell’interfaccia utente: Le impostazioni dell'interfaccia hanno precedenza rispetto al codice personalizzato (ad esempio, se si desidera ignorare un eVar  se è stata attivata un'impostazione nell'interfaccia). </p> <p> <b>Dopo le impostazioni</b>dell'interfaccia utente: Il codice personalizzato ha la precedenza sulle impostazioni dell'interfaccia. </p> </td> 
  </tr> 
 </tbody> 
</table>

