---
description: Adobe richiede un preavviso per la configurazione di nuovi account, per i picchi e gli aumenti di traffico. L’hardware deve essere assegnato in anticipo per ridurre al minimo la latenza e gli eventuali impatti negativi sull’intero sistema.
title: Lead time richiesto per aumento di traffico
feature: Report Suite Settings
exl-id: fb428f8d-9dff-43a6-a1e8-1a892cbed7ac
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 100%

---

# Lead time richiesto per aumento di traffico

Adobe richiede un preavviso per la configurazione di nuovi account, per i picchi e gli aumenti di traffico. L’hardware deve essere assegnato in anticipo per ridurre al minimo la latenza e gli eventuali impatti negativi sull’intero sistema.

>[!IMPORTANT]
>
>Adobe non è in grado di soddisfare le richieste di modifica del “segnaposto” traffico. Se non diversamente indicato, rispetta il più possibile il lead time suggerito evitando di inviare un avviso troppo presto.

Per determinare con quanto anticipo è necessario inviare un avviso relativo al traffico, utilizza le seguenti linee guida:

## Lead time assegnazione hardware


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
   <td colname="col1"> Picco di traffico o aumento improvviso del traffico permanente fino al 25% del volume medio giornaliero rispetto agli ultimi 30 giorni</td>
   <td colname="col2"> <ul><li>Suite dei rapporti con &lt; 100 milioni di hit/giorno: non è richiesta alcuna notifica</li><li>Suite dei rapporti con &gt; 100 milioni di hit/giorno: 5 giorni lavorativi</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Picco di traffico o aumento improvviso del traffico permanente superiore al 25% del volume medio giornaliero rispetto agli ultimi 30 giorni</td>
   <td colname="col2"> <ul><li>5 giorni lavorativi</li></ul></td>
  </tr>
  <tr>
   <td colname="col1"> Eventi di vacanza ottobre - dicembre </td>
   <td colname="col2"> <ul><li>Un mese di calendario</li></ul> </td>
  </tr>
 </tbody>
</table>

Altri aspetti da considerare:

* Se disponi di diverse suite di rapporti in fase di avvio o aumento che si sommano ai numeri elencati in precedenza, il lead time si applica come somma del traffico previsto per ciascuna di esse.
* Per inviare una modifica del traffico, è necessario disporre delle seguenti informazioni:

   * ID suite di rapporti
   * Hit stimati al giorno
   * Data di pubblicazione

* Gli avvisi del client sono necessari anche quando il traffico diminuisce o una suite dei rapporti è obsoleta.

## Deallocazione dell’hardware a causa di traffico non realizzato

L’hardware per i nuovi account, i picchi e gli aumenti di traffico verranno deallocati se il traffico previsto nell’avviso del client non si concretizza entro 4 settimane dalla “data di pubblicazione”. Se il traffico è ancora previsto, è necessario generare un nuovo avviso del client come aumento del traffico.
