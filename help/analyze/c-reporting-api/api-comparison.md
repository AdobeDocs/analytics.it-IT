---
description: Una tabella di confronto per le API di reporting di Analytics. Vengono forniti collegamenti alla documentazione di supporto.
title: Confronto delle API di reportistica di Analytics
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
translation-type: tm+mt
source-git-commit: 49875f086be6fe47552f50b41d8111179039f7c4
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 90%

---


# Confronto delle API di reportistica di Analytics

Una tabella di confronto per le API di reporting di Analytics. Vengono forniti collegamenti alla documentazione di supporto.

>[!NOTE]
>
>Per quanto riguarda la latenza, Analytics for Target (A4T) combina i dati di Analytics e di Target sullo stesso hit per il reporting integrato. Poiché le chiamate Analytics e Target si verificano in momenti diversi, gli hit vengono memorizzati prima di eventuali elaborazioni per raccogliere i dati da entrambe le soluzioni. Questo processo aggiunge una latenza **supplementare di 7-10 minuti** a tutti i punti di controllo.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo API </th> 
   <th colname="col2" class="entry"> Elaborazione completa </th> 
   <th colname="col3" class="entry"> Tempo reale </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Descrizione</b> </td> 
   <td colname="col2"> Dati completamente elaborati e finalizzati disponibili in tutte le interfacce di Analytics. </td> 
   <td colname="col3"> Metriche limitate ed elaborate parzialmente, disponibili entro pochi secondi dalla raccolta. </td> 
   <td colname="col4"> Dati dei risultati elaborati parzialmente, disponibili entro pochi secondi dalla raccolta. </td> 
   <td colname="col5"> Dati completamente elaborati e finalizzati utilizzati per eseguire il pull di esportazioni dati di grandi dimensioni. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://docs.adobe.com/content/help/it-IT/analytics/technotes/latency.translate.html"  > Latenza</a> </p> </td> 
   <td colname="col2"> 30-90 minuti </td> 
   <td colname="col3"> * Secondi -10 minuti </td> 
   <td colname="col4"> Secondi -10 minuti </td> 
   <td colname="col5"> 90 minuti + </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Completamento elaborazione</b> </td> 
   <td colname="col2"> a schermo intero </td> 
   <td colname="col3"> Parziale </td> 
   <td colname="col4"> Parziale </td> 
   <td colname="col5"> a schermo intero </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <a href="https://docs.adobe.com/content/help/it-IT/analytics/landing/home.html"  > Interfacce di reporting</a> </td> 
   <td colname="col2">  Analysis Workspace, Reporting e  Analytics, Report Builder, API </td> 
   <td colname="col3"> Report in tempo reale in Reporting e  Analytics, Report Builder, API 1.4 </td> 
   <td colname="col4"> Solo API </td> 
   <td colname="col5"> Data Warehouse e API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Granularità dei dati</b> </td> 
   <td colname="col2"> Di riepilogo </td> 
   <td colname="col3"> Di riepilogo </td> 
   <td colname="col4"> Livello di hit </td> 
   <td colname="col5"> Di riepilogo </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Elaborazione profilo visitatore</b> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> No </td> 
   <td colname="col5"> Sì </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Supporta i segmenti</b> </td> 
   <td colname="col2"> Sì </td> 
   <td colname="col3"> No </td> 
   <td colname="col4"> No </td> 
   <td colname="col5"> Sì (ma solo segmenti compatibili con Data Warehouse) </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <b>Documentazione</b> </td> 
   <td colname="col2"> <p> <a href="https://www.adobe.io/apis/experiencecloud/analytics/docs.html"  > API di Analytics</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://github.com/AdobeDocs/analytics-1.4-apis"  > Rapporti in tempo reale</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md"  > Panoramica di Livestream</a> </p> </td> 
   <td colname="col5"> <p><a href="https://docs.adobe.com/content/help/it-IT/analytics/export/data-warehouse/data-warehouse.translate.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Argomenti correlati**

* [Adobe I/O](https://www.adobe.io/): una fonte completa per la documentazione tecnica e gli strumenti necessari per integrare le tecnologie Adobe nelle applicazioni.
* [API di query di Data Workbench](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

