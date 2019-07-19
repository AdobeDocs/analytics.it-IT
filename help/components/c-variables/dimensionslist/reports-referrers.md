---
description: Visualizza il dominio o l'URL in cui i visitatori provengono prima che arrivino sul sito, i metodi utilizzati dai visitatori per trovare il tuo sito Web e il numero di visite al tuo sito derivanti da queste posizioni di provenienza.
seo-description: Visualizza il dominio o l'URL in cui i visitatori provengono prima che arrivino sul sito, i metodi utilizzati dai visitatori per trovare il tuo sito Web e il numero di visite al tuo sito derivanti da queste posizioni di provenienza.
seo-title: Referenti
solution: Analytics
title: Referenti
topic: Rapporti
uuid: e 63 b 47 b 4-49 f 3-43 af -8409-3272 bec 0484 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Referenti

Visualizza il dominio o l'URL in cui i visitatori provengono prima che arrivino sul sito, i metodi utilizzati dai visitatori per trovare il tuo sito Web e il numero di visite al tuo sito derivanti da queste posizioni di provenienza.

Ad esempio, se un visitatore fa clic su un collegamento dal Sito A e accede al sito, il Sito A è il referente se non viene definito come parte del dominio. Durante l'implementazione, il consulente di implementazione può aiutarti a definire i domini e gli URL che fanno parte del tuo sito Web. (Questa modifica può essere effettuata dopo l'implementazione.)

I domini o gli URL che non fanno parte di tali domini e URL definiti sono considerati referenti. Ad esempio, la pagina Web A e la pagina Web B vengono aggiunte al filtro URL interno, mentre la pagina Web C non lo è. In questo caso, la pagina Web C è considerata un referente.

## Allocation, Expiration, and Special Values {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reporting e analisi di marketing (sitecatalyst) </th> 
   <th colname="col3" class="entry"> Analisi ad hoc </th> 
   <th colname="col4" class="entry"> Data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Allocazione metrica </td> 
   <td colname="col2"> Più recente </td> 
   <td colname="col3"> Più recente </td> 
   <td colname="col4"> Più recente </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori scaduti dopo </td> 
   <td colname="col2"> Visita </td> 
   <td colname="col3"> Visita </td> 
   <td colname="col4"> Visita </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limiti valore </td> 
   <td colname="col2"> Nessun limite (potrebbe subire modifiche in una release futura) </td> 
   <td colname="col3"> Nessun limite (potrebbe subire modifiche in una release futura) </td> 
   <td colname="col4"> none </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori speciali </td> 
   <td colname="col2"> <p>" None ": totali del sito che non avevano un referente durante la visita. </p> </td> 
   <td colname="col3"> <p>" None ": totali del sito che non avevano un referente durante la visita. </p> </td> 
   <td colname="col4"> <p> Vuoto - equivalente di "None", del sito wide wide che non aveva un referente durante la visita. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Note {#section_B83A3571D64E4E7792712FAF740D7955}

* Il referente, il tipo di referente e il dominio di provenienza sono impostati al primo hit della visita, oppure durante una visita quando il referente è esterno (ad esempio, se un visitatore lascia il sito, utilizza un motore di ricerca, quindi ritorna al sito prima della scadenza della prima visita). Questi valori vengono impostati contemporaneamente e persistono nella visita.
* Gli URL interni vengono filtrati. Questo rapporto contiene solo i riferimenti che non corrispondono ai filtri URL interni.
* La metrica corrispondente si chiama Istanza referente in analisi ad hoc.
* I valori digitati/segnalibri non sono inclusi nel rapporto Referenti. Ciò significa che le visite al sito non corrispondono alle visite su questo rapporto.

## Report History {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

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
   <td colname="col2"> Data warehouse è stato aggiornato per corrispondere alla logica utilizzata da reporting e analisi di marketing. Prima di questa data, le parole chiave di ricerca non venivano mantenute nella visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6/19/2012 </td> 
   <td colname="col2"> <p> Prima di luglio 2012, «None» include tutto il traffico mobile, il tipo Typed/Bookmarked e le visite senza javascript. Dopo luglio 2012, "None" (Nessuno) include solo gli hit senza javascript nella prima pagina di visita. </p> </td> 
  </tr> 
 </tbody> 
</table>

