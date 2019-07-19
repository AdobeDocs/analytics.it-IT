---
description: Una tabella di confronto per le API di reporting di Analytics. Sono forniti collegamenti alla documentazione di supporto.
seo-description: Una tabella di confronto per le API di reporting di Analytics. Sono forniti collegamenti alla documentazione di supporto.
seo-title: Confronto delle API di reporting Analisi
solution: Analytics
title: Confronto delle API di reporting Analisi
uuid: fa 533 a 8 e -33 c 0-42 f 4-a 294-cabee 0258 c 8 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Confronto delle API di reporting Analisi

Una tabella di confronto per le API di reporting di Analytics. Sono forniti collegamenti alla documentazione di supporto.

>[!NOTE]
>
>Riguardo alla latenza, Analytics per Target (A 4 T) combina i dati Analytics e Target sullo stesso hit per il reporting integrato. Poiché le chiamate Analytics e Target si verificano in momenti diversi, gli hit vengono memorizzati prima di qualsiasi elaborazione per raccogliere dati da entrambe le soluzioni. This process adds **an additional 7-10 minutes** of latency to all checkpoints.

<table id="table_7AF4FD678D494063ADF459B3CBC3EF3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo API </th> 
   <th colname="col2" class="entry"> Elaborato completamente </th> 
   <th colname="col3" class="entry"> Real-Time (Tempo reale) </th> 
   <th colname="col4" class="entry"> Livestream </th> 
   <th colname="col5" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Descrizione</b> </td> 
   <td colname="col2"> Dati completati completamente, che sono disponibili in tutte le interfacce di Analytics. </td> 
   <td colname="col3"> Metriche limitate e parzialmente elaborate disponibili entro i secondi della raccolta. </td> 
   <td colname="col4"> Dati hit parzialmente elaborati disponibili entro i secondi della raccolta. </td> 
   <td colname="col5"> Dati completati completamente elaborati, utilizzati per estrarre esportazioni di dati grandi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://marketing.adobe.com/resources/help/en_US/analytics/whitepapers/analytics-data-availability.pdf" format="https" scope="external"> Latenza</a> </p> </td> 
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
   <td colname="col1"> <a href="https://marketing.adobe.com/resources/help/en_US/reference/" format="https" scope="external"> Interfacce di reporting</a> </td> 
   <td colname="col2"> Reporting e analisi, Generatore di report, API </td> 
   <td colname="col3"> Report in tempo reale in Reporting e analisi, Generatore di report, API </td> 
   <td colname="col4"> Solo API </td> 
   <td colname="col5"> Data Warehouse e API </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Granularità dati</b> </td> 
   <td colname="col2"> Riepilogato </td> 
   <td colname="col3"> Riepilogato </td> 
   <td colname="col4"> Livello hit </td> 
   <td colname="col5"> Riepilogato </td> 
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
   <td colname="col1"> <b>SKU di Analytics</b> </td> 
   <td colname="col2"> Standard+ </td> 
   <td colname="col3"> Standard+ </td> 
   <td colname="col4"> Premium Complete o Predictive Intelligence </td> 
   <td colname="col5"> Standard+ </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Documentazione</b> </td> 
   <td colname="col2"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/get-started%E2%80%8B" format="https" scope="external"> Servizi web</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-reporting-1-4/real-time" format="https" scope="external"> Report in tempo reale</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://marketing.adobe.com/developer/documentation/analytics-live-stream/overview-1%E2%80%8B" format="https" scope="external"> Panoramica Livestream</a> </p> </td> 
   <td colname="col5"> <p><a href="https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse.html" format="https" scope="external"> Data Warehouse</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Argomenti correlati**

* [Adobe/IO](https://www.adobe.io/) - Una sorgente completa per la documentazione tecnica e gli strumenti necessari per integrare le tecnologie Adobe nelle applicazioni.
* [API query di Workbench dati](https://marketing.adobe.com/developer/documentation/data-workbench-query-api/c-ins-qry-api)

