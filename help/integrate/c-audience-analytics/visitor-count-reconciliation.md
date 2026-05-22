---
description: In Adobe Analytics e Adobe Audience Manager esistono metriche visitatore con definizioni simili, ma non allineate al 100%, per vari motivi.
title: Differenze tra i conteggi dei visitatori
feature: Audience Analytics
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
TQID: 'https://experienceleague.adobe.com/ksfYYDZ6G9vH7WEZVh-JsN93Rl-jsZTe9-CQADSwnfI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: a97e0d8c-238a-47ee-8d81-16bd45309bed
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 312
ht-degree: 4%

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
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html"  > Adobe Audience Manager: popolazione totale del segmento</a> </p> </td> 
   <td colname="col3"> <p>Numero di dispositivi (Experience Cloud ID) che erano membri del segmento durante il periodo di lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html"  > Adobe Audience Manager: Popolazione segmento in tempo reale</a> </p> </td> 
   <td colname="col3"> <p>Numero di dispositivi (Experience Cloud ID) membri del segmento che hanno raggiunto le proprietà durante il periodo di lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: visitatori univoci </p> </td> 
   <td colname="col3"> <p>Mostra il numero di visitatori univoci che hanno raggiunto le proprietà durante l’intervallo di reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: visitatori con Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Mostra il numero di visitatori univoci con un Experience Cloud ID che hanno raggiunto le proprietà durante l’intervallo di reporting. </p> </td> 
  </tr> 
 </tbody> 
</table>

La popolazione dei segmenti in tempo reale di Adobe Audience Manager e i visitatori di Analytics con Experience Cloud ID utilizzati nel reporting di Audience Analytics saranno i più simili. Nel breve periodo, tuttavia, a causa di diversi fattori, vi saranno lievi discrepanze tra di essi. I fattori che contribuiscono sono:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fattore </th> 
   <th colname="col2" class="entry"> Adobe Audience Manager: popolazione dei segmenti in tempo reale </th> 
   <th colname="col3" class="entry"> Analytics: visitatori con Experience Cloud ID </th> 
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

Per ulteriori spiegazioni sulle sfumature tra i dati e la segmentazione di Analytics e Audience Manager, consulta [Informazioni sui segmenti in Analytics e Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md).
