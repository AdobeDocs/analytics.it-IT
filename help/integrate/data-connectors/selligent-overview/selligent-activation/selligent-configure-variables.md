---
description: Questa integrazione richiede 2 evar per l'implementazione di ogni suite di rapporti.
seo-description: Questa integrazione richiede 2 evar per l'implementazione di ogni suite di rapporti.
seo-title: Configurare le variabili di Analytics per Selligent
solution: Analytics
title: Configurare le variabili di Analytics per Selligent
uuid: 3 b 7 b 8 b 4 b -7614-4439-bcb 0-dbdec 5304844
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configure Analytics Variables for Selligent{#configure-analytics-variables-for-selligent}

Questa integrazione richiede 2 evar per l'implementazione di ogni suite di rapporti.

Oltre a tali evar, alcuni eventi possono essere riservati in base ai dati di Selligent, che si desidera visualizzare in Analytics. Queste evar ed eventi sono descritti come segue:

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di variabile </th> 
   <th colname="col2" class="entry"> Nome della variabile </th> 
   <th colname="col3" class="entry"> Modalità di utilizzo </th> 
   <th colname="col4" class="entry"> Impostazioni </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID messaggio </td> 
   <td colname="col3"> Per acquisire la singola identificazione della campagna dei messaggi e-mail. </td> 
   <td colname="col4"> <p><b>Stato</b>: Attivato </p> <p><b>Allocazione</b>: Più recente </p> <p><b>Scade dopo</b>: «Business Decision» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV </td> 
   <td colname="col2"> ID destinatario </td> 
   <td colname="col3"> Per acquisire l'identificativo anonimo del cliente che ha fatto clic sulla campagna e-mail. </td> 
   <td colname="col4"> <p><b>Stato</b>: Attivato </p> <p><b>Allocazione</b>: Più recente </p> <p><b>Scade dopo</b>: «Business Decision» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Inviato </td> 
   <td colname="col3"> Per memorizzare il numero di e-mail inviate da Selligent. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Attivato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Consegnato </td> 
   <td colname="col3"> Per memorizzare il numero di e-mail che sono state distribuite. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Attivato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Visualizzazioni </td> 
   <td colname="col3"> Per memorizzare il numero di e-mail uniche visualizzate. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Attivato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Clic </td> 
   <td colname="col3"> Per memorizzare il numero di volte in cui è stato fatto clic su un messaggio e-mail. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Attivato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Bounced </td> 
   <td colname="col3"> Per memorizzare il numero di messaggi e-mail che sono stati rimbalzati. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Attivato </p> </td> 
  </tr> 
 </tbody> 
</table>

