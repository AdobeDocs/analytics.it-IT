---
description: Tabella di ricerca per determinare il tipo di hit in base al valore page_event.
keywords: Feed dati;pagina;evento;page_event;post_page_event
seo-description: Tabella di ricerca per determinare il tipo di hit in base al valore page_event.
seo-title: Ricerca eventi pagina
solution: Analytics
title: Ricerca eventi pagina
topic: Reports and Analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Ricerca eventi pagina

Tabella di ricerca per determinare il tipo di hit in base al valore page_event.

<table id="table_33AF375E0B41474696D7A4A92C652A5F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di hit </th> 
   <th colname="col02" class="entry"> page_event, valore </th> 
   <th colname="col2" class="entry"> post_page_event, valore </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina </td> 
   <td colname="col02"> come post </td> 
   <td colname="col2"> <p>0 per tutte le visualizzazioni di pagina ( <code> s.t() </code> chiamate) </p> <p>0 per <code> trackState </code> le chiamate dagli SDK per dispositivi mobili. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tracciamento dei collegamenti </td> 
   <td colname="col02"> <p>10 per "altro collegamento" </p> <p>10 per le chiamate <code> trackAction </code> e del ciclo di vita dagli SDK di Mobile. </p> <p>11 per "collegamento per il download" </p> <p>12 per "collegamento esterno o di uscita" </p> </td> 
   <td colname="col2"> <p>100 per "altro collegamento" </p> <p>100 per le chiamate <code> trackAction </code> e dal ciclo di vita dagli SDK di Mobile. </p> <p>101 per "collegamento per il download" </p> <p>102 per "collegamento esterno o di uscita" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Video Milestone </td> 
   <td colname="col02"> 
    <!--<p>30 - Legacy full media tracking event at the end of the video playback (no longer supported)</p>--> <p>31 - Evento inizio media </p> <p>32 - Evento solo aggiornamento multimediale (non esegue alcuna eVar o altra elaborazione variabile) </p> <p>33 - File multimediali + altro evento di aggiornamento variabile (include eVar e altre elaborazioni variabili) </p> </td> 
   <td colname="col2"> 
    <!--<p> 75 - Legacy full media tracking event at theend of the video playback (no longer supported)</p>--> <p> 76 - Evento inizio media </p> <p>77 - Evento solo aggiornamento multimediale (non esegue alcuna eVar o altra elaborazione variabile) </p> <p>78 - Media + altro evento di aggiornamento variabile (include eVar e altre elaborazioni variabili) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Video Heartbeat </p> </td> 
   <td colname="col02"> come post </td> 
   <td colname="col2"> <p> 50 = (non-Primetime) avvio flusso multimediale </p> <p> 51 = (non Primetime) chiusura flusso multimediale (completo/fine) </p> <p> 52 = (non Primetime) scorrimento flusso multimediale </p> <p> 53 = (non-Primetime) Flusso multimediale mantenuto attivo </p> <p> 54 = (non-Primetime) Media Stream Ad Start </p> <p> 55 = (non-Primetime) Annuncio flusso multimediale chiusura (completo/fine) </p> <p> 56 = (non Primetime) Media Stream Ad Scrubbing (scorrimento pubblicitario non Primetime) </p> <p> 60 = Avvio flusso multimediale Primetime </p> <p> 61 = Chiusura flusso multimediale Primetime (Completato/Fine) </p> <p> 62 = Scorrimento flusso multimediale Primetime </p> <p> 63 = Flusso multimediale Primetime Mantieni vivo </p> <p> 64 = Primetime Media Stream Ad Start </p> <p> 65 = Primetime Media Stream Ad Close (Complete/Finish) </p> <p> 66 = Scorrimento Ad Stream Media Primetime </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sondaggio </td> 
   <td colname="col02"> 40 </td> 
   <td colname="col2"> 80 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Analisi per Target </td> 
   <td colname="col02"> 70 - Indica un hit che include i dati dell'attività Target. 70 per gli hit che sono e non sono associati a una chiamata Analytics. </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

