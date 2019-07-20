---
description: Domande frequenti su Analytics per gli attributi del cliente e come eseguire il rapporto Attributi del cliente.
seo-description: Domande frequenti su Analytics per gli attributi del cliente e come eseguire il rapporto Attributi del cliente.
seo-title: Attributi del cliente
solution: Marketing Cloud, Analytics
title: Attributi del cliente
uuid: 94721265-ba 23-45 d 5-8807-76 f 81 b 0 b 8 a 30
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Attributi del cliente

Domande frequenti su Analytics per gli attributi del cliente e come eseguire il rapporto Attributi del cliente.

**[!UICONTROL Reports]** **[!UICONTROL > Visitor Profile]** &gt; **[!UICONTROL Customer Attributes]**

Se acquisisci dati del cliente di livello Enterprise in un database CRM (Customer Relationship Management), puoi caricare tali dati in una sorgente dati di attributi cliente in Experience Cloud. Una volta caricati i dati, puoi eseguire il rapporto Attributi del cliente in Reporting e analisi.

* [Attributi del cliente e metriche di reporting in Analytics](../../../components/c-variables/dimensionslist/reports-customer-attributes.md#section_EF343662146B460A882D3DF772ADD86D)
* [Domande frequenti - Attributi del cliente in Analytics](../../../components/c-variables/dimensionslist/reports-customer-attributes.md#section_E29641D1F3D649C1AC9EA5231921F038)

See [Customer Attributes](https://marketing.adobe.com/resources/help/en_US/mcloud/index.html?f=attributes) in Experience Cloud help for information about uploading customer attribute data.

## Customer Attributes and Reporting Metrics in Analytics {#section_EF343662146B460A882D3DF772ADD86D}

After you upload customer attributes and validate the schema (in the Experience Cloud), the system creates metrics based on the friendly names (like *`age`* or *`gender`*) that you map to the attribute strings and integers. These metrics appear in **[!UICONTROL Visitor Profile]** &gt; **[!UICONTROL Customer Attributes]** reports.

Ad esempio:

**[!UICONTROL Visitor Profile]** &gt; **[!UICONTROL Customer Attributes]** &gt; **[!UICONTROL Age]**

![](assets/report_age.png)

**Esempio - Metriche age**

If you specify a string as *`age`*, the system creates the following metrics and dimensions:

* Dimensione età: Consente di eseguire un report basato sull'attributo Age.
* Metrica età: Una metrica che puoi aggiungere a un report, ad esempio un rapporto Visitatori unici.
* Count of Age metric: Lets you understand, for example, if visitors specified an *`age`* value on a form.

Because metrics are sums in a report table, you should [create a calculated metric](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) that tells you the average age. The formula for this metric is `Age / Count of Age`.

## FAQ - Customer Attributes in Analytics {#section_E29641D1F3D649C1AC9EA5231921F038}

<table id="table_88631069013B408EBB0A810657662B36"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Perché è preferibile utilizzare il servizio identità per impostare l'ID cliente invece di compilare l'ID cliente in una prop o evar? </p> </td> 
   <td colname="col2"> <p>L'utilizzo del servizio identità offre molti vantaggi: </p> 
    <ul id="ul_5D3659604D43419F9CA5920B4F93728E"> 
     <li id="li_BA2EF0715C5A47EFAFA7191CFAD088A4">Se non impostate l'ID cliente con il servizio identità, i record dei clienti sono disponibili solo per Adobe Analytics. Se desiderate utilizzare i record del cliente per il targeting in tempo reale, dovete utilizzare il servizio identità. </li> 
     <li id="li_228358684E474A298E39578D427BF932">L'utilizzo del servizio identità per impostare l'ID cliente riduce il tempo necessario per sincronizzare gli ID con Experience Cloud. Se imposti l'ID cliente in una prop o evar, gli ID cliente vengono inviati a Experience Cloud tramite la sincronizzazione server back-end che si verifica in batch. Il servizio identità sincronizza immediatamente l'ID cliente con Experience Cloud. </li> 
     <li id="li_BCF28219E4014FCF9F747C3D8D270526"> Utilizzando il servizio identità invece di una prop o evar, la proprietà o evar viene liberato per altri usi. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se stai già memorizzando un ID cliente in una prop o evar, perché dovrei usare questa nuova funzionalità invece di classificare la mia prop o evar con gli attributi CRM? </p> </td> 
   <td colname="col2"> <p>I prop e le evar sono soggetti a limitazioni Superato per Uniques. Con questa funzionalità puoi inserire dati attributo per un numero illimitato di ID cliente. Inoltre, l'utilizzo dell'approccio prop/evar limita le informazioni CRM ad Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>In che modo gli attributi CRM vengono visualizzati in Adobe Analytics? </p> </td> 
   <td colname="col2"> <p>Gli attributi CRM saranno espressi in Analysis Workspace, Reporting e analisi, Analisi ad hoc, API di reporting e Generatore di report. Gli attributi del testo verranno visualizzati come report/dimensioni. Gli attributi numerici vengono visualizzati come dimensioni e metriche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I dati CRM saranno disponibili in Data Warehouse e nei feed dati? </p> </td> 
   <td colname="col2"> <p>I dati CRM non sono attualmente disponibili in Data Warehouse o Feed dati di Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

