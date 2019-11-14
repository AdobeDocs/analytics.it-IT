---
description: Descrizioni dei campi in Gestione tag dinamica per referenti e opzioni delle campagne durante la distribuzione di Gestione tag dinamica in Adobe Analytics.
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Riferimenti e campagne
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Riferimenti e campagne

Descrizioni dei campi in [!UICONTROL Dynamic Tag Management] per referenti e opzioni della campagna durante la distribuzione [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

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
   <td colname="col1"> Override Referrer </td> 
   <td colname="col2"> <p>Sostituisce il valore impostato nella variabile <span class="varname"> s.referrer</span> , generalmente popolata dal set di referrer nel browser. </p> <p>Consultate Variabili <a href="/help/implement/js-implementation/c-variables/page-variables.md">di</a>pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campagna </td> 
   <td colname="col2"> <p>Variabile che identifica le campagne di marketing utilizzate per portare i visitatori sul sito. Il valore della campagna viene in genere ricavato da un parametro di stringa di query. </p> <p>Vedere [Variabili<a href="/help/implement/js-implementation/c-variables/page-variables.md">di</a>pagina. </p> </td> 
  </tr> 
 </tbody> 
</table>

Utilizzate l'interfaccia di Gestione dinamica dei tag per scegliere se utilizzare una stringa o un valore di query (che può essere estratta da un elemento dati):

![](assets/dtm-queryparam.png)

È possibile immettere la stringa di query direttamente nell'interfaccia oppure fare riferimento a un elemento dati separato se si dispone di altri mezzi per tracciare una campagna.
