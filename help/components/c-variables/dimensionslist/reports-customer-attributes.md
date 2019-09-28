---
description: Domande frequenti su Analytics per gli attributi del cliente e come eseguire il rapporto Attributi del cliente.
seo-description: Domande frequenti su Analytics per gli attributi del cliente e come eseguire il rapporto Attributi del cliente.
seo-title: Attributi cliente
solution: Experience Cloud, Analytics
title: Attributi cliente
uuid: 94721265-ba23-45d5-8807-76f81b0b8a30
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Attributi cliente

Domande frequenti su Analytics per gli attributi del cliente e come eseguire il rapporto Attributi del cliente.

**[!UICONTROL Reports]** **[!UICONTROL > Visitor Profile]** &gt; **[!UICONTROL Customer Attributes]**

Se acquisisci dati del cliente di livello Enterprise in un database CRM (Customer Relationship Management), puoi caricare tali dati in una sorgente dati di attributi cliente in Experience Cloud. Dopo aver caricato i dati, puoi eseguire il rapporto Attributi del cliente in Reporting e analisi.

* [Attributi del cliente e metriche di reporting in Analytics](../../../components/c-variables/dimensionslist/reports-customer-attributes.md#section_EF343662146B460A882D3DF772ADD86D)
* [Domande frequenti - Attributi del cliente in Analytics](../../../components/c-variables/dimensionslist/reports-customer-attributes.md#section_E29641D1F3D649C1AC9EA5231921F038)

Consulta Attributi [del](https://marketing.adobe.com/resources/help/en_US/mcloud/attributes.html) cliente nell'Aiuto di Experience Cloud per informazioni sul caricamento dei dati attributo del cliente.

## Attributi del cliente e metriche di reporting in Analytics {#section_EF343662146B460A882D3DF772ADD86D}

Dopo aver caricato gli attributi del cliente e convalidato lo schema (in Experience Cloud), il sistema crea metriche in base ai nomi descrittivi (come *`age`* o *`gender`*) mappati alle stringhe e ai numeri interi degli attributi. Tali metriche vengono visualizzate in **[!UICONTROL Visitor Profile]** &gt; **[!UICONTROL Customer Attributes]** report.

Ad esempio:

**[!UICONTROL Visitor Profile]** &gt; **[!UICONTROL Customer Attributes]** &gt; **[!UICONTROL Age]**

![](assets/report_age.png)

**Esempio - Metriche dell'età**

Se si specifica una stringa con nome, *`age`* il sistema crea le metriche e le dimensioni seguenti:

* Dimensione età: Consente di eseguire un report basato sull'attributo Age.
* Metrica età: Una metrica che puoi aggiungere a un rapporto, ad esempio un rapporto Visitatori unici.
* Conteggio metriche età: Consente di comprendere, ad esempio, se i visitatori hanno specificato un *`age`* valore in un modulo.

Poiché le metriche sono somme in una tabella di report, devi [creare una metrica](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) calcolata che ti indichi l'età media. La formula per questa metrica è `Age / Count of Age`.

## Domande frequenti - Attributi del cliente in Analytics {#section_E29641D1F3D649C1AC9EA5231921F038}

<table id="table_88631069013B408EBB0A810657662B36"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Perché è preferibile utilizzare il servizio identità per impostare l'ID cliente invece di compilare l'ID cliente in una prop o eVar? </p> </td> 
   <td colname="col2"> <p>L'utilizzo di Identity Service offre una serie di vantaggi: </p> 
    <ul id="ul_5D3659604D43419F9CA5920B4F93728E"> 
     <li id="li_BA2EF0715C5A47EFAFA7191CFAD088A4">Se non imposti l'ID cliente con il servizio identità, i record cliente sono disponibili solo per Adobe Analytics. Se desiderate utilizzare i record cliente per il targeting in tempo reale, dovete utilizzare il servizio identità. </li> 
     <li id="li_228358684E474A298E39578D427BF932">L'utilizzo del servizio identità per impostare l'ID cliente riduce il tempo necessario per sincronizzare gli ID con Experience Cloud. Se inserisci l'ID cliente in una prop o eVar, gli ID cliente vengono inviati a Experience Cloud tramite la sincronizzazione server back-end che si verifica in batch. Il servizio identità sincronizza immediatamente l'ID cliente con Experience Cloud. </li> 
     <li id="li_BCF28219E4014FCF9F747C3D8D270526"> L'utilizzo di Identity Service invece di una prop o eVar consente di liberare tale prop o eVar per altri usi. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se sto già memorizzando un ID cliente in una prop o eVar, perché dovrei utilizzare questa nuova funzionalità invece di classificare la mia prop o eVar con gli attributi CRM? </p> </td> 
   <td colname="col2"> <p>Le proprietà e le eVar sono soggette a limitazioni di tipo Uniques superate. Utilizzando questa funzionalità puoi inserire dati attributo per un numero illimitato di ID cliente. Inoltre, l'utilizzo dell'approccio prop/eVar limita le informazioni CRM ad Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Come verranno visualizzati gli attributi CRM in Adobe Analytics? </p> </td> 
   <td colname="col2"> <p>Gli attributi CRM saranno visibili in Analysis Workspace, Reporting e analisi, Analisi ad hoc, API di reporting e Generatore di report. Gli attributi di testo verranno visualizzati come rapporti/dimensioni. Gli attributi numerici verranno visualizzati sia come dimensioni che come metriche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I dati CRM saranno disponibili in Data Warehouse e nei feed di dati? </p> </td> 
   <td colname="col2"> <p>I dati CRM non sono attualmente disponibili in Data Warehouse o nei feed di dati di Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

