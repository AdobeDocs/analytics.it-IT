---
description: Elenca gli identificatori di dimensione facoltativi che possono essere forniti al passaggio 4 della procedura guidata di integrazione di Adobe.
title: Demandbase - Dimensioni personalizzate
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Demandbase - Dimensioni personalizzate{#demandbase-custom-dimensions}

Elenca gli identificatori di dimensione facoltativi che possono essere forniti al passaggio 4 della procedura guidata di integrazione di Adobe.

Se non sei sicuro dell'ID API esatto per entrare nella procedura guidata, consulta il rappresentante Demandbase.

>[!IMPORTANT]
>
>È fortemente consigliato NON includere Indirizzo IP come dimensione personalizzata. Il numero estremamente elevato di valori univoci può causare problemi di prestazioni con i report. Inoltre, l'indirizzo IP è già disponibile come opzione di reporting tramite il reporting di data warehouse di Adobe.

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensione </th> 
   <th colname="col2" class="entry"> ID API </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ISP </td> 
   <td colname="col2"> isp </td> 
   <td colname="col3"> Indica se l'organizzazione identificata è classificata come ISP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alias marketing </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> Nome organizzazione pulito e/o abbreviato (massimo 32 caratteri) da utilizzare in annunci pubblicitari, messaggi o copie di marketing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tag controllo account </td> 
   <td colname="col2"> watch_list (personalizzato) </td> 
   <td colname="col3">Set illimitato di tag definiti dal client che possono essere aggiunti ai dati di risposta API dall'organizzazione. <p><b>Esempio</b>: se disponete di un tag Watch denominato Q4 Target, il campo API sarà </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> luck_1000 </td> 
   <td colname="col3"> Indica se l'organizzazione è inclusa nell'elenco Fortune 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> Indica se l'organizzazione si trova nell'elenco Forbes 2000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conteggio dipendenti </td> 
   <td colname="col2"> count_dipendente </td> 
   <td colname="col3"> Numero di persone occupate nell'organizzazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vendite annuali </td> 
   <td colname="col2"> year_sales </td> 
   <td colname="col3"> Per gli enti pubblici, le entrate annuali si basano sui record pubblici segnalati dall'azienda per il QG globale in tutte le sedi. Per le organizzazioni private, si basa sulla stima del consenso per il numero di ricavi annuali di vendita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numero di telefono </td> 
   <td colname="col2"> telefono </td> 
   <td colname="col3"> Numero di telefono dell'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo via </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> L'indirizzo della strada dell'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Città </td> 
   <td colname="col2"> city </td> 
   <td colname="col3"> La città dell'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stato </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> Stato dell'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Codice paese </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> Codice del paese a due caratteri ISO dell'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome Paese </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> Il nome del paese del valore stringa per l'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ZIP </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> Codice postale del paese/stato per l'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sito Web </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> L'URL utilizzato dall'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nastro </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> Il contrassegno azionario se l'organizzazione identificata è quotata in borsa. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Codice SIC principale </td> 
   <td colname="col2"> initial_sic </td> 
   <td colname="col3"> Codice SIC di consenso assegnato per l'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitudine </td> 
   <td colname="col2"> latitudine </td> 
   <td colname="col3"> Latitudine per la posizione dell'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitudine </td> 
   <td colname="col2"> longitudine </td> 
   <td colname="col3"> Longitudine per la posizione dell'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Traffico </td> 
   <td colname="col2"> traffico </td> 
   <td colname="col3"> La quantità di traffico del sito web, stimata a basso, medio o alto o molto alto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> Indica che la società identificata vende principalmente ad altre imprese. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> Indica che l'azienda identificata vende principalmente a consumatori o individui. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Technology Insight </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> Fino a 75 categorie di tecnologie definite dai clienti tramite categoria, fornitore e prodotti per l'utilizzo del targeting e/o la personalizzazione di annunci, messaggi o copia di marketing. </td> 
  </tr> 
 </tbody> 
</table>

