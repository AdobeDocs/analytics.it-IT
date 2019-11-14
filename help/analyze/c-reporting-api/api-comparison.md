---
description: Una tabella di confronto per le API di reporting di Analytics. Vengono forniti collegamenti alla documentazione di supporto.
solution: Analytics
title: Confronto delle API di reportistica di Analytics
uuid: fa533a8e-33c0-42f4-a294-cabee0258c8f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Confronto delle API di reportistica di Analytics

Una tabella di confronto per le API di reporting di Analytics. Vengono forniti collegamenti alla documentazione di supporto.

> [!NOTE] Per quanto riguarda la latenza, Analytics per Target (A4T) combina i dati di Analytics e Target con lo stesso hit per il reporting integrato. Poiché le chiamate Analytics e Target si verificano in momenti diversi, gli hit vengono memorizzati prima che venga elaborata qualsiasi volta per raccogliere i dati da entrambe le soluzioni. Questo processo aggiunge **una latenza supplementare di 7-10 minuti** a tutti i checkpoint.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo API </th> 
   <th colname="col2" class="entry"> Elaborazione Completa </th> 
   <th colname="col3" class="entry"> Real-Time (Tempo reale) </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Descrizione</b> </td> 
   <td colname="col2"> Dati completamente elaborati e finalizzati disponibili in tutte le interfacce di Analytics. </td> 
   <td colname="col3"> Metriche limitate elaborate parzialmente disponibili entro pochi secondi dalla raccolta. </td> 
   <td colname="col4"> Dati hit elaborati parzialmente disponibili entro pochi secondi dalla raccolta. </td> 
   <td colname="col5"> Dati completamente elaborati e finalizzati utilizzati per il pulling di grandi esportazioni di dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf"  > Latenza</a> </p> </td> 
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
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/"  > Interfacce di reporting</a> </td> 
   <td colname="col2"> Reporting e analisi, Generatore di report, API </td> 
   <td colname="col3"> Report in tempo reale in Reporting e analisi, Generatore di report, API </td> 
   <td colname="col4"> Solo API </td> 
   <td colname="col5"> Data Warehouse e API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Granularità dei dati</b> </td> 
   <td colname="col2"> Riepilogo </td> 
   <td colname="col3"> Riepilogo </td> 
   <td colname="col4"> Livello hit </td> 
   <td colname="col5"> Riepilogo </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Elaborazione profilo visitatori</b> </td> 
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
   <td colname="col1"> <b>SKU di Analytics</b> </td> 
   <td colname="col2"> Standard+ </td> 
   <td colname="col3"> Standard+ </td> 
   <td colname="col4"> Informazioni complete o predittive </td> 
   <td colname="col5"> Standard+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Documentazione</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B"  > Servizi web</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time"  > Rapporti in tempo reale</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B"  > Panoramica di Livestream</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse.html"  > Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Argomenti correlati**

* [Adobe/IO](https://www.adobe.io/) - Una fonte completa per la documentazione tecnica e gli strumenti necessari per integrare le tecnologie Adobe nelle applicazioni.
* [API query Workbench dati](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

