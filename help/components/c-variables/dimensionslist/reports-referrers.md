---
description: Visualizza il dominio o l’URL da cui i visitatori sono arrivati prima del loro arrivo sul sito, i metodi utilizzati dai visitatori per trovare il sito Web e il numero di visite al sito provenienti da queste posizioni di riferimento.
seo-description: Visualizza il dominio o l’URL da cui i visitatori sono arrivati prima del loro arrivo sul sito, i metodi utilizzati dai visitatori per trovare il sito Web e il numero di visite al sito provenienti da queste posizioni di riferimento.
seo-title: Riferimenti
solution: Analytics
title: Riferimenti
topic: Rapporti
uuid: e63b47b4-49f3-43af-8409-3272bec0484e
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Riferimenti

Visualizza il dominio o l’URL da cui i visitatori sono arrivati prima del loro arrivo sul sito, i metodi utilizzati dai visitatori per trovare il sito Web e il numero di visite al sito provenienti da queste posizioni di riferimento.

Ad esempio, se un visitatore fa clic su un collegamento dal sito A e arriva sul sito, il sito A è il referente se non è definito come parte del dominio. Durante l’implementazione, il consulente di implementazione può aiutarti a definire i domini e gli URL che fanno parte del tuo sito Web. (Questa modifica può essere eseguita dopo l’implementazione).

I domini o gli URL che non fanno parte di tali domini definiti e gli URL sono considerati referenti. Ad esempio, la pagina Web A e la pagina Web B vengono aggiunte al filtro URL interno, ma non la pagina Web C. In questo caso, la pagina Web C è considerata un referente.

## Assegnazione, scadenza e valori speciali {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reporting e analisi di marketing (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Analisi ad hoc </th> 
   <th colname="col4" class="entry"> Data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Allocazione metrica </td> 
   <td colname="col2"> Più recenti </td> 
   <td colname="col3"> Più recenti </td> 
   <td colname="col4"> Più recenti </td> 
  </tr> 
  <tr> 
   <td colname="col1"> I valori scadono dopo </td> 
   <td colname="col2"> Visita </td> 
   <td colname="col3"> Visita </td> 
   <td colname="col4"> Visita </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limiti valore </td> 
   <td colname="col2"> Nessun limite (potrebbe essere modificato in una versione futura) </td> 
   <td colname="col3"> Nessun limite (potrebbe essere modificato in una versione futura) </td> 
   <td colname="col4"> none </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori speciali </td> 
   <td colname="col2"> <p>"None": totali a livello di sito che non avevano un referente durante la visita. </p> </td> 
   <td colname="col3"> <p>"None": totali a livello di sito che non avevano un referente durante la visita. </p> </td> 
   <td colname="col4"> <p> Vuoto: equivalente a "None" (Nessuno), totali per l'intero sito che non avevano un referente durante la visita. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Note {#section_B83A3571D64E4E7792712FAF740D7955}

* Il referente, il tipo di referente e il dominio di provenienza vengono impostati sul primo hit della visita o durante una visita quando il referente è esterno (ad esempio, se un visitatore lascia il sito, utilizza un motore di ricerca e quindi ritorna al sito prima della scadenza della prima visita). Questi valori vengono impostati allo stesso tempo e persistono per tutta la visita.
* Gli URL interni vengono filtrati. In questo rapporto sono presenti solo i referenti che non corrispondono ai filtri URL interni.
* La metrica corrispondente è denominata Istanza di riferimento nell'analisi ad hoc.
* I valori digitati/con segnalibro non sono inclusi nel rapporto Referenti. Ciò significa che le visite a livello di sito non corrispondono alle visite in questo rapporto.

## Cronologia report {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

<table id="table_9DFA79EC6A5A48648F2FB5418E1752DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data </th> 
   <th colname="col2" class="entry"> Modifica </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1/16/2014 </td> 
   <td colname="col2"> Il data warehouse è stato aggiornato in base alla logica utilizzata da reporting e analisi di marketing. Prima di tale data, le parole chiave di ricerca non restavano invariate durante la visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6/19/2012 </td> 
   <td colname="col2"> <p> Prima di luglio 2012, "None" include tutto il traffico mobile, digitato/con segnalibro e le visite senza JavaScript. Dopo luglio 2012, "None" include solo gli hit senza JavaScript nella prima pagina della visita. </p> </td> 
  </tr> 
 </tbody> 
</table>

