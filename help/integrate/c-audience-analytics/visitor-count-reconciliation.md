---
description: In Adobe Analytics e Adobe Audience Manager esistono metriche visitatore con definizioni simili, ma non allineate al 100%, per vari motivi.
title: Differenze tra i conteggi dei visitatori
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 3%

---

# Differenze tra i conteggi dei visitatori

In Adobe Analytics e Adobe Audience Manager esistono metriche visitatore con definizioni simili, ma non allineate al 100%, per vari motivi.

Le metriche del visitatore sono:

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Metrica </th> 
   <th colname="col3" class="entry"> Definizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=it"  > Adobe Audience Manager: popolazione totale del segmento</a> </p> </td> 
   <td colname="col3"> <p>Numero di dispositivi (ID Experience Cloud) che erano membri del segmento durante il periodo di lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html?lang=it"  > Adobe Audience Manager: Popolazione segmento in tempo reale</a> </p> </td> 
   <td colname="col3"> <p>Numero di dispositivi (ID Experience Cloud) membri del segmento che hanno raggiunto le proprietà durante il periodo di lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: visitatori univoci </p> </td> 
   <td colname="col3"> <p>Mostra il numero di visitatori univoci che hanno raggiunto le proprietà durante l’intervallo di reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: visitatori con ID Experience Cloud </p> </td> 
   <td colname="col3"> <p>Mostra il numero di visitatori univoci con un ID Experience Cloud che hanno raggiunto le proprietà durante l’intervallo di reporting. </p> </td> 
  </tr> 
 </tbody> 
</table>

La popolazione dei segmenti in tempo reale di Adobe Audience Manager e i visitatori di Analytics con l’ID Experience Cloud utilizzato nel reporting di Audience Analytics saranno i più simili. Nel breve periodo, tuttavia, a causa di diversi fattori, vi saranno lievi discrepanze tra di essi. I fattori che contribuiscono sono:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fattore </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager: popolazione dei segmenti in tempo reale </th> 
   <th colname="col3" class="entry"> Analytics: visitatori con ID Experience Cloud </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fuso orario </p> </td> 
   <td colname="col2"> <p>UTC (Coordinated Universal Time) </p> </td> 
   <td colname="col3"> <p>Specificato per suite di rapporti </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtri personalizzati </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Sì, ad es. filtri IP, filtri bot </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite di 150 segmenti </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Sì - I conteggi di Analytics possono essere interessati fino al 5% dal limite di integrazione del segmento 150. Se viene raggiunto il troncamento, nella dimensione Nome pubblico viene visualizzato "Limite di pubblico raggiunto". </p> </td> 
  </tr> 
 </tbody> 
</table>

Per ulteriori spiegazioni sulle sfumature tra Analytics e i dati e la segmentazione di Audience Manager, consulta [Informazioni sui segmenti in Analytics e Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md).
