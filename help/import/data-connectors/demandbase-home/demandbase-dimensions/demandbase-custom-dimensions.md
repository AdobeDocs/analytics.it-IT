---
description: Elenca gli identificatori dimensione facoltativi che possono essere forniti al passaggio 4 della procedura guidata Integrazione Adobe.
seo-description: Elenca gli identificatori dimensione facoltativi che possono essere forniti al passaggio 4 della procedura guidata Integrazione Adobe.
seo-title: Demandbase Custom Dimensions
title: Demandbase Custom Dimensions
uuid: d 1621046-3 aa 2-46 b 9-a 536-4 a 8 fb 792 b 69 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Demandbase Custom Dimensions{#demandbase-custom-dimensions}

Elenca gli identificatori dimensione facoltativi che possono essere forniti al passaggio 4 della procedura guidata Integrazione Adobe.

Se non sei sicuro dell'ID API esatto da inserire nella procedura guidata, consulta il rappresentante Demandbase.

>[!IMPORTANT]
>
>È vivamente consigliabile NON includere l'indirizzo IP come dimensione personalizzata. L'elevato numero di valori univoci può causare problemi di prestazioni con i rapporti. Inoltre, l'indirizzo IP è già offerto come opzione di reporting tramite il reporting di data warehouse Adobe.

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
   <td colname="col2"> marketing_ alias </td> 
   <td colname="col3"> Nome organizzazione pulito e/o abbreviato (massimo: 32 caratteri) da utilizzare in annunci, messaggi o copia di marketing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tag Watch Watch </td> 
   <td colname="col2"> watch_ list (personalizzato) </td> 
   <td colname="col3">Numero illimitato di tag definiti dal client che possono essere aggiunti ai dati della risposta API, ordinati dall'organizzazione. <p><b>Esempio</b>: se si dispone di un tag Watch denominato Q 4 Target, il campo API è </p> <code> watch_ list_ q 4_ target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> fortune_ 1000 </td> 
   <td colname="col3"> Indica se l'organizzazione è inclusa nell'elenco Fortune 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_ 2000 </td> 
   <td colname="col3"> Indica se l'organizzazione è inclusa nell'elenco Forbes 2000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conteggio dei dipendenti </td> 
   <td colname="col2"> employee_ count </td> 
   <td colname="col3"> Numero di persone che lavorano nell'organizzazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vendite annuali </td> 
   <td colname="col2"> annual_ sales </td> 
   <td colname="col3"> Per le entità pubbliche, le entrate annuali sono basate sui record pubblici segnalati dalla società per l'HQ globale su tutte le posizioni. Per le organizzazioni private, si basa sulla stima del consenso per il numero di fatturato annuo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numero telefonico </td> 
   <td colname="col2"> phone </td> 
   <td colname="col3"> Numero di telefono dell'organizzazione identificato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo street </td> 
   <td colname="col2"> street_ address </td> 
   <td colname="col3"> Indirizzo street dell'organizzazione identificato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Città </td> 
   <td colname="col2"> city </td> 
   <td colname="col3"> Città dell'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stato </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> Lo stato dell'organizzazione identificato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Codice paese </td> 
   <td colname="col2"> country_ code </td> 
   <td colname="col3"> Il codice paese di due caratteri ISO dell'organizzazione identificato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome paese </td> 
   <td colname="col2"> country_ name </td> 
   <td colname="col3"> Il nome del paese stringa del paese per l'organizzazione identificata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ZIP </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> Il codice zip del paese/dello stato dell'organizzazione identificato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sito Web </td> 
   <td colname="col2"> web_ site </td> 
   <td colname="col3"> L'URL utilizzato dall'organizzazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ticker di Stock </td> 
   <td colname="col2"> stock_ ticker </td> 
   <td colname="col3"> Il ticker di azione se l'organizzazione identificato è commercializzata pubblicamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Codice SIC principale </td> 
   <td colname="col2"> primary_ sic </td> 
   <td colname="col3"> Codice SIC del consenso assegnato per l'organizzazione identificato. </td> 
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
   <td colname="col1"> Traffic (Traffico) </td> 
   <td colname="col2"> traffico </td> 
   <td colname="col3"> Quantità di traffico sul sito Web stimato a bassa, media o alta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> Indica che la società identificata vende principalmente ad altre aziende. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> Indica che la società rilevata vende principalmente a consumatori o individui. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tecnologia Insight </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> Fino a 75 categorie tecnologiche definite dai clienti tramite categoria, fornitori e prodotti per l'utilizzo di targeting e/o di personalizzazione annunci, messaggi o copia di marketing. </td> 
  </tr> 
 </tbody> 
</table>

