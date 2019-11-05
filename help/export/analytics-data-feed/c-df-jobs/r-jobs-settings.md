---
description: Quando configurate un feed, alcune impostazioni determinano la frequenza di elaborazione dei processi.
keywords: Feed dati;processo;impostazioni;giornaliero;ogni ora;Recupero dati per feed di dati orari;backfill
seo-description: Quando configurate un feed, alcune impostazioni determinano la frequenza di elaborazione dei processi.
seo-title: Impostazioni dei processi
solution: Analytics
title: Impostazioni dei processi
uuid: e124b4f1-0168-4eaa-8657-19207b2f263f
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# Impostazioni dei processi

Quando configurate un feed, alcune impostazioni determinano la frequenza di elaborazione dei processi.

Utilizzate le seguenti impostazioni per configurare i tempi di elaborazione dei processi. Queste impostazioni sono impostate a livello di feed, non a livello di processo.

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
   <td colname="col2"> <p>I dati per ogni giorno vengono inviati in un singolo file compresso. Questo file ha un limite di dimensioni di 2 GB. Se il file supera i 2 GB di dati non compressi, vengono creati file aggiuntivi. Riceverete una singola consegna di tutti i file per ogni giorno. </p> <p>Ogni file è denominato nel seguente formato: </p> <p> <span class="filepath"> <span class="varname"> report-suite</span>-<span class="varname"> date</span>.tar</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Orario (predefinito) </td> 
   <td colname="col2"> <p>I dati relativi a ogni ora vengono inviati in un singolo file compresso contenente tutti i dati ricevuti durante quell'ora. Riceverete 24 consegne separate per ogni giorno, con ogni file consegnato dopo l'elaborazione dei dati per quell'ora. </p> <p>Il termine "ogni ora" descrive l'intervallo di tempo dei dati inviati con ogni singola esportazione di dati, e non l'intervallo di tempo in cui avviene la consegna. I feed di dati orari vengono elaborati e consegnati nel miglior modo possibile. </p> <p>Per i feed di dati orari l'aspettativa è che il 95% delle volte che il feed consegnerà entro 12 ore dalla fine del valore di dati di quell'ora. I feed di dati per le suite di rapporti con un volume di traffico elevato potrebbero richiedere più tempo per l'elaborazione e la distribuzione. </p> <p>La ricezione di un feed di dati ogni ora è diversa rispetto alla ricezione di feed giornalieri con consegna di più file. Quando ricevete feed di dati orari, i dati per ogni giorno vengono suddivisi in 24 file in base ai dati raccolti durante quell'ora, e ogni file viene consegnato non appena disponibile. Un feed giornaliero distribuito in più file viene distribuito una volta al giorno dopo l'elaborazione dei dati del giorno precedente e viene distribuito in incrementi di 2 GB in base alla quantità di dati raccolti. </p> <p>Ogni file è denominato nel seguente formato: </p> <p> <span class="filepath"> reportsuite <span class="varname"> -</span>data<span class="varname"> -</span>ora<span class="varname"></span>.tar</span> </p> <p>Consultate <a href="/help/export/analytics-data-feed/c-df-contents/jobs-faq.md"  > Domande frequenti</a> sui processi per ulteriori informazioni sui fattori che possono avere un impatto sui feed orari. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Recupero dei dati per feed di dati orari </td> 
   <td colname="col2"> <p>Se durante la configurazione di un nuovo feed di dati orario si richiedono dati per date precedenti, i dati relativi alle date precedenti a 60 giorni potrebbero essere consegnati con cadenza giornaliera e non oraria. </p> <p>In tal caso non si riceveranno 24 consegne separate per i giorni specificati, ma si riceverà un'unica consegna con data e ora corrispondente a mezzanotte e contenente tutti i dati relativi al giorno specificato. Se si richiede questo tipo di recupero di informazioni, verificare che ETL sia configurato per l'elaborazione delle consegne giornaliere. </p> </td> 
  </tr> 
 </tbody> 
</table>

