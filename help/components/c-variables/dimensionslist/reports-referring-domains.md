---
description: Mostra i domini che fanno riferimento ai clienti che hanno più inciso sulle metriche di successo del sito. I referenti appartengono a due categorie principali Domini e URL. I domini fanno riferimento al nome del dominio e vengono visualizzati come dominio di base senza la stringa di query o le sottodirectory associate. Gli URL includono il nome del dominio di base, nonché eventuali stringhe di query o sottodirectory.
solution: Analytics
title: Domini di riferimento
topic: Reports
uuid: ab310bb8-51b1-4428-a42e-2377d36ca986
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Domini di riferimento

Mostra i domini che fanno riferimento ai clienti che hanno più inciso sulle metriche di successo del sito. I riferimenti sono suddivisi in due categorie principali: Domini e URL. I domini fanno riferimento al nome del dominio e vengono visualizzati come dominio di base senza la stringa di query o le sottodirectory associate. Gli URL includono il nome del dominio di base, nonché eventuali stringhe di query o sottodirectory.

## Assegnazione, scadenza e valori speciali {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reporting e analisi </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Allocazione metrica </td> 
   <td colname="col2"> <p>Più recenti </p> </td> 
   <td colname="col3"> <p>Più recente (può essere modificato in lineare utilizzando la versione lineare di un metic) </p> </td> 
   <td colname="col4"> <p>Più recenti </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> I valori scadono dopo </td> 
   <td colname="col2"> Visita - può essere ridotta ma non allungata </td> 
   <td colname="col3"> Visita </td> 
   <td colname="col4"> Visita </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limiti valore </td> 
   <td colname="col2"> Nessuno </td> 
   <td colname="col3"> Nessuno </td> 
   <td colname="col4"> Nessuno </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori speciali </td> 
   <td colname="col2"> <p>" Typed/Segnalibro": visite senza dominio di riferimento. </p> </td> 
   <td colname="col3"> <p>" Typed/Segnalibro": visite senza dominio di riferimento. </p> </td> 
   <td colname="col4"> <p>" Typed/Segnalibro": visite senza dominio di riferimento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Note {#section_B83A3571D64E4E7792712FAF740D7955}

* Il referente, il tipo di referente e il dominio di provenienza vengono impostati sul primo hit della visita o durante una visita quando il referente è esterno (ad esempio, se un visitatore lascia il sito, utilizza un motore di ricerca e quindi ritorna al sito prima della scadenza della prima visita). Questi valori vengono impostati allo stesso tempo e persistono per tutta la visita.
* L’elemento di riga Typed/bookmarked non include altri tipi di referente, ad esempio nessun Javascript o all’interno del sito. Pertanto, gli elementi della riga non corrisponderanno al totale a causa di queste omissioni.
* Prima di luglio 2012, il traffico mobile non veniva visualizzato in questo rapporto.

