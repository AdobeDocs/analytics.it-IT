---
description: Adobe richiede un avviso anticipato per le nuove impostazioni account, le picchi del traffico e il traffico aumentano. L'hardware deve essere allocato in anticipo per ridurre la latenza e possibili conseguenze negative per il sistema globale.
seo-description: Adobe richiede un avviso anticipato per le nuove impostazioni account, le picchi del traffico e il traffico aumentano. L'hardware deve essere allocato in anticipo per ridurre la latenza e possibili conseguenze negative per il sistema globale.
seo-title: Tempo di lead richiesto per aumentare il traffico
solution: Analytics
title: Tempo di lead richiesto per aumentare il traffico
topic: Strumenti di amministrazione
uuid: aa 3 fb 882-51 b 0-458 f -917 b -7 c 54 d 5659623
translation-type: tm+mt
source-git-commit: e373297bcf1c9ae0f421ed246125204f31c39cc3

---


# Tempo di lead richiesto per aumentare il traffico

Adobe richiede un avviso anticipato per le nuove impostazioni account, le picchi del traffico e il traffico aumentano. L'hardware deve essere allocato in anticipo per ridurre la latenza e possibili conseguenze negative per il sistema globale.

L'allocazione di hardware è basata sugli avvisi inviati tramite l'interfaccia utente di reporting e analisi.

> [!IMPORTANT] Adobe non può contenere richieste di modifica del traffico "segnaposto". Se non diversamente indicato, aderisci al tempo di lead suggerito il più vicino possibile, incluso l'invio di un avviso troppo presto. See [Schedule a traffic spike](../../admin/c-traffic-management/t-traffic-schedule-spike.md) or [Specify permanent traffic increase](../../admin/c-traffic-management/t-traffic-permanent.md).

Per determinare la distanza in anticipo, utilizzate le seguenti linee guida:

## Orari lead allocazione hardware

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Stime traffico giornaliere (hit) </th>
   <th colname="col2" class="entry"> <p>Tempo lead necessario (gennaio - Ottobre) </p> </th>
   <th colname="col3" class="entry"> <p>Tempo lead necessario (novembre - Dicembre) </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Fino a 1,000,000 </td>
   <td colname="col2"> Nessun tempo di lead necessario </td>
   <td colname="col3"> Nessun tempo di lead necessario </td>
  </tr>
  <tr>
   <td colname="col1"> 1,000,000 - 5,000,000 </td>
   <td colname="col2"> Due giorni LAVORATIVI </td>
   <td colname="col3" morerows="3"> Tutti gli incrementi del traffico destinati a novembre-dicembre devono essere inviati entro il 1 settembre. Per consentire il traffico delle festività, se necessario è possibile utilizzare la capacità di acquisto. </td>
  </tr>
  <tr>
   <td colname="col1"> 5,000,000 - 10,000,000 </td>
   <td colname="col2"> Una settimana di calendario </td>
  </tr>
  <tr>
   <td colname="col1"> 10,000,000 - 25,000,000 </td>
   <td colname="col2"> Due settimane di calendario </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Sopra 25,000,000 </p> </td>
   <td colname="col2"> Uno o più mesi </td>
  </tr>
 </tbody>
</table>

Altri aspetti da tenere in considerazione:

* Se hai numerose suite di rapporti che iniziano o aumentano in base ai numeri elencati qui sopra, il tempo lead si applica come una somma del traffico previsto per ciascuno di essi.
* Per inviare una modifica traffico, sono disponibili le seguenti informazioni:

   * ID suite di rapporti
   * Hit stimati al giorno
   * Data live

* Gli avvisi client sono necessari anche quando si riducono le riduzioni del traffico o una suite di rapporti.

## Attribuzione hardware a causa di traffico non realizzato

Hardware per nuovi account, picchi di traffico e aumenti del traffico verranno soggetti a allocazione se il traffico proiettato nell'avviso client non viene materializzato entro 4 settimane dalla "Data live". Se il traffico è ancora previsto, un nuovo avviso client deve essere generato come un incremento del traffico.
