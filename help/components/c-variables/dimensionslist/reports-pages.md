---
description: ' Consente di classificare le pagine del sito in base alle pagine che ricevono più traffico. Se la domanda aziendale tratta dati quantitativi per le pagine, potete utilizzare questo rapporto per rispondere a tale domanda, aggiungendo le metriche corrette.'
solution: Analytics
title: Pagine
topic: Reports
uuid: 6435e262-e734-4c15-af5b-173799d5cc43
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Pagine

 Consente di classificare le pagine del sito in base alle pagine che ricevono più traffico. Se la domanda aziendale tratta dati quantitativi per le pagine, potete utilizzare questo rapporto per rispondere a tale domanda, aggiungendo le metriche corrette.

## Assegnazione, scadenza e valori speciali {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

In Reporting e analisi, le metriche nel report Pagine utilizzano l'allocazione lineare. Ad esempio, le entrate sono suddivise tra tutte le pagine visualizzate prima di un evento di acquisto. Ciò può causare confusione per alcune metriche che potrebbero verificarsi solo su una pagina, ad esempio un'aggiunta al carrello.

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry">Rapporti &amp; <p>Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
   <th colname="col5" class="entry"> Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Allocazione metrica </td> 
   <td colname="col2"> Lineare </td> 
   <td colname="col3"> L'allocazione è specifica per ogni dimensione. Il valore predefinito è Allocazione Last Touch, ma la dimensione 'nome pagina' è un'eccezione. Se si applica un evento personalizzato a 'nomepagina', sarà l'allocazione Exact Hit. </td> 
   <td colname="col4"> <p>Valori impostati nella stessa visualizzazione pagina </p> </td> 
   <td colname="col5"> <p>Valori impostati nella stessa visualizzazione pagina </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> I valori scadono dopo </td> 
   <td colname="col2"> Visualizzazione pagina </td> 
   <td colname="col3"> Visualizzazione pagina </td> 
   <td colname="col4"> Visualizzazione pagina </td> 
   <td colname="col5"> Visualizzazione pagina </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limiti valore </td> 
   <td colname="col2"> <p>Primi 500 k univoci al mese + nuovi valori con traffico </p> </td> 
   <td colname="col3"> <p>Primi 500 k univoci al mese + nuovi valori con traffico </p> </td> 
   <td colname="col4"> Nessuno </td> 
   <td colname="col5"> <p>Primi 500 k univoci al mese + nuovi valori con traffico </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori speciali </td> 
   <td colname="col2"> <p>(traffico limitato) rappresenta valori oltre i primi 500 k che non hanno ricevuto abbastanza traffico per essere segnalati. </p> </td> 
   <td colname="col3"> <p>(traffico limitato) rappresenta valori oltre i primi 500 k che non hanno ricevuto abbastanza traffico per essere segnalati. </p> </td> 
   <td colname="col4"> none </td> 
   <td colname="col5"> <p>(traffico limitato) rappresenta valori oltre i primi 500 k che non hanno ricevuto abbastanza traffico per essere segnalati. </p> </td> 
  </tr> 
 </tbody> 
</table>

In Reporting e analisi, se si applica un evento personalizzato come metrica in un rapporto Pagine, si applica l'allocazione lineare.

Ciò significa che anche se l’evento è stato inviato con una chiamata s.tl(), otterrà l’allocazione lineare di qualsiasi chiamata s.t() precedente. Esempio:

| Nome pagina | Page_event | Eventi |
|---|---|---|
| Page1 | **s.t()** |  |
| Page1 | s.tl() | Event1 |
| Page1 | s.tl() | Event1 |
| Page1 | s.tl() | Event1 |
| Page2 | **s.t()** |  |
| Page2 | **s.t()** |  |
| Page2 | s.tl() | Event1 |

Per questo scenario, nel rapporto Pagine verrà ottenuta la seguente allocazione:

| Pagine | Pagvisi | Evento 1 |
|---|---|---|
| Pagina 1 | 1 | 1+1+1+1/3 = 3.33 |
| Pagina 2 | 2 | 2/3 = 0.67 |

Anche se l’evento viene inviato in una chiamata s.tl, la pagina visualizzata prima dell’evento inviato (chiamata s.t()) riceverà un credito parziale.

## Note {#section_47B0F4746D4847AC9E8697127063F4D0}

* Se non esiste un nome di pagina, viene utilizzato l’URL.
* Se avete un hit senza nome pagina, URL pagina o elenco eventi (nessun evento commerce), l’hit viene escluso.
* Le suddivisioni nelle pagine mostrano tutte le pagine con un valore persistente.

