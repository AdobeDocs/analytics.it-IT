---
description: Classifica le pagine sul sito in base alle pagine che ricevono più traffico. Se la tua domanda aziendale riguarda i dati quantitativi per le pagine, puoi usare questo rapporto per rispondere a tale domanda, aggiungendo le metriche corrette.
seo-description: Classifica le pagine sul sito in base alle pagine che ricevono più traffico. Se la tua domanda aziendale riguarda i dati quantitativi per le pagine, puoi usare questo rapporto per rispondere a tale domanda, aggiungendo le metriche corrette.
seo-title: Pagine
solution: Analytics
title: Pagine
topic: Rapporti
uuid: 6435 e 262-e 734-4 c 15-af 5 b -173799 d 5 cc 43
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Pagine

Classifica le pagine sul sito in base alle pagine che ricevono più traffico. Se la tua domanda aziendale riguarda i dati quantitativi per le pagine, puoi usare questo rapporto per rispondere a tale domanda, aggiungendo le metriche corrette.

## Allocation, Expiration, and Special Values {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

In Reporting e analisi, le metriche nel report Pagine usano l'allocazione lineare. Ad esempio, le entrate vengono suddivise tra tutte le pagine visualizzate prima di un evento di acquisto. Ciò potrebbe causare confusione per alcune metriche che potrebbero verificarsi solo in una pagina, ad esempio un'aggiunta al carrello.

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
   <td colname="col3"> L'allocazione è specifica per ogni dimensione. L'impostazione predefinita è l'allocazione Ultimo tocco, ma la dimensione «pagename» è un'eccezione. Se si applica un evento personalizzato a'pagenamè, si tratterà di un'allocazione Exact Hit. </td> 
   <td colname="col4"> <p>Valori impostati sulla stessa visualizzazione di pagina </p> </td> 
   <td colname="col5"> <p>Valori impostati sulla stessa visualizzazione di pagina </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori scaduti dopo </td> 
   <td colname="col2"> Visualizzazione pagina </td> 
   <td colname="col3"> Visualizzazione pagina </td> 
   <td colname="col4"> Visualizzazione pagina </td> 
   <td colname="col5"> Visualizzazione pagina </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limiti valore </td> 
   <td colname="col2"> <p>Primo 500 k univoco al mese + nuovi valori con traffico </p> </td> 
   <td colname="col3"> <p>Primo 500 k univoco al mese + nuovi valori con traffico </p> </td> 
   <td colname="col4"> Nessuno </td> 
   <td colname="col5"> <p>Primo 500 k univoco al mese + nuovi valori con traffico </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori speciali </td> 
   <td colname="col2"> <p>(basso traffico) rappresenta valori oltre i primi 500 k che non hanno ricevuto traffico sufficiente per essere segnalati. </p> </td> 
   <td colname="col3"> <p>(basso traffico) rappresenta valori oltre i primi 500 k che non hanno ricevuto traffico sufficiente per essere segnalati. </p> </td> 
   <td colname="col4"> none </td> 
   <td colname="col5"> <p>(basso traffico) rappresenta valori oltre i primi 500 k che non hanno ricevuto traffico sufficiente per essere segnalati. </p> </td> 
  </tr> 
 </tbody> 
</table>

In Reporting e analisi, se applichi un evento personalizzato come metrica nel rapporto Pagine, si applica l'allocazione lineare.

Ciò significa che anche se l'evento è stato inviato con una chiamata s. tl (), otterrete l'allocazione lineare di qualsiasi chiamata s. t () precedente. Esempio:

| Nome pagina | Page_ event | Eventi |
|---|---|---|
| Page1 | **s.t()** |  |
| Page1 | s. tl () | Event1 |
| Page1 | s. tl () | Event1 |
| Page1 | s. tl () | Event1 |
| Page2 | **s.t()** |  |
| Page2 | **s.t()** |  |
| Page2 | s. tl () | Event1 |

Per questo scenario, nel rapporto Pagine otterremo la seguente allocazione:

| Pagine | Visualizzazioni | Event 1 |
|---|---|---|
| Pagina 1 | 1 | 1+1+1+1/3 = 3.33 |
| Pagina 2 | 2 | 2/3 = 0.67 |

Anche se l'evento viene inviato in una chiamata s. tl, la pagina visualizzata prima dell'evento inviato (chiamata s.

## Note {#section_47B0F4746D4847AC9E8697127063F4D0}

* Se non esiste alcun nome di pagina, viene utilizzato l'URL.
* Se hai un hit senza nome pagina, URL pagina o elenco eventi (nessun evento di commercio), l'hit viene escluso.
* Le suddivisioni nelle pagine mostrano tutte le pagine con un valore persistente.

