---
description: Descrive le evar ed Eventi da riservare a ogni implementazione di suite di rapporti.
seo-description: Descrive le evar ed Eventi da riservare a ogni implementazione di suite di rapporti.
seo-title: Configurare le variabili di Adobe Analytics per Lyris
solution: Analytics
title: Configurare le variabili di Adobe Analytics per Lyris
uuid: 12 e 150 c 4-052 a -481 c -8 c 27-ef 45 ee 801977
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Configurare le variabili di Adobe Analytics per Lyris{#configure-adobe-analytics-variables-for-lyris}

Descrive le evar ed Eventi da riservare a ogni implementazione di suite di rapporti.

Questa integrazione richiede almeno 2 evar per l'implementazione di ogni suite di rapporti. Oltre a tali evar, alcuni eventi possono essere riservati a seconda dei dati Lyris che si desidera visualizzare in Analytics. Queste evar ed eventi sono descritti nella tabella seguente:

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di variabile </th> 
   <th colname="col2" class="entry"> Nome della variabile </th> 
   <th colname="col3" class="entry"> Utilizzo della variabile </th> 
   <th colname="col4" class="entry"> Impostazioni </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID messaggio </td> 
   <td colname="col3"> Per acquisire la singola identificazione della campagna dei messaggi e-mail </td> 
   <td colname="col4"> <p>Stato: Attivato </p> <p>Allocazione: Più recente </p> <p>Scade dopo: «Business Decision» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email ID destinatario </td> 
   <td colname="col3"> Per acquisire l'identificazione anonima del cliente che ha fatto clic sulla campagna e-mail </td> 
   <td colname="col4"> <p>Stato: Attivato </p> <p>Allocazione: Più recente </p> <p>Scade dopo: «Business Decision» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - E-mail inviate </td> 
   <td colname="col3"> Per memorizzare no. di e-mail inviate da Lyris </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Attivato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - E-mail aperte </td> 
   <td colname="col3"> Per memorizzare no. delle e-mail aperte </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Attivato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - E-mail uniche aperte </td> 
   <td colname="col3"> Per memorizzare no. di e-mail univoche aperte </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Attivato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Click-through-through </td> 
   <td colname="col3"> Per memorizzare no. di volte in cui è stato fatto clic su un'e-mail </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Attivato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Bounce e-mail </td> 
   <td colname="col3"> Per memorizzare il no. di e-mail che sono state scartate </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Attivato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Annulla sottoscrizione e-mail </td> 
   <td colname="col3"> Per memorizzare il no. delle sottoscrizioni e-mail disattivate </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Attivato </p> </td> 
  </tr> 
 </tbody> 
</table>

