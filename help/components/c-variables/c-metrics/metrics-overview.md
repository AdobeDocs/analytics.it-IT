---
description: Elenca le metriche standard in Adobe Analytics.
seo-description: Elenca le metriche standard in Adobe Analytics.
seo-title: Riferimento rapido metriche
solution: Analytics
title: Riferimento rapido metriche
topic: Metriche
uuid: 34160c96-7cb3-4e2f-9956-9ffa9d9a359e
translation-type: tm+mt
source-git-commit: bdac23691a7de1cd308e9f1c68c74739a51244d6

---


# Riferimento rapido metriche

Elenca le metriche standard in Adobe Analytics.

>[!NOTE]
>
>Qualsiasi metrica (evento) non elencata di seguito è una metrica [](../../../components/c-variables/c-metrics/metrics-custom.md#concept_F44638FC95A44B06AEBA3A6F9D008D27) personalizzata (evento personalizzato).

>[!IMPORTANT]
>
>Analysis Workspace non si distingue più tra le metriche Traffico e Conversione. Pertanto, il tipo di metrica è pertinente solo ai pedaggi quali Reporting e analisi, Web Services 1.4 e Generatore di report.)

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
| Clickthrough | I click-through rappresentano il numero di volte in cui un codice di tracciamento per una determinata campagna è stato passato nel reporting. When a visitor clicks on an affiliate link that has been tagged with one of these tracking codes, the visitor is taken to your landing page and the tracking code is captured in  s.campaign. That data is sent into reporting and a click-through is recorded. | Conversione |
| Customer (New, Return, Loyal) | Categories of the Customer Loyalty report: New Customer: Customer with 0 purchases.  Return Customer: Customer with 1 purchase.  Loyal Customer: Customer with more than 1 purchase. | Traffico |
| Visite giornaliere di ritorno | Displays the number of visitors to your website more than once on a given day. A day is defined as the last 24-hour period. | Traffico |
| Voci | Le voci rappresentano il numero di volte in cui un dato valore viene acquisito come il primo valore di una visita. Entries can occur only once per visit. However, it is not necessarily the first hit if the variable is not defined. | Traffico |
| Uscite | Il numero di volte in cui un dato valore viene acquisito come ultimo valore di una visita. Exits can occur only once per visit. | Traffico |
| Istanze | Il numero di volte in cui un valore è stato impostato per una variabile. Le istanze vengono conteggiate per tutti i tipi di hit, ma non nel caso in cui un valore venga registrato per una variabile su una hit successiva a causa della persistenza. | Conversione |
| Visualizzazioni dispositivi mobili | The number of times a page is viewed or a dimension is set when accessed via a mobile device. Ad hoc analysis only. Instead of using the mobile views metric, we recommend applying the "Visits from Mobile Devices" segment. | Conversione |
| Nuovi engagement | New Engagement è una metrica di reporting del canale di marketing che conta i nuovi visitatori generati da un canale. This metric also counts visitors who have not been to your site in the last 30 days. Un nuovo coinvolgimento è una eVar impostata all'inizio di ogni visita (allocazione originale). I canali di primo contatto possono anche essere Nuovi coinvolgimenti, a seconda dell’impostazione di scadenza del coinvolgimento del visitatore. | Conversione |
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
| Accesso singolo | Accesso singolo è definito dal numero di visite al sito che contenevano un singolo valore Nome pagina univoco. Se un utente accede al sito e fa clic su un collegamento tracciato, attiva un evento (ad esempio una visualizzazione video) o ricarica la pagina, la visita è comunque considerata una visita a accesso singolo. As long as value for the pageName variable does not change, any number of requests can be sent and the visit is still considered a Single Access. | Traffico |
| Durata | Metriche che segnalano il tempo trascorso dai visitatori su una pagina, un sito o per visita. | Traffico |
| Totale | Total metrics report the value of all report line items for a reported period. If a filter is currently selected, the total might represent the filtered total instead of the report suite total. If no filter is selected total represents the report suite total. | The Total version of a metric follows the type of the base metric. E.g.,  would be Traffic because  is Traffic.`totalpageviews``pageviews` |
| Unique Customer | (Hourly, Daily, Weekly, Monthly, Quarterly, Yearly)  A Unique Customer is counted once for that time frame but cannot be counted again, no matter how many times the visitor returns to make a purchase. A Unique Visitor is counted once for the first visit in a specified period and not counted again until the period expires. After the period expires, the Unique Visitor is counted again. Unique Customers are always counted as Unique Visitors because they must visit the site in order to make the purchase. | Conversione |
| Visitatori unici | Shows the total number of unique visitors for the reporting period (can be configured to daily, weekly, monthly, quarterly, yearly). | Conversione |
| Unità | The total units that were ordered for the selected time period. Because you have many units purchased per order, Units is a vital metric that reveals general inventory movement. | Conversione |
| Visitatori | Il numero di visitatori unici del sito per un'ora, un giorno, una settimana, un mese, un trimestre o un anno selezionati. | Conversione |
| Visite | Una sequenza di pagine visualizzate in una sessione. La metrica visite viene comunemente utilizzata nei rapporti che presentano il numero di sessioni utente nel corso del periodo di tempo selezionato.  The visit metric is always associated with a time period, so you know whether to count a new visit if the same visitor returns to your site. | Conversione |

