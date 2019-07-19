---
description: Descrizioni dei campi per Task Manager pianificati.
seo-description: Descrizioni dei campi per Task Manager pianificati.
seo-title: Scheduled Task Manager
solution: Analytics
title: Scheduled Task Manager
topic: Generatore di report
uuid: dec 259 f 0-2 a 04-4 c 94-abbc -5008 cf 2 f 1 cb 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Scheduled Task Manager

Descrizioni dei campi per Task Manager pianificati.

Gestione attività pianificata consente di visualizzare un elenco dei rapporti pianificati esistenti, oltre ai destinatari, ai dettagli sulla pianificazione e ai formati di file. Consente inoltre di riattivare le cartelle di lavoro pianificate che non sono state eseguite.

<table id="table_21B07A0B5F1D4435A4E882E45A7A6B6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Scheda Rapporti </b>pianificati </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome rapporto </p> </td> 
   <td colname="col2"> <p>Indica il nome dell'attività pianificata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> E-mail/FTP </p> </td> 
   <td colname="col2"> <p>Indirizzo e-mail o indirizzo FTP del destinatario. </p> <p>Nota: Se è selezionata l'e-mail, i rapporti più grandi di 1 MB vengono allegati automaticamente al messaggio e-mail come file.zip. Questa funzione consente di mantenere piccole dimensioni del file allegato e non può essere disattivata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opzioni pubblicazione </p> </td> 
   <td colname="col2"> <p>This column will list Power BI if one of the <a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#concept_0C4105AA10F9460A872C2489C9CD7945" format="dita" scope="local"> Power BI publishing options</a> is selected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pianificazione </p> </td> 
   <td colname="col2"> <p>Tipo di consegna pianificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Formato file </p> </td> 
   <td colname="col2"> <p> Formato di consegna del rapporto, come Excel, PDF, HTML e così via. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Riattiva </p> </td> 
   <td colname="col2"> <p>Quando una cartella di lavoro pianificata non viene eseguita, Generatore di report tenta di eseguire la cartella di lavoro due volte ogni cinque minuti. After three failed attempts, Report Builder deactivates the schedule and displays the <span class="wintitle"> Reactivate</span> button. Quando riattivate una cartella di lavoro, la distribuzione pianificata riavvia dal momento in cui è stata disattivata. </p> <p>Ad esempio, se una cartella di lavoro pianificata è stata disattivata 14 giorni fa e la riattivate oggi, viene eseguita per ogni giorno mancante e sarà distribuita 14 volte. Se non desiderate distribuire la cartella di lavoro per giorni mancanti, potete eliminare la cartella di lavoro pianificata e quindi creare una nuova cartella di lavoro pianificata utilizzando gli stessi parametri di programmazione. </p> <p> <p>Nota: Non dovete riattivare una cartella di lavoro a meno che non sappiate il motivo per cui il sistema lo disattiverà. Una soluzione di risoluzione dei problemi consiste nel scaricare una cartella di lavoro disattivata e aggiornarla sul lato client. Se non visualizzate errori, dovreste essere in grado di riattivarlo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ultima invio </p> </td> 
   <td colname="col2"> <p>Data e ora dell'ultima invio del rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Scheda Destinatario</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E-mail destinatario </p> </td> 
   <td colname="col2"> Destinatario e-mail del rapporto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rapporti </p> </td> 
   <td colname="col2"> Report/s inviati a ciascun destinatario. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Scheda Cronologia</b> rapporti </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome file </p> </td> 
   <td colname="col2"> Indica il nome dell'attività pianificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data </p> </td> 
   <td colname="col2"> Data e ora dell'ultima invio del rapporto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato </p> </td> 
   <td colname="col2"> Lo stato indica se il rapporto è stato inviato o Non inviato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E-mail/FTP </p> </td> 
   <td colname="col2"> L'indirizzo e-mail o l'indirizzo FTP del destinatario del rapporto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Formato file </p> </td> 
   <td colname="col2"> Formato di consegna del rapporto, come Excel, PDF, HTML e così via. </td> 
  </tr> 
 </tbody> 
</table>
