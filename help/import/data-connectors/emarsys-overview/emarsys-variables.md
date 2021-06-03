---
description: L’integrazione dei Data Connectors per emarsys utilizza le variabili di Analytics per tenere traccia di varie metriche di emarsys.
title: Variabili di Analytics
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
exl-id: a59216f2-047b-429b-8714-a2bdaa271911
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 6%

---

# Variabili di Analytics{#analytics-variables}

L’integrazione dei Data Connectors per emarsys utilizza le variabili di Analytics per tenere traccia di varie metriche di emarsys.

Dopo aver identificato l&#39;evento e le eVar da utilizzare con l&#39;integrazione emarsys, abilitali nell&#39; [Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/c-admin-tools.html).

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
   <td colname="col1"> evento (numerico) </td> 
   <td colname="col2"> Rimbalzi totali </td> 
   <td colname="col3"> <p>Importa automaticamente da emarsys </p> </td> 
   <td colname="col4"> <p>L’evento Rimbalzi totali ti consente di visualizzare il numero di messaggi e-mail che non sono stati recapitati ai destinatari a causa di un problema di consegna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> evento (numerico) </td> 
   <td colname="col2"> Clic </td> 
   <td colname="col3"> <p>Importa automaticamente da emarsys </p> </td> 
   <td colname="col4"> <p>L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> evento (numerico) </td> 
   <td colname="col2"> Aperto </td> 
   <td colname="col3"> <p>Importa automaticamente da emarsys </p> </td> 
   <td colname="col4"> <p>L’evento Open (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> evento (numerico) </td> 
   <td colname="col2"> Inviate </td> 
   <td colname="col3"> <p>Importa automaticamente da emarsys </p> </td> 
   <td colname="col4"> <p>L’evento Invio ti consente di visualizzare il numero di messaggi e-mail inviati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> evento (numerico) </td> 
   <td colname="col2"> Annulla sottoscrizione </td> 
   <td colname="col3"> <p>Importa automaticamente da emarsys </p> </td> 
   <td colname="col4"> <p>L’evento Annulla sottoscrizione ti consente di visualizzare il numero di visitatori che hanno aperto l’e-mail e poi hanno fatto clic sul collegamento Annulla sottoscrizione per rinunciare ai messaggi e-mail futuri della tua organizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>Raccolti da parametri di query in collegamenti e-mail tramite il metodo di raccolta automatizzata o un plug-in JavaScript. </p> </td> 
   <td colname="col4"> ID destinatario </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar o s.campaign </td> 
   <td colname="col2"> ID messaggio </td> 
   <td colname="col3"> <p>Raccolti da parametri di query in collegamenti e-mail tramite il metodo di raccolta automatizzata o un plug-in JavaScript. </p> </td> 
   <td colname="col4"> Questo valore viene spesso memorizzato nella variabile della campagna. </td> 
  </tr> 
 </tbody> 
</table>
