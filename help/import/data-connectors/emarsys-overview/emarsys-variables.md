---
description: L'integrazione dei Connettori dati per emarsys utilizza le variabili Analytics per tenere traccia delle varie metriche emarsys.
seo-description: L'integrazione dei Connettori dati per emarsys utilizza le variabili Analytics per tenere traccia delle varie metriche emarsys.
seo-title: Variabili Analytics
title: Variabili Analytics
uuid: 4 d 5 e 087 c-f 495-4 aab -9 ad 1-9 b 901 d 34 a 254
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Variabili Analytics{#analytics-variables}

L'integrazione dei Connettori dati per emarsys utilizza le variabili Analytics per tenere traccia delle varie metriche emarsys.

Dopo aver identificato l'evento e le evar da usare con l'integrazione emarsys, attivali in [Admin Console](https://microsite.omniture.com/t2/help/en_US/reference/index.html?f=conversion_var_admin).

**Variabili richieste**

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di variabile </th> 
   <th colname="col2" class="entry"> Nome </th> 
   <th colname="col3" class="entry"> Metodo di compilazione </th> 
   <th colname="col4" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> event (numerico) </td> 
   <td colname="col2"> Totale bounce </td> 
   <td colname="col3"> <p>Importazione automatica da emarsys </p> </td> 
   <td colname="col4"> <p>L'evento Bounce totale permette di visualizzare il numero di messaggi e-mail che non sono stati consegnati ai destinatari a causa di un problema di consegna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numerico) </td> 
   <td colname="col2"> Clic </td> 
   <td colname="col3"> <p>Importazione automatica da emarsys </p> </td> 
   <td colname="col4"> <p>L'evento Clic permette di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numerico) </td> 
   <td colname="col2"> Aperto </td> 
   <td colname="col3"> <p>Importazione automatica da emarsys </p> </td> 
   <td colname="col4"> <p>L'evento Aperto permette di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numerico) </td> 
   <td colname="col2"> Inviato </td> 
   <td colname="col3"> <p>Importazione automatica da emarsys </p> </td> 
   <td colname="col4"> <p>L'evento Sends permette di visualizzare il numero di messaggi e-mail inviati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numerico) </td> 
   <td colname="col2"> Annullato </td> 
   <td colname="col3"> <p>Importazione automatica da emarsys </p> </td> 
   <td colname="col4"> <p>L'evento Non iscritto consente di visualizzare il numero di visitatori che hanno aperto l'e-mail, quindi hanno fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri dall'organizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID destinatario </td> 
   <td colname="col3"> <p>Raccolti dai parametri di query nei collegamenti e-mail tramite il metodo di raccolta automatizzato o un plug-in javascript. </p> </td> 
   <td colname="col4"> ID destinatario </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evar o s. campaign </td> 
   <td colname="col2"> ID messaggio </td> 
   <td colname="col3"> <p>Raccolti dai parametri di query nei collegamenti e-mail tramite il metodo di raccolta automatizzato o un plug-in javascript. </p> </td> 
   <td colname="col4"> Questo valore viene spesso memorizzato nella variabile della campagna. </td> 
  </tr> 
 </tbody> 
</table>

