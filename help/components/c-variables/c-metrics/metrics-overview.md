---
description: Elenca le metriche standard in Adobe Analytics.
seo-description: Elenca le metriche standard in Adobe Analytics.
seo-title: Riferimento rapido metriche
solution: Analytics
title: Riferimento rapido metriche
topic: Metriche
uuid: 34160c96-7cb3-4e2f-9956-9ffa9d9a359e
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Riferimento rapido metriche

Elenca le metriche standard in Adobe Analytics.

>[!NOTE]
>
>Qualsiasi metrica (evento) non elencata di seguito è una metrica [](/help/components/c-variables/c-metrics/metrics-custom.md) personalizzata (evento personalizzato).

>[!IMPORTANT]
>
>Analysis Workspace non si distingue più tra le metriche Traffico e Conversione. Pertanto, il tipo di metrica è pertinente solo a strumenti come Reporting e analisi, Web Services 1.4 e Generatore di report.)

| Nome della metrica | Descrizione | Tipo |
|--- |--- |---|
| Profondità media della pagina | Visualizza in media la distanza all’interno di una visita in cui è stato attivato ogni valore. Questa metrica è utile per determinare fino a che punto all’interno di una visita il pubblico raggiunge una determinata pagina o un determinato valore di proprietà. Profondità pagina media è disponibile su qualsiasi variabile con percorso abilitato. | Traffico |
| Tempo medio trascorso sulla pagina | Rappresenta il tempo medio trascorso su una pagina all’interno di una visita. | Traffico |
| Tempo medio trascorso sul sito | Rappresenta il tempo medio trascorso su un sito all’interno di una visita. | Traffico |
| Percentuale non recapitate | Mostra la percentuale di visite che contengono un singolo hit. Il tasso di rimbalzo utilizza la metrica Blocchi ed è calcolato come segue: Sfondi divisi per Voci. | Conversione |
| Bounce | Una visita che consiste in una singola chiamata server. Ad esempio, una visita a una sola pagina viene considerata bounce se un visitatore non interagisce con la pagina in modo da inviare dati ad Adobe, come ad esempio fare clic su un collegamento o avviare un video. Se durante una visita viene ricevuto più di un hit, non viene conteggiato un bounce. | Conversione |
| Click-through delle campagne | I click-through rappresentano il numero di volte in cui un codice di tracciamento per una determinata campagna è stato passato nel reporting. Quando un visitatore fa clic su un collegamento affiliato a cui è stato assegnato un tag con uno di questi codici di tracciamento, viene portato alla pagina di destinazione e il codice di tracciamento viene acquisito in s.campaign. Tali dati vengono inviati nel reporting e viene registrato un click-through. | Conversione |
| Aggiunte carrello | Il numero di volte in cui un articolo è stato aggiunto a un carrello. Questo valore deriva dall'evento scAdd. | Conversione |
| Apri carrello | Il numero di volte in cui un cliente ha aperto un carrello aggiungendo il primo articolo. Si verifica la prima volta che un elemento viene aggiunto al carrello. Questo valore deriva dall'evento scOpen. | Conversione |
| Rimozioni carrello | Il numero di volte in cui un articolo è stato rimosso da un carrello. Questo valore deriva dall'evento scRemove. | Conversione |
| Carrelli | Il numero di volte in cui un nuovo carrello è stato aperto o inizializzato. | Conversione |
| Visualizzazioni carrello | Il numero di volte in cui il contenuto del carrello viene visualizzato dal cliente. | Conversione |
| Pagamenti | Un evento che si verifica quando i clienti arrivano alla fase di estrazione di un acquisto. La fase di checkout si verifica solitamente prima della finalizzazione di un acquisto e in genere comporta l'immissione di informazioni personali da parte del cliente (come le informazioni di spedizione e fatturazione). Potete controllare gli eventi sul sito che possono essere considerati come pagamenti. Questo valore deriva dall'evento scCheckout. | Conversione |
| Clickthrough | I click-through rappresentano il numero di volte in cui un codice di tracciamento per una determinata campagna è stato passato nel reporting. Quando un visitatore fa clic su un collegamento affiliato a cui è stato assegnato un tag con uno di questi codici di tracciamento, viene portato alla pagina di destinazione e il codice di tracciamento viene acquisito in s.campaign. Tali dati vengono inviati nel reporting e viene registrato un click-through. | Conversione |
| Cliente (Nuovo, Ritorno, Fedele) | Categorie del rapporto Fedeltà cliente: Nuovo cliente: Cliente con 0 acquisti.  Restituisci cliente: Cliente con 1 acquisto.  Cliente fedele: Cliente con più di 1 acquisto. | Traffico |
| Visite giornaliere di ritorno | Visualizza il numero di visitatori del sito Web più di una volta al giorno specificato. Un giorno è definito come l’ultimo periodo di 24 ore. | Traffico |
| Voci | Le voci rappresentano il numero di volte in cui un dato valore viene acquisito come il primo valore di una visita. Le voci possono verificarsi solo una volta per visita. Tuttavia, non è necessariamente il primo hit se la variabile non è definita. | Traffico |
| Uscite | Il numero di volte in cui un dato valore viene acquisito come ultimo valore di una visita. Le uscite possono verificarsi solo una volta per visita. | Traffico |
| Istanze | Il numero di volte in cui un valore è stato impostato per una variabile. Le istanze vengono conteggiate per tutti i tipi di hit, ma non nel caso in cui un valore venga registrato per una variabile su una hit successiva a causa della persistenza. | Conversione |
| Visualizzazioni dispositivi mobili | Il numero di volte che una pagina viene visualizzata o una dimensione viene impostata quando l'accesso viene effettuato tramite un dispositivo mobile. Solo analisi ad hoc. Invece di utilizzare la metrica delle viste mobili, consigliamo di applicare il segmento "Visite da dispositivi mobili". | Conversione |
| Nuovi engagement | New Engagement è una metrica di reporting del canale di marketing che conta i nuovi visitatori generati da un canale. Questa metrica include anche i visitatori che non sono stati sul sito negli ultimi 30 giorni. Un nuovo coinvolgimento è una eVar impostata all'inizio di ogni visita (allocazione originale). I canali di primo contatto possono anche essere Nuovi coinvolgimenti, a seconda dell’impostazione di scadenza del coinvolgimento del visitatore. | Conversione |
| Occorrenze | Il numero di volte in cui un valore specifico viene acquisito, più il numero di visualizzazioni di pagina per cui il valore specificato è persistente. In altre parole, le occorrenze sono la somma delle visualizzazioni di pagina e degli eventi di pagina. Le occorrenze sono disponibili solo nelle analisi ad hoc. | Non disponibile in Reporting e analisi, Web Services 1.4 o Generatore di report |
| Ordini | Il numero di ordini effettuati sul tuo sito Web nel corso del periodo di tempo selezionato. Potete suddividere singoli periodi di tempo in base ad altre metriche per mostrare gli elementi (come prodotti o campagne) che hanno contribuito al maggior numero di ordini durante tale intervallo di tempo. | Conversione |
| Profondità pagina | Numero medio di clic che gli utenti devono passare a una determinata pagina del sito Web. | Traffico |
| Eventi pagina | Gli eventi pagina sono costituiti dai dati delle richieste di immagini provenienti da richieste di immagini non standard. Le origini delle richieste di immagini non standard sono collegamenti per il download, collegamenti di uscita e tracciamento dei collegamenti personalizzati. | Traffico |
| Visualizzazioni pagina | Viene conteggiata una visualizzazione di pagina per ogni chiamata server inviata. Questa metrica rappresenta le istanze totali di Visualizzazioni di pagina. Le chiamate TrackLink non vengono conteggiate come visualizzazioni di pagina e non incrementano la metrica Visualizzazioni di pagina. | Conversione |
| Visualizzazioni di percorso | La metrica Visualizzazioni percorso si basa sui dati del percorso, che vengono tracciati per tutti gli utenti che accettano cookie persistenti.  Il termine Visualizzazione percorso indica il numero di volte in cui una pagina è stata visualizzata, in base ai vincoli dei percorsi visualizzati. Questa metrica indica il numero di visualizzazioni di pagina per la pagina specificata che si sono verificate nel percorso selezionato. Questa metrica è disponibile nel rapporto Percorsi. Visualizzazioni percorso mostra quante volte una particolare sequenza di pagine è stata visualizzata. | Traffico |
| Visualizzazioni prodotto | Istanza della visualizzazione prodotto impostata. Si verifica quando viene visualizzata la pagina dei dettagli del prodotto. Questo valore deriva dall'evento prodView. | Conversione |
| Ricariche | Contata quando lo stesso nome pagina viene caricato due volte in una riga. In genere indica che la pagina è stata aggiornata. Tenere presente che la visita della stessa pagina due volte nella stessa visita non viene conteggiata come un ricarico a meno che entrambe le visite non si siano verificate in una sola riga. | Traffico |
| Visite di ritorno | Mostra il numero di visite in cui il numero di visita è maggiore di 1. Le visite di ritorno includono i visitatori non cookie. | Conversione |
| Ricavi | Le entrate vengono acquisite nel momento in cui si verifica un evento acquisto. Vengono definite come l’importo complessivo in dollari per la somma degli ordini di ogni prodotto. Questo valore deriva dall’evento acquisto. | Conversione |
| Ricerche | Le ricerche non sono una metrica predefinita, ma sempre una metrica personalizzata.  È la metrica predefinita consigliata per motori di ricerca e parole chiave. Questa metrica rappresenta le istanze di un click-through e mostra la pagina associata a un motore o a una parola chiave specifici. I dati delle metriche delle ricerche possono essere segnalati retroattivamente all'inizio del set di dati. | Conversione |
| Accesso singolo | Accesso singolo è definito dal numero di visite al sito che contenevano un singolo valore Nome pagina univoco. Se un utente accede al sito e fa clic su un collegamento tracciato, attiva un evento (ad esempio una visualizzazione video) o ricarica la pagina, la visita è comunque considerata una visita a accesso singolo. Fintanto che il valore della variabile pageName non cambia, è possibile inviare un numero qualsiasi di richieste e la visita viene comunque considerata un accesso singolo. | Traffico |
| Durata | Metriche che segnalano il tempo trascorso dai visitatori su una pagina, un sito o per visita. | Traffico |
| Totale | Le metriche totali riportano il valore di tutte le voci del rapporto per un periodo indicato. Se un filtro è attualmente selezionato, il totale potrebbe rappresentare il totale filtrato anziché il totale della suite di rapporti. Se non viene selezionato alcun filtro, il totale della suite di rapporti è rappresentato. | La versione totale di una metrica segue il tipo di metrica di base. Ad esempio, `totalpageviews` sarebbe Traffico perché `pageviews` è Traffico. |
| Cliente unico | (Orario, Giornaliero, Settimanale, Mensile, Trimestrale, Annuale) Un cliente univoco viene conteggiato una volta per tale intervallo di tempo, ma non può essere conteggiato di nuovo, indipendentemente dal numero di volte in cui il visitatore ritorna per effettuare un acquisto. Un Visitatore univoco viene conteggiato una volta per la prima visita in un periodo specificato e non viene nuovamente conteggiato fino alla scadenza del periodo. Dopo la scadenza del periodo, viene conteggiato di nuovo il Visitatore univoco. I clienti univoci vengono sempre contati come Visitatori univoci perché devono visitare il sito per effettuare l'acquisto. | Conversione |
| Visitatori unici | Mostra il numero totale di visitatori univoci per il periodo di reporting (può essere configurato su base giornaliera, settimanale, mensile, trimestrale, annuale). | Conversione |
| Unità | Unità totali ordinate per il periodo di tempo selezionato. Poiché sono state acquistate molte unità per ordine, le unità sono una metrica vitale che rivela il movimento generale delle scorte. | Conversione |
| Visitatori | Il numero di visitatori unici del sito per un'ora, un giorno, una settimana, un mese, un trimestre o un anno selezionati. | Conversione |
| Visite | Una sequenza di pagine visualizzate in una sessione. La metrica visite viene comunemente utilizzata nei rapporti che presentano il numero di sessioni utente nel corso del periodo di tempo selezionato.  La metrica visite è sempre associata a un periodo di tempo, quindi sai se contare una nuova visita se lo stesso visitatore ritorna al tuo sito. | Conversione |

