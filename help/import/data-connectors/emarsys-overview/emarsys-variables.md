---
description: L'integrazione dei Connettori dati per emarsys utilizza le variabili di Analytics per tenere traccia di varie metriche di emarsys.
title: Variabili di Analytics
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variabili di Analytics{#analytics-variables}

L'integrazione dei Connettori dati per emarsys utilizza le variabili di Analytics per tenere traccia di varie metriche di emarsys.

Dopo aver identificato gli eventi e le eVar da utilizzare con l'integrazione emarsys, abilitali in [Admin Console](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/c-admin-tools.html).

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
   <td colname="col2"> Totale importi </td> 
   <td colname="col3"> <p>Importazione automatica da emarsys </p> </td> 
   <td colname="col4"> <p>L'evento Totale bacheche consente di visualizzare il numero di messaggi e-mail che non sono stati inviati ai destinatari a causa di un problema di consegna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numerico) </td> 
   <td colname="col2"> Clic </td> 
   <td colname="col3"> <p>Importazione automatica da emarsys </p> </td> 
   <td colname="col4"> <p>L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numerico) </td> 
   <td colname="col2"> Aperto </td> 
   <td colname="col3"> <p>Importazione automatica da emarsys </p> </td> 
   <td colname="col4"> <p>L’evento Opened (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numerico) </td> 
   <td colname="col2"> Inviato </td> 
   <td colname="col3"> <p>Importazione automatica da emarsys </p> </td> 
   <td colname="col4"> <p>L'evento Sending consente di visualizzare il numero di messaggi e-mail inviati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numerico) </td> 
   <td colname="col2"> Annulla sottoscrizione </td> 
   <td colname="col3"> <p>Importazione automatica da emarsys </p> </td> 
   <td colname="col4"> <p>L’evento Annulla sottoscrizione consente di visualizzare il numero di visitatori che hanno aperto l’e-mail e hanno quindi fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri della vostra organizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>Raccolti da parametri di query nei collegamenti e-mail tramite il metodo di raccolta automatizzata o un plug-in JavaScript. </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar o s.campaign </td> 
   <td colname="col2"> ID messaggio </td> 
   <td colname="col3"> <p>Raccolti da parametri di query nei collegamenti e-mail tramite il metodo di raccolta automatizzata o un plug-in JavaScript. </p> </td> 
   <td colname="col4"> Questo valore viene spesso memorizzato nella variabile della campagna. </td> 
  </tr> 
 </tbody> 
</table>

