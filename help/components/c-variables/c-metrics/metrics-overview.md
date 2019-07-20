---
description: Elenca le metriche standard in Adobe Analytics.
seo-description: Elenca le metriche standard in Adobe Analytics.
seo-title: Riferimento rapido metriche
solution: Analytics
title: Riferimento rapido metriche
topic: Metrics (Metriche)
uuid: 34160 c 96-7 cb 3-4 e 2 f -9956-9 ffa 9 d 9 a 359 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Riferimento rapido metriche

Elenca le metriche standard in Adobe Analytics.

>[!NOTE]
>
>Any metric (event) not listed below is a [custom metric](../../../components/c-variables/c-metrics/metrics-custom.md#concept_F44638FC95A44B06AEBA3A6F9D008D27) (event).

<table id="table_CF4480B640BD4C81B4B32121FED5C96A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome della metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Profondità pagina media </td> 
   <td colname="col2"> Mostra in media quanto tempo all'interno di una visita ogni valore è stato attivato. Questa metrica è preziosa per determinare quanto all'interno di una visita il pubblico raggiunge un determinato valore di pagina o prop. Profondità pagina media è disponibile su qualsiasi variabile con percorsi abilitati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo medio trascorso sulla pagina </td> 
   <td colname="col2"> Rappresenta il tempo medio trascorso su una pagina all'interno di una visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo medio trascorso sul sito </td> 
   <td colname="col2"> Rappresenta il tempo medio trascorso su un sito all'interno di una visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Percentuale non recapitate </td> 
   <td colname="col2"> Mostra la percentuale di visite che contengono un hit unico. Bounce rate utilizza la metrica Bounce e viene calcolata come: Rimbalzi suddivisi per Voci. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Non recapitate </td> 
   <td colname="col2"> Una visita che consiste in una singola chiamata server. Ad esempio, una visita a una sola pagina viene considerata bounce se un visitatore non interagisce con la pagina in modo da inviare dati ad Adobe, come ad esempio fare clic su un collegamento o avviare un video. Se durante una visita viene ricevuto più di un hit, non viene conteggiato un bounce. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Click-through campagna </td> 
   <td colname="col2"> I click-through rappresentano il numero di volte in cui un codice di tracciamento di una determinata campagna è stato trasmesso al reporting. Quando un visitatore fa clic su un collegamento affiliato dotato di uno di questi codici di tracciamento, il visitatore viene portato alla pagina di destinazione e il codice di tracciamento viene acquisito in s. campaign. Tali dati vengono inviati al reporting e viene registrato un click-through. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aggiunte carrello </td> 
   <td colname="col2"> Numero di volte in cui un elemento è stato aggiunto a un carrello. Questo valore deriva dall'evento neard. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Apri carrello </td> 
   <td colname="col2"> Il numero di volte in cui un cliente ha aperto un carrello aggiungendo il primo elemento. Si verifica la prima volta che un elemento viene aggiunto al carrello. Questo valore deriva dall'evento scoen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rimozioni carrello </td> 
   <td colname="col2"> Il numero di volte in cui un elemento è stato rimosso da un carrello. Questo valore deriva dall'evento scremove. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Carrelli </td> 
   <td colname="col2"> Numero di volte in cui un nuovo carrello è stato aperto o inizializzato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni carrello </td> 
   <td colname="col2"> Il numero di volte in cui il contenuto del carrello acquisti viene visualizzato dal cliente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pagamenti </td> 
   <td colname="col2"> Un evento che si verifica quando i clienti arrivano alla fase di checkout di un acquisto. In genere si verifica l'area di visualizzazione prima che un acquisto venga finalizzato e in genere il cliente immetta informazioni personali (ad esempio le informazioni di spedizione e fatturazione). Potete controllare gli eventi sul sito che si qualificano come pagamenti. Questo valore deriva dall'evento sccheckout. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Click-through </td> 
   <td colname="col2">I click-through rappresentano il numero di volte in cui un codice di tracciamento di una determinata campagna è stato trasmesso al reporting. When a visitor clicks on an affiliate link that has been tagged with one of these tracking codes, the visitor is taken to your landing page and the tracking code is captured in <span class="varname"> s.campaign</span>. Tali dati vengono inviati al reporting e viene registrato un click-through. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cliente (Novità, Restituzione, Fedeltà) </td> 
   <td colname="col2">Categorie del report Fedeltà cliente: <p>Nuovo cliente: Cliente con 0 acquisti. </p> <p>Return Customer: Cliente con un acquisto del 1. </p> <p>Cliente fidato: Cliente con più di 1 acquisto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite giornaliere di ritorno </td> 
   <td colname="col2"> Consente di visualizzare più volte il numero di visitatori sul sito Web in un determinato giorno. Un giorno è definito come ultimo periodo di 24 ore. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingressi </td> 
   <td colname="col2"> Le voci rappresentano il numero di volte in cui un dato valore viene acquisito come il primo valore di una visita. Le voci possono avvenire solo una volta per visita. Tuttavia, non è necessariamente il primo hit se la variabile non è definita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Uscite </td> 
   <td colname="col2"> Il numero di volte in cui un dato valore viene acquisito come ultimo valore in una visita. Le uscite possono avvenire solo una volta per visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Istanze </td> 
   <td colname="col2"> Il numero di volte in cui un valore è stato impostato per una variabile. Le istanze vengono conteggiate per tutti i tipi di hit, ma non nel caso in cui un valore venga registrato per una variabile su una hit successiva a causa della persistenza. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ciclo vita </td> 
   <td colname="col2"> La quantità totale di una metrica di successo specificata per un singolo utente. Ad esempio, il numero totale di visite per un utente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni mobili </td> 
   <td colname="col2"> Il numero di volte in cui viene visualizzata una pagina o una dimensione quando accede tramite un dispositivo mobile. Analisi ad hoc. Invece di utilizzare la metrica visualizzazioni mobili, consigliamo di applicare il segmento «Visite da dispositivi mobili». </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nuove coinvolgimenti </td> 
   <td colname="col2"> La nuova Engagement è una metrica di reporting Canale marketing che conta i nuovi visitatori derivanti da un canale. Questa metrica conta anche i visitatori che non hanno visitato il tuo sito negli ultimi 30 giorni. Un nuovo coinvolgimento è una evar impostata all'inizio di ogni visita (allocazione originale). I canali first-touch possono essere anche Nuovi engagement, a seconda dell'impostazione di scadenza del visitatore. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Occorrenze </td> 
   <td colname="col2"> Il numero di volte in cui viene acquisito un valore specifico, più il numero di visualizzazioni di pagina per le quali il valore specificato viene mantenuto. In altre parole, Occorrenze è la somma delle visualizzazioni di pagina e degli eventi di pagina. Occorrenze sono disponibili solo nell'analisi ad hoc. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ordini </td> 
   <td colname="col2"> Il numero di ordini effettuati sul tuo sito Web nel corso del periodo di tempo selezionato. Potete suddividere singoli periodi di tempo in base ad altre metriche per mostrare gli elementi (quali prodotti o campagne) che hanno contribuito al maggior numero di ordini durante tale intervallo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profondità pagina </td> 
   <td colname="col2"> Il numero medio di clic richiede agli utenti di passare a una determinata pagina del sito Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eventi pagina </td> 
   <td colname="col2"> Gli eventi di pagina sono dati di richiesta di immagini provenienti da richieste di immagini non standard. Origini di richieste di immagini non standard sono collegamenti di download, collegamenti di uscita e tracciamento personalizzato dei collegamenti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina </td> 
   <td colname="col2"> Viene conteggiata una visualizzazione di pagina per ogni chiamata server inviata. Questa metrica rappresenta le istanze totali di Visualizzazioni di pagina. Le chiamate tracklink non vengono conteggiate come visualizzazioni di pagina e non incrementano la metrica Visualizzazioni pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni percorso </td> 
   <td colname="col2"> <p>La metrica Visualizzazioni percorso è basata sui dati percorsi, tracciati per tutti gli utenti che accettano cookie persistenti. </p> <p>Il termine Visualizzazione percorso viene usato per indicare quante volte è stata visualizzata una pagina, in base alle limitazioni dei percorsi visualizzati. Questa metrica indica il numero di visualizzazioni di pagina per la pagina che si è verificata all'interno del percorso selezionato. Questa metrica è disponibile nel rapporto Percorsi. Visualizzazioni percorso mostra quante volte è stata visualizzata una particolare sequenza di pagine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizzazioni prodotto </td> 
   <td colname="col2"> Istanza della visualizzazione prodotto che viene impostata. Si verifica quando viene visualizzata la pagina dei dettagli del prodotto. Questo valore deriva dall'evento prodview. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricarica </td> 
   <td colname="col2"> Conteggiato quando lo stesso nome di pagina viene caricato due volte in una riga. In genere indica che la pagina è stata aggiornata. Si noti che il visitamento due volte della stessa pagina nella stessa visita non conta come ricaricato, a meno che non sia avvenuta una sola visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite di ritorno </td> 
   <td colname="col2"> Mostra il numero di visite in cui il numero di visite è maggiore di 1. Return Visits include visitatori non cooker. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricavi </td> 
   <td colname="col2"> Le entrate vengono acquisite nel momento in cui si verifica un evento acquisto. Vengono definite come l’importo complessivo in dollari per la somma degli ordini di ogni prodotto. Questo valore deriva dall’evento acquisto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricerche </td> 
   <td colname="col2"> <p>Le ricerche non rappresentano una metrica predefinita, ma si tratta sempre di una metrica personalizzata. </p> <p>È la metrica predefinita consigliata per i motori di ricerca e le parole chiave. Questa metrica rappresenta le istanze di un click-through e mostra la pagina associata a uno specifico motore o parola chiave. I dati delle metriche di ricerca possono essere riportate retroattivamente all'inizio del set di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Accesso singolo </td> 
   <td colname="col2"> Accesso singolo è definito dal numero di visite al sito che contengono un unico valore univoco per Nome pagina. Se un utente accede al sito e fa clic su un collegamento tracciato, attiva un evento (ad esempio una visualizzazione video) o ricarica la pagina, la visita viene comunque considerata una visita Accesso singolo. Fintanto che il valore della variabile pagename non viene modificato, è possibile inviare un numero qualsiasi di richieste e la visita viene ancora considerata un accesso singolo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata </td> 
   <td colname="col2"> Metriche relative al tempo che i visitatori trascorrono su una pagina, un sito o una visita. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Totale </td> 
   <td colname="col2"> Le metriche totali riferiscono il valore di tutte le voci di report per un periodo segnalato. Se è selezionato un filtro, il totale potrebbe rappresentare il totale filtrato invece della suite di rapporti totale. Se nessun filtro è selezionato, il totale rappresenta il totale della suite di rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cliente univoco </td> 
   <td colname="col2"> <p>(Orario, giornaliero, settimanale, mensile, trimestrale, annuale) </p> <p>Un Cliente univoco viene conteggiato una volta per quell'intervallo di tempo ma non può essere conteggiato di nuovo, indipendentemente dal numero di volte in cui il visitatore ritorna per effettuare un acquisto. Un visitatore univoco viene conteggiato una volta per la prima visita in un periodo specificato e non sarà più conteggiato fino alla scadenza del periodo. Una volta scaduto il periodo, il Visitatore univoco viene conteggiato di nuovo. I clienti univoci vengono sempre conteggiati come Visitatori unici perché devono visitare il sito per effettuare l'acquisto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori univoci </td> 
   <td colname="col2"> Mostra il numero totale di visitatori unici per il periodo di reporting (può essere configurato su base giornaliera, settimanale, mensile, trimestrale, annuale). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unità </td> 
   <td colname="col2"> Le unità totali ordinate per il periodo di tempo selezionato. Poiché sono state acquistate diverse unità per ordine, Unità è una metrica fondamentale che rivela il movimento generale delle scorte. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori </td> 
   <td colname="col2"> Numero di visitatori univoci del sito per l'ora, il giorno, la settimana, il mese, il trimestre o l'anno selezionato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite </td> 
   <td colname="col2"> <p>Una sequenza di pagine visualizzate in una sessione. La metrica visite viene comunemente utilizzata nei rapporti che presentano il numero di sessioni utente nel corso del periodo di tempo selezionato. </p> <p>La metrica visita è sempre associata a un periodo di tempo, quindi sai se conteggiare una nuova visita se lo stesso visitatore ritorna al sito. </p> </td> 
  </tr> 
 </tbody> 
</table>

