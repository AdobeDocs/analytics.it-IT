---
description: Tabella di ricerca per determinare il tipo di hit basato sul valore page_ event.
keywords: Feed dati; page; evento; page_ event; post_ page_ event
seo-description: Tabella di ricerca per determinare il tipo di hit basato sul valore page_ event.
seo-title: Ricerca eventi pagina
solution: Analytics
title: Ricerca eventi pagina
topic: Reports & Analytics
uuid: 73 af 597 c -5560-466 e -94 b 2-ddd 1 d 64797 c 8
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Ricerca eventi pagina

Tabella di ricerca per determinare il tipo di hit basato sul valore page_ event.

<table id="table_33AF375E0B41474696D7A4A92C652A5F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di hit </th> 
   <th colname="col02" class="entry"> page_ event, valore </th> 
   <th colname="col2" class="entry"> post_ page_ event, valore </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Visualizzazioni di pagina </td> 
   <td colname="col02"> come post </td> 
   <td colname="col2"> <p>0 for all page views ( <code> s.t() </code> calls) </p> <p>0 for <code> trackState </code> calls from the mobile SDKs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tracciamento dei collegamenti </td> 
   <td colname="col02"> <p>10 per "altro collegamento" </p> <p>10 for <code> trackAction </code> and lifecycle calls from the Mobile SDKs. </p> <p>11 per "collegamento download" </p> <p>12 per «collegamento esterno o di uscita» </p> </td> 
   <td colname="col2"> <p>100 per "altro collegamento" </p> <p>100 for <code> trackAction </code> and lifecycle calls from the Mobile SDKs. </p> <p>101 per "collegamento download" </p> <p>102 per «collegamento esterno o di uscita» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Video milestone (Pietra miliare) </td> 
   <td colname="col02"> 
    <!--<p>30 - Legacy full media tracking event at the end of the video playback (no longer supported)</p>--> <p>31 - Evento di avvio multimediale </p> <p>32 - Evento solo aggiornamento multimediale (non esegue evar o qualsiasi altra elaborazione variabile) </p> <p>33 - Media + altro evento di aggiornamento variabile (include evar e altre elaborazioni variabili) </p> </td> 
   <td colname="col2"> 
    <!--<p> 75 - Legacy full media tracking event at theend of the video playback (no longer supported)</p>--> <p> 76 - Evento di avvio multimediale </p> <p>77 - Evento solo aggiornamento multimediale (non esegue evar o qualsiasi altra elaborazione variabile) </p> <p>78 - Media + altro evento di aggiornamento variabile (include evar e altre elaborazioni variabili) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Video Heartbeat </p> </td> 
   <td colname="col02"> come post </td> 
   <td colname="col2"> <p> 50 = (non Primetime) Media Stream Start </p> <p> 51 = (non Primetime) Media Stream Close (Completato/Completato) </p> <p> 52 = (non Primetime) Scorrimento flusso Media </p> <p> 53 = (non Primetime) Media Stream Keep Alive </p> <p> 54 = (non Primetime) Media Stream Ad Start </p> <p> 55 = (non-Primetime) Media Stream Ad Close (Complete/Finish) </p> <p> 56 = (non Primetime) Media Stream Ad Scrubbing </p> <p> 60 = Primetime Media Stream Start </p> <p> 61 = Primetime Media Stream Close (Complete/Finish) </p> <p> 62 = Strumento Primetime Media Stream Scrubbing </p> <p> 63 = Keep Metime Media Stream Keep Alive </p> <p> 64 = Primetime Media Stream Ad Start </p> <p> 65 = Primetime Media Stream Ad Close (Complete/Finish) </p> <p> 66 = Primetime Media Stream Ad Scrubbing </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sondaggio </td> 
   <td colname="col02"> 40 </td> 
   <td colname="col2"> 80 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Analytics per Target </td> 
   <td colname="col02"> 70 - Indica un hit che include i dati dell'attività Target. Questo è il 70 per gli hit che sono e non sono associati a una chiamata Analytics. </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

