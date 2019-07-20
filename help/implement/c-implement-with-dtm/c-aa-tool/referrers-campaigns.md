---
description: Descrizioni dei campi in Gestione tag dinamica per i referenti e le opzioni della campagna durante l'implementazione di Gestione tag dinamica in Adobe Analytics.
keywords: Gestione tag dinamica; referrer; campagne; referrer override; variabile campagna; query param
seo-description: Descrizioni dei campi in Gestione tag dinamica per i referenti e le opzioni della campagna durante l'implementazione di Gestione tag dinamica in Adobe Analytics.
seo-title: Referenti e campagne
solution: Marketing Cloud, Analytics, Gestione tag dinamica
title: Referenti e campagne
uuid: 56580206-a 382-4993-9 bba-a 488 da 65 cf 89
translation-type: tm+mt
source-git-commit: e271cf73e7fd31d8893ed57112f2f3bb7821fbdd

---


# Referenti e campagne

Field descriptions in [!UICONTROL Dynamic Tag Management] for referrers and campaign options when deploying [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

**[!UICONTROL  *`Property`*]**&gt;![](assets/settings_gear.png)**[!UICONTROL Edit Tool]**&gt;**[!UICONTROL Referrers & Campaigns]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Override referente </td> 
   <td colname="col2"> <p>Overrides the value set in the <span class="varname"> s.referrer</span> variable, which is typically populated by the referrer set in the browser. </p> <p>Consultate [Variabili pagina] (/help/implementation/js-implementation/c-variables/page-variables. md). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campagna </td> 
   <td colname="col2"> <p>Variabile che identifica le campagne di marketing utilizzate per portare visitatori sul sito. In genere, il valore della campagna viene prelevato da un parametro di stringa query. </p> <p>Consultate [Variabili pagina] (/help/implementation/js-implementation/c-variables/page-variables. md). </p> </td> 
  </tr> 
 </tbody> 
</table>

Usa l'interfaccia DTM per scegliere se usare una stringa o un valore query (che potrebbe essere estraibile da un elemento dati):

![](assets/dtm-queryparam.png)

Potete immettere la stringa di query direttamente nell'interfaccia, oppure potete fare riferimento a un elemento dati separato se disponete di altri metodi per tracciare una campagna.
