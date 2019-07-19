---
description: Utilizza le descrizioni dei campi in Gestione tag dinamica per personalizzare il codice della pagina durante la distribuzione di Analytics.
keywords: Gestione tag dinamica; personalizzare il codice della pagina; editor aperto; execute
seo-description: Utilizza le descrizioni dei campi in Gestione tag dinamica per personalizzare il codice della pagina durante la distribuzione di Analytics.
seo-title: Personalizzare il codice della pagina
solution: Marketing Cloud, Analytics, Target, Gestione tag dinamica
title: Personalizzare il codice della pagina
uuid: b 7 cad 069-3 eb 8-4388-b 0 b 0-34 f 54001 e 05 f
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Personalizzare il codice della pagina

Utilizza le descrizioni dei campi in Gestione tag dinamica per personalizzare il codice della pagina durante la distribuzione di Analytics.

Aggiungete i plug-in per assicurarvi che il codice venga eseguito contemporaneamente allo strumento Analytics. For more information about the Analytics plugins, see [Implementation Plug-ins](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**[!UICONTROL  *`Property`*]**&gt;** [! UICONTROL![](assets/settings_gear.png)

Edit Tool]** &gt; **[!UICONTROL Customize Page Code]**

<table id="table_A4676A5FEE814DF9A05DA0E56F8B4C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Editor aperto </p> </td> 
   <td colname="col2"> <p>You can insert any JavaScript call that must be triggered before the final <code> s.t()</code> call, which is contained in the <code> s_code</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esegui </p> </td> 
   <td colname="col2"> <p> <b>Prima delle impostazioni dell'interfaccia utente</b>: Le impostazioni dell'interfaccia hanno precedenza rispetto al codice personalizzato (ad esempio, se desideri escludere un evar se è stata abilitata un'impostazione nell'interfaccia). </p> <p> <b>Dopo le impostazioni dell'interfaccia</b>utente: Il codice personalizzato ha la precedenza sulle impostazioni dell'interfaccia. </p> </td> 
  </tr> 
 </tbody> 
</table>

