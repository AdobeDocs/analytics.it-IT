---
description: In Adobe Analytics e Adobe Audience Manager sono presenti metriche dei visitatori con definizioni simili, ma che non sono allineate al 100% per vari motivi.
title: Differenze tra i conteggi dei visitatori
uuid: c3bbb887-bd02-4c1c-9a2b-64811c0ef56a
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Differenze tra i conteggi dei visitatori

In Adobe Analytics e Adobe Audience Manager sono presenti metriche dei visitatori con definizioni simili, ma che non sono allineate al 100% per vari motivi.

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
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html"  > AAM: Popolazione segmento totale</a> </p> </td> 
   <td colname="col3"> <p>Numero di dispositivi (Experience Cloud ID) che erano membri del segmento durante il periodo di lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html"  > AAM: Popolazione di segmenti in tempo reale</a> </p> </td> 
   <td colname="col3"> <p>Numero di dispositivi (Experience Cloud ID) che appartenevano al segmento e che hanno raggiunto le tue proprietà durante il periodo di lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analisi: Visitatori unici </p> </td> 
   <td colname="col3"> <p>Mostra il numero di visitatori univoci che hanno raggiunto le vostre proprietà durante la finestra di rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analisi: Visitatori con Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Mostra il numero di visitatori univoci con un Experience Cloud ID che ha raggiunto le tue proprietà durante la finestra di rapporto. </p> </td> 
  </tr> 
 </tbody> 
</table>

I visitatori di AAM in tempo reale per la popolazione di segmenti e di Analytics con Experience Cloud ID utilizzati nella generazione dei rapporti di Audience Analytics saranno i più simili. A breve termine, tuttavia, a causa di diversi fattori, vi saranno lievi discrepanze tra di essi. I fattori che contribuiscono sono:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Factor </th> 
   <th colname="col2" class="entry"> AAM: Popolazione segmenti in tempo reale </th> 
   <th colname="col3" class="entry"> Analisi: Visitatori con Experience Cloud ID </th> 
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
   <td colname="col3"> <p>Sì: i conteggi di Analytics possono essere influenzati fino al 5% dal limite di integrazione di 150 segmenti. Se si verifica un troncamento, nella dimensione Nome pubblico viene visualizzato "Limite pubblico raggiunto". </p> </td> 
  </tr> 
 </tbody> 
</table>

Consulta [Informazioni sui segmenti in Analytics e Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md) per ulteriori spiegazioni sulle sfumature tra i dati e la segmentazione di Analytics e Audience Manager.
