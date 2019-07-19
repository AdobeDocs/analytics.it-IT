---
description: In Adobe Analytics e Adobe Audience Manager sono disponibili metriche dei visitatori con definizioni simili, ma non con allineamento del 100%, per vari motivi.
seo-description: In Adobe Analytics e Adobe Audience Manager sono disponibili metriche dei visitatori con definizioni simili, ma non con allineamento del 100%, per vari motivi.
seo-title: Differenze tra i conteggi dei visitatori
title: Differenze tra i conteggi dei visitatori
uuid: c 3 bbb 887-bd 02-4 c 1 c -9 a 2 b -64811 c 0 ef 56 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Differenze tra i conteggi dei visitatori

In Adobe Analytics e Adobe Audience Manager sono disponibili metriche dei visitatori con definizioni simili, ma non con allineamento del 100%, per vari motivi.

Le metriche dei visitatori sono:

<table id="table_F9FE107A89934C3B854C55D7D76AC6E8"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Metrica </th> 
   <th colname="col3" class="entry"> Definizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html" format="html" scope="external"> AAM: Popolazione segmento totale</a> </p> </td> 
   <td colname="col3"> <p>Conteggio dei dispositivi (Experience Cloud ID) che erano membri del segmento durante il periodo di lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><a href="https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html" format="html" scope="external"> AAM: Popolazione segmento in tempo reale</a> </p> </td> 
   <td colname="col3"> <p>Conteggio dei dispositivi (Experience Cloud ID) che erano membri del segmento e hanno raggiunto le proprietà durante il periodo di lookback. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitatori unici </p> </td> 
   <td colname="col3"> <p>Mostra il numero di visitatori univoci che hanno raggiunto le proprietà durante la finestra di reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Analytics: Visitatori con Experience Cloud ID </p> </td> 
   <td colname="col3"> <p>Mostra il numero di visitatori univoci con un Experience Cloud ID che hanno raggiunto le tue proprietà durante la finestra di reporting. </p> </td> 
  </tr> 
 </tbody> 
</table>

AAM Real-time Segment Population and Analytics Visitors with Experience Cloud ID used within Audience Analytics report will be the most similar. Tuttavia, a causa di diversi fattori, si verificheranno lievi discrepanze tra i due fattori. Fattori che contribuiscono sono:

<table id="table_A391B37CC077456F8BB83BAA3C640EF6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fattore </th> 
   <th colname="col2" class="entry"> AAM: Popolazione segmento in tempo reale </th> 
   <th colname="col3" class="entry"> Analytics: Visitatori con Experience Cloud ID </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fuso orario </p> </td> 
   <td colname="col2"> <p>UTC (Universal Universal Time) </p> </td> 
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
   <td colname="col3"> <p>Sì - I conteggi di Analytics possono essere interessati dal limite dell'integrazione di 150 segmenti. «Il limite pubblico raggiunto» verrà visualizzato nella dimensione Nome audience se si è verificato un troncamento. </p> </td> 
  </tr> 
 </tbody> 
</table>

See [Understanding Segments in Analytics and Audience Manager](../../integrate/c-audience-analytics/aam-analytics-segments.md#concept_AB72F76AFAF14F82A5BB17809925813B) for additional explanation on the nuances between Analytics and Audience Manager data and segmentation.
