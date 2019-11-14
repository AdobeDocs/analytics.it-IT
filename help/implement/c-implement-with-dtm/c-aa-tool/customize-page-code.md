---
description: Utilizzate le descrizioni dei campi in Gestione tag dinamica per personalizzare il codice della pagina durante la distribuzione di Analytics.
keywords: Dynamic Tag Management;customize page code;open editor;execute
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Personalizzare il codice della pagina
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Personalizzare il codice della pagina

Utilizzate le descrizioni dei campi in Gestione tag dinamica per personalizzare il codice della pagina durante la distribuzione di Analytics.

Aggiungete i plug-in per assicurarvi che il codice venga eseguito contemporaneamente allo strumento Analytics. Per ulteriori informazioni sui plug-in di Analytics, consultate Plug-in [di](/help/implement/js-implementation/plugins/impl-plugins.md)implementazione.

**[!UICONTROL  *`Property`*]**&gt; **[!UICONTROL![](assets/settings_gear.png)

Modifica strumento]** &gt; **[!UICONTROL Customize Page Code]**

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
   <td colname="col2"> <p> <b>Prima delle impostazioni</b>dell’interfaccia utente: Le impostazioni dell'interfaccia hanno precedenza rispetto al codice personalizzato (ad esempio, se si desidera ignorare un'eVar se è stata attivata un'impostazione nell'interfaccia). </p> <p> <b>Dopo le impostazioni</b>dell'interfaccia utente: Il codice personalizzato ha la precedenza sulle impostazioni dell'interfaccia. </p> </td> 
  </tr> 
 </tbody> 
</table>

