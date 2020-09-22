---
description: Descrizioni dei campi in Gestione tag dinamica per referenti e opzioni delle campagne durante la distribuzione di Gestione tag dinamica in  Adobe Analytics.
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics
title: Riferimenti e campagne
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 6%

---


# Riferimenti e campagne

Descrizioni dei campi in [!UICONTROL Dynamic Tag Management] per referenti e opzioni della campagna durante la distribuzione [!UICONTROL Dynamic Tag Management] in  Adobe [!DNL Analytics].

**[!UICONTROL  *`Property`*]** > Icona ![](assets/settings_gear.png) ingranaggio **[!UICONTROL Edit Tool]** > **[!UICONTROL Referrers & Campaigns]**

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
   <td colname="col2"> <p>Sostituisce il valore impostato nella variabile <span class="varname"> s.referrer</span> , generalmente popolata dal set di referrer nel browser. </p> <p>Vedere <a href="../../../vars/page-vars/referrer.md">referrer</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Campaign </td>
   <td colname="col2"> <p>Variabile che identifica le campagne di marketing utilizzate per portare i visitatori sul sito. Il valore della campagna viene in genere ricavato da un parametro di stringa di query. </p> <p>Consultate <a href="../../../vars/page-vars/campaign.md">campagna</a>. </p> </td>
  </tr>
 </tbody>
</table>

Utilizzate l&#39;interfaccia di Gestione dinamica dei tag per scegliere se utilizzare una stringa o un valore di query (che può essere estratta da un elemento di dati):

![Parametro query](assets/dtm-queryparam.png)

È possibile immettere la stringa di query direttamente nell&#39;interfaccia oppure fare riferimento a un elemento dati separato se si dispone di altri mezzi per tracciare una campagna.
