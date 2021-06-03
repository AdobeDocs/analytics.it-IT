---
description: In Adobe Analytics e Adobe Audience Manager sono presenti metriche visitatore con definizioni simili, ma non allineate al 100%, per vari motivi.
title: Differenze tra i conteggi dei visitatori
uuid: c3bbb887-bd02-4c1c-9a2b-64811c0ef56a
exl-id: be5a935a-c3a2-4ab4-8cd7-ed54a37932c8
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 3%

---

# Differenze tra i conteggi dei visitatori

In Adobe Analytics e Adobe Audience Manager sono presenti metriche visitatore con definizioni simili, ma non allineate al 100%, per vari motivi.

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
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html"  > AAM: Popolazione totale del segmento</a> </p> </td> 
   <td colname="col3"> <p>Numero di dispositivi (ID Experience Cloud) che facevano parte del segmento durante il periodo di lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html"  > AAM: Popolazione di segmenti in tempo reale</a> </p> </td> 
   <td colname="col3"> <p>Numero di dispositivi (ID Experience Cloud) che facevano parte del segmento e che hanno raggiunto le tue proprietà durante il periodo di lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitatori unici </p> </td> 
   <td colname="col3"> <p>Mostra il numero di visitatori unici che hanno raggiunto le tue proprietà durante il periodo definito per la generazione del rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitatori con ID Experience Cloud </p> </td> 
   <td colname="col3"> <p>Mostra il numero di visitatori unici con un ID Experience Cloud che hanno raggiunto le tue proprietà durante il periodo di reporting. </p> </td> 
  </tr> 
 </tbody> 
</table>

AAM i visitatori di Real-time Segment Population e Analytics con ID Experience Cloud utilizzato nel reporting di Audience Analytics saranno i più simili. A breve termine, tuttavia, a causa di diversi fattori, vi saranno lievi discrepanze tra loro. I fattori che contribuiscono sono:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fattore </th> 
   <th colname="col2" class="entry"> AAM: Popolazione di segmenti in tempo reale </th> 
   <th colname="col3" class="entry"> Analytics: Visitatori con ID Experience Cloud </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fuso orario </p> </td> 
   <td colname="col2"> <p>UTC (ora universale coordinata) </p> </td> 
   <td colname="col3"> <p>Specificato per suite di rapporti </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtri personalizzati </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Sì, ad esempio filtri IP, filtri bot </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite di 150 segmenti </p> </td> 
   <td colname="col2"> <p>No </p> </td> 
   <td colname="col3"> <p>Sì: i conteggi di Analytics possono essere influenzati fino al 5% dal limite di integrazione di 150 segmenti. Se si verifica un troncamento, nella dimensione Nome pubblico verrà visualizzato "Limite pubblico raggiunto". </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulta [Informazioni sui segmenti in Analytics e Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) per ulteriori spiegazioni sulle sfumature tra i dati di Audience Manager e la segmentazione.
