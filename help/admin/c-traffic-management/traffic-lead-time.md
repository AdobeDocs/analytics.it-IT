---
description: Ad Adobe, è necessario un preavviso per le nuove impostazioni account, i picchi di traffico e l’aumento del traffico. L'hardware deve essere assegnato in anticipo per ridurre al minimo la latenza e gli eventuali impatti negativi sul sistema nel suo complesso.
title: Tempo di lead richiesto per aumento di traffico
feature: Admin Tools
uuid: aa3fb882-51b0-458f-917b-7c54d5659623
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 5%

---

# Tempo di lead richiesto per aumento di traffico

Ad Adobe, è necessario un preavviso per le nuove impostazioni account, i picchi di traffico e l’aumento del traffico. L&#39;hardware deve essere assegnato in anticipo per ridurre al minimo la latenza e gli eventuali impatti negativi sul sistema nel suo complesso.

L’allocazione dell’hardware è guidata dagli avvisi inviati tramite l’interfaccia utente di Reports &amp; Analytics.

>[!IMPORTANT]
>
>Adobe non è in grado di soddisfare le richieste di modifica del traffico &quot;segnaposto&quot;. Se non diversamente indicato, rispettare il lead time suggerito il più vicino possibile, compreso il mancato invio di un avviso troppo presto. Consulta [Pianificare un picco di traffico](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) o [Specificare un aumento di traffico permanente](/help/admin/c-traffic-management/t-traffic-permanent.md).

Per determinare con quale anticipo è necessario inviare un avviso di traffico, attenersi alle seguenti linee guida:

## Lead time di allocazione hardware

<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Stime giornaliere del traffico (hit) </th>
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
   <td colname="col1"> 1.000.000 - 5.000.000 </td>
   <td colname="col2"> Due giorni lavorativi </td>
   <td colname="col3" morerows="3"> Tutti gli aumenti di traffico previsti per novembre-dicembre devono essere presentati entro il 1° settembre. In questo modo, è possibile disporre del tempo necessario per l'acquisto della capacità necessaria per accogliere il traffico delle vacanze. </td>
  </tr>
  <tr>
   <td colname="col1"> 5.000.000 - 10.000.000 </td>
   <td colname="col2"> Una settimana di calendario </td>
  </tr>
  <tr>
   <td colname="col1"> 10.000.000 - 25.000.000 </td>
   <td colname="col2"> Due settimane di calendario </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Superiore a 25.000.000 </p> </td>
   <td colname="col2"> Uno o più mesi </td>
  </tr>
 </tbody>
</table>

Altri aspetti da considerare:

* Se hai diverse suite di rapporti che iniziano o aumentano fino ai numeri elencati sopra, il lead time si applica come somma del traffico previsto per ciascuna di esse.
* Avere a disposizione le seguenti informazioni per inviare una modifica del traffico:

   * ID suite di rapporti
   * Risultati stimati al giorno
   * Data di pubblicazione

* Gli avvisi client sono necessari anche quando il traffico diminuisce o una suite di rapporti è deprecata.

## Disallocazione hardware a causa di traffico non realizzato

L&#39;hardware per i nuovi account, i picchi di traffico e gli aumenti di traffico verranno deallocati se il traffico previsto nell&#39;avviso del cliente non si materializza entro 4 settimane dalla &quot;data di inizio&quot;. Se il traffico è ancora in attesa, è necessario generare un nuovo avviso al cliente come aumento di traffico.
