---
description: ' Adobe richiede un preavviso per nuove impostazioni account, picchi di traffico e aumenti di traffico. L''hardware deve essere allocato in anticipo per ridurre al minimo la latenza e gli eventuali impatti negativi sul sistema.'
title: Tempo di lead richiesto per aumento di traffico
topic: Admin tools
uuid: aa3fb882-51b0-458f-917b-7c54d5659623
translation-type: tm+mt
source-git-commit: a114bef4679da24d4fd6323a55c9ccf52ac772ed
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 4%

---


# Tempo di lead richiesto per aumento di traffico

 Adobe richiede un preavviso per nuove impostazioni account, picchi di traffico e aumenti di traffico. L&#39;hardware deve essere allocato in anticipo per ridurre al minimo la latenza e gli eventuali impatti negativi sul sistema.

L&#39;allocazione dell&#39;hardware è guidata dagli avvisi inviati tramite l&#39;interfaccia utente di reporting e analisi.

>[!IMPORTANT]
>
> Adobe non può contenere le richieste di modifica del traffico &quot;segnaposto&quot;. Salvo indicazione contraria, rispettare il termine di segnalazione proposto il più vicino possibile, compreso il mancato invio di un avviso troppo presto. Consultate [Pianificare un picco](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) di traffico o [Specificare un aumento](/help/admin/c-traffic-management/t-traffic-permanent.md)di traffico permanente.

Utilizzate le seguenti linee guida per determinare con quale anticipo è necessario inviare un avviso di traffico:

## Lead time di allocazione hardware

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Stime del traffico giornaliere (hit) </th>
   <th colname="col2" class="entry"> <p>Lead time necessario (gennaio - ottobre) </p> </th>
   <th colname="col3" class="entry"> <p>Lead time necessario (novembre - dicembre) </p> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Fino a 1.000.000 </td>
   <td colname="col2"> Nessun lead time necessario </td>
   <td colname="col3"> Nessun lead time necessario </td>
  </tr>
  <tr>
   <td colname="col1"> 1,000,000 - 5,000,000 </td>
   <td colname="col2"> Due giorni lavorativi </td>
   <td colname="col3" morerows="3"> Tutti gli aumenti di traffico previsti per novembre-dicembre dovrebbero essere presentati entro il 1° settembre. In questo modo si concederà il tempo necessario per l'acquisto della capacità, se necessario, per accogliere il traffico delle vacanze. </td>
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
   <td colname="col1"> <p>Oltre 25.000.000 </p> </td>
   <td colname="col2"> Uno o più mesi </td>
  </tr>
 </tbody>
</table>

Altre considerazioni da prendere in considerazione:

* Se hai diverse suite di rapporti che iniziano o aumentano fino ai numeri sopra elencati, il lead time si applica come somma del traffico previsto per ognuna di esse.
* Per inviare una modifica al traffico sono disponibili le seguenti informazioni:

   * ID suite di rapporti
   * Stima hit al giorno
   * Data Go-live

* Gli avvisi client sono necessari anche quando il traffico diminuisce o una suite di rapporti è obsoleta.

## Disallocazione hardware a causa di traffico non realizzato

L&#39;hardware per i nuovi account, i picchi di traffico e gli aumenti di traffico verranno deallocati se il traffico previsto nell&#39;avviso del cliente non si materializza entro 4 settimane dalla &quot;data di inizio&quot;. Se il traffico è ancora previsto, è necessario generare un nuovo avviso client come aumento del traffico.
