---
description: Ad Adobe, è necessario un preavviso per le nuove impostazioni account, i picchi di traffico e l’aumento del traffico. L'hardware deve essere assegnato in anticipo per ridurre al minimo la latenza e gli eventuali impatti negativi sul sistema nel suo complesso.
title: Tempo di lead richiesto per aumento di traffico
feature: Traffic Management
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: f9462d1b8b2795bec9dab9b479d4885fcaa92b5d
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 3%

---

# Tempo di lead richiesto per aumento di traffico

Ad Adobe, è necessario un preavviso per le nuove impostazioni account, i picchi di traffico e l’aumento del traffico. L&#39;hardware deve essere assegnato in anticipo per ridurre al minimo la latenza e gli eventuali impatti negativi sul sistema nel suo complesso.

L’allocazione dell’hardware è guidata dagli avvisi inviati tramite l’interfaccia utente di Reports &amp; Analytics.

>[!IMPORTANT]
>
>Adobe non è in grado di soddisfare le richieste di modifica del traffico &quot;segnaposto&quot;. Se non diversamente indicato, rispettare il lead time suggerito il più vicino possibile, compreso il mancato invio di un avviso troppo presto. Vedi [Pianificare un picco di traffico](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) o [Specifica aumento traffico permanente](/help/admin/c-traffic-management/t-traffic-permanent.md).

Per determinare con quale anticipo è necessario inviare un avviso di traffico, attenersi alle seguenti linee guida:

## Lead time di allocazione hardware


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Tipo di modifica del traffico </th>
   <th colname="col2" class="entry"> Lead time necessario </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Nuova configurazione account </td>
   <td colname="col2"> <ul><li>3 giorni lavorativi</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Aumento improvviso del traffico permanente fino al 25% in volume medio giornaliero rispetto agli ultimi 30 giorni</td>
   <td colname="col2"> <ul><li>Suite di rapporti con &lt; 100M hit/giorno: Nessuna notifica richiesta</li><li>Suite di rapporti con &gt; 100M hit/giorno: 5 giorni lavorativi</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Aumento improvviso del traffico permanente di oltre il 25% in volume medio giornaliero rispetto agli ultimi 30 giorni</td>
   <td colname="col2"> <ul><li>5 giorni lavorativi</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Eventi festivi Ottobre - Dicembre </td>
   <td colname="col2"> <ul><li>Un mese di calendario</li></ul> </td>
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
