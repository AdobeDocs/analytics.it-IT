---
description: Quando configurate un feed, alcune impostazioni determinano la frequenza con cui vengono elaborati i processi.
keywords: Feed dati; processo; impostazioni; giornaliere; orario; Recupero di dati per feed di dati orari; backfill
seo-description: Quando configurate un feed, alcune impostazioni determinano la frequenza con cui vengono elaborati i processi.
seo-title: Impostazioni dei processi
solution: Analytics
title: Impostazioni dei processi
uuid: e 124 b 4 f 1-0168-4 eaa -8657-19207 b 2 f 263 f
translation-type: tm+mt
source-git-commit: b6169d2febded32d772f82d5917b1132695ab442

---


# Impostazioni dei processi

Quando configurate un feed, alcune impostazioni determinano la frequenza con cui vengono elaborati i processi.

Utilizzate le impostazioni seguenti per configurare i tempi di elaborazione dei processi. Queste impostazioni sono impostate a livello di feed, non a livello di processo.

<table id="table_2070F73212F245E98DADC6B5DFDB1C72"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Giornaliero </td> 
   <td colname="col2"> <p>I dati di ogni giorno vengono consegnati in un unico file compresso. Il file ha un limite di dimensione pari a 2 GB. Se il file contiene più di 2 GB di dati non compressi, vengono creati altri file. Riceverete una singola consegna di tutti i file per ogni giorno. </p> <p>A ciascun file viene assegnato il nome seguente: </p> <p> <span class="filepath"><span class="varname"> reportsuite</span>-<span class="varname"> date</span>.tar</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Orario (predefinito) </td> 
   <td colname="col2"> <p>I dati per ogni ora vengono consegnati in un singolo file compresso contenente tutti i dati ricevuti durante quell'ora. Riceverete 24 consegne separate per ogni giorno, con ogni file distribuito dopo l'elaborazione dei dati per quell'ora. </p> <p>Il termine «orario» descrive il periodo di tempo dei dati inviati con ogni singola esportazione dati e non il periodo di tempo in cui si verifica la consegna. I feed di dati orari vengono elaborati e consegnati in modo ottimale. </p> <p>Per i feed di dati orari si attende che il 95% delle ore in cui il feed distribuirà il feed entro 12 ore dalla data di dati di quell'ora. I feed di dati per suite di rapporti con volume di traffico elevato potrebbero richiedere più tempo per l'elaborazione e la distribuzione. </p> <p>La ricezione di feed di dati orari è diversa e quindi riceve feed giornalieri con più file. Quando ricevi dati orari, i dati di ogni giorno vengono suddivisi in 24 file in base ai dati raccolti durante quella ora e ogni file viene distribuito non appena disponibile. Un feed giornaliero distribuito in più file viene distribuito una volta al giorno al momento dell'elaborazione dei dati del giorno precedente e viene aumentato a incrementi di 2 GB in base alla quantità di dati raccolti. </p> <p>A ciascun file viene assegnato il nome seguente: </p> <p> <span class="filepath"><span class="varname"> reportsuite</span>-<span class="varname"> date</span>-<span class="varname"> hour</span>.tar</span> </p> <p>See <a href="../../../export/analytics-data-feed/c-df-contents/jobs-faq.md#concept_7C67A012CCF64B0C8DA33E5A6CF7FD9E" format="dita" scope="local"> Jobs FAQ</a> for more information about factors that can impact hourly feeds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recupero di dati per feed di dati orari </td> 
   <td colname="col2"> <p>Se durante la configurazione di un nuovo feed di dati orario si richiedono dati per date precedenti, i dati relativi alle date precedenti a 60 giorni potrebbero essere consegnati con cadenza giornaliera e non oraria. </p> <p>In tal caso non si riceveranno 24 consegne separate per i giorni specificati, ma si riceverà un'unica consegna con data e ora corrispondente a mezzanotte e contenente tutti i dati relativi al giorno specificato. Se si richiede questo tipo di recupero di informazioni, verificare che ETL sia configurato per l'elaborazione delle consegne giornaliere. </p> </td> 
  </tr> 
 </tbody> 
</table>

