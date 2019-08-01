---
description: Nella maggior parte dei casi, non sarà necessario apportare modifiche al codice di integrazione prodotto dalla procedura guidata del connettore dati.
seo-description: Nella maggior parte dei casi, non sarà necessario apportare modifiche al codice di integrazione prodotto dalla procedura guidata del connettore dati.
seo-title: Modifica del codice di integrazione
title: Modifica del codice di integrazione
uuid: 3 f 49 a 29 b-ad 38-4967-894 a-ef 7 ecf 4 d 268 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Modifying the Integration Code{#modifying-the-integration-code}

Nella maggior parte dei casi, non sarà necessario apportare modifiche al codice di integrazione prodotto dalla procedura guidata del connettore dati.

Tuttavia, se devi apportare delle modifiche, alcune delle impostazioni del codice sono descritte di seguito.

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione codice </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s. maxdelay </td> 
   <td colname="col2">Il numero massimo di millisecondi in cui la richiesta di immagini Adobe Analytics attenderà i dati Demandbase prima di passare al server di raccolta Analytics. <p>Nota: Questa impostazione si applica a tutte le integrazioni che potrebbero essere eseguite mediante il modulo Integra modulo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._key </td> 
   <td colname="col2"> La chiave API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Apiurl </td> 
   <td colname="col2"> Modello URL per l'API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ delim </td> 
   <td colname="col2"> Il delimitatore utilizzato per separare i valori dimensione Demandbase quando vengono inviati ad Adobe Analytics. Modificando questa impostazione, le regole di classificazione predefinite potrebbero non funzionare correttamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Settnt </td> 
   <td colname="col2">Se true, il codice di integrazione tenterà di utilizzare una mbox nascosta per inviare le dimensioni di Demandbase ad Adobe Target come parametri di profilo. <p>Nota: Ciò richiede che sulla pagina sia presente il codice mbox. js. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Tntvarprefix </td> 
   <td colname="col2"> Prima dell'invio ad Adobe Target, questa stringa viene preceduta da ogni nome di dimensione Demandbase. Ad esempio, se questa impostazione ha il valore «db_», la dimensione «industry» verrà inviata ad Adobe Target come «db_ industry». </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Dimensionsarray </td> 
   <td colname="col2"> Le dimensioni standard Demandbase inviate ad Adobe Analytics. Si consiglia di non modificare questa impostazione. La proprietà «max_ size» è il numero di caratteri consentiti per la dimensione prima che venga eseguito il troncamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Dimensionsarraycustom </td> 
   <td colname="col2"> Le dimensioni di Demandbase personalizzate inviate ad Adobe Analytics. La proprietà «max_ size» è il numero di caratteri consentiti per la dimensione prima che venga eseguito il troncamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Cname </td> 
   <td colname="col2"> Il nome del cookie di sessione utilizzato per mantenere lo stato per la comunicazione delle API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Contextname </td> 
   <td colname="col2"> Nome della variabile contextdata utilizzata per inviare le dimensioni standard ad Adobe Analytics. Si consiglia di non modificare questa impostazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Contextnamecustom </td> 
   <td colname="col2"> Il nome della variabile contextdata utilizzata per inviare le dimensioni personalizzate ad Adobe Analytics. Si consiglia di non modificare questa impostazione. </td> 
  </tr> 
 </tbody> 
</table>

