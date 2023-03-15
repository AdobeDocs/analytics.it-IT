---
description: L’Adobe richiede un preavviso per le nuove impostazioni dell’account, i picchi di traffico e gli aumenti di traffico. L'hardware deve essere allocato in anticipo per ridurre al minimo la latenza e i possibili effetti negativi sul sistema complessivo.
title: Tempo di lead richiesto per aumento di traffico
feature: Traffic Management
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 55c8337dbeebcc76db367ead15128c095e4d8ce5
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 5%

---

# Tempo di lead richiesto per aumento di traffico

## Tempo di lead richiesto per aumento di traffico

L’Adobe richiede un preavviso per le nuove impostazioni dell’account, i picchi di traffico e gli aumenti di traffico. L&#39;hardware deve essere allocato in anticipo per ridurre al minimo la latenza e i possibili effetti negativi sul sistema complessivo.

L’allocazione dell’hardware è guidata dagli avvisi inviati tramite l’interfaccia utente di Reports &amp; Analytics.

>[!IMPORTANT]
>
>L’Adobe non può soddisfare le richieste di modifica del traffico &quot;placeholder&quot;. Se non diversamente indicato, attieniti il più possibile al lead time suggerito, anche evitando di inviare un avviso troppo presto.

Utilizza le seguenti linee guida per determinare con quale anticipo devi inviare un avviso relativo al traffico:

### Lead time allocazione hardware


<table id="table_A67CC3B164F740088797BD8913244E47">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Tipo di modifica del traffico </th>
   <th colname="col2" class="entry"> Lead time necessario </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Configurazione nuovo account </td>
   <td colname="col2"> <ul><li>3 giorni lavorativi</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Picco di traffico o improvviso aumento del traffico permanente fino al 25% del volume medio giornaliero rispetto agli ultimi 30 giorni</td>
   <td colname="col2"> <ul><li>Suite di rapporti con &lt; 100 milioni di hit/die: non è richiesta alcuna notifica</li><li>Suite di rapporti con &gt; 100 milioni di hit/giorno: 5 giorni lavorativi</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Picco di traffico o improvviso aumento permanente del traffico superiore al 25% del volume medio giornaliero rispetto agli ultimi 30 giorni</td>
   <td colname="col2"> <ul><li>5 giorni lavorativi</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Eventi di vacanza ottobre - dicembre </td>
   <td colname="col2"> <ul><li>Un mese di calendario</li></ul> </td>
  </tr>
 </tbody>
</table>

Altri aspetti da considerare:

* Se hai diverse suite di rapporti in fase di avvio o aumento che si sommano ai numeri elencati sopra, il lead time si applica come somma del traffico previsto per ciascuna di esse.
* Per inviare una modifica del traffico, è necessario disporre delle seguenti informazioni:

   * ID suite di rapporti
   * Hit stimati al giorno
   * Data di pubblicazione

* Gli avvisi del client sono necessari anche quando il traffico diminuisce o una suite di rapporti è obsoleta.

### Disallocazione hardware a causa di traffico non realizzato

L&#39;hardware per i nuovi account, i picchi di traffico e gli aumenti di traffico verranno deallocati se il traffico previsto nell&#39;avviso del client non si materializza entro 4 settimane dalla data di lancio. Se il traffico è ancora previsto, deve essere generato un nuovo avviso client con un aumento del traffico.
