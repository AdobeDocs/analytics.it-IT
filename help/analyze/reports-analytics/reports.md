---
title: Rapporti
description: Dimensioni e metriche utilizzate da Reporting e  Analytics per ciascun report.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 0%

---


# Rapporti

Ogni report in Reporting e  Analytics utilizza una dimensione dedicata e una metrica predefinita. Puoi modificare la metrica in ciascun rapporto e aggiungere suddivisioni, se necessario. Gli elenchi seguenti indicano la dimensione utilizzata in ciascun rapporto.

>[!NOTE]
>
>Il menu dei rapporti può essere diverso a seconda delle personalizzazioni effettuate da un amministratore nell&#39;organizzazione. Consultate Personalizzazione del [menu](/help/admin/admin/customize-menus.md) nella guida utente di amministrazione.

## Metriche del sito

Contiene rapporti che in genere tendono utilizzando un intervallo di date. Contiene anche rapporti univoci, come i rapporti consigliati e i rapporti in tempo reale.

* Report consigliati: Crea una dashboard che contiene diversi minirapporti per approfondimenti immediati.
* Metriche chiave: Report che consente di visualizzare fino a cinque metriche alla volta. Tendenze Visualizzazioni [di](/help/components/metrics/page-views.md)pagina, [Visite](/help/components/metrics/visits.md)e visitatori [](/help/components/metrics/unique-visitors.md) univoci per impostazione predefinita.
* Visualizzazioni pagina: Tendenza della metrica Visualizzazioni [di](/help/components/metrics/page-views.md) pagina nel tempo.
* Visite: Tendenza della metrica [Visite](/help/components/metrics/visits.md) nel tempo.
* Visitatori: Tendenza di varie metriche [dei visitatori](/help/components/metrics/unique-visitors.md) univoci nel tempo.
   * Visitatori univoci: Conteggia i visitatori solo una volta per l’intero intervallo di date selezionato.
   * Visitatori unici orari: Conteggia più volte i visitatori che visitano in diverse ore dell’intervallo di date selezionato.
   * Visitatori univoci giornalieri: Conteggia più volte i visitatori che visitano durante diversi giorni dell’intervallo di date selezionato.
   * Visitatori unici settimanali: Conteggia più volte i visitatori che visitano durante diverse settimane dell’intervallo di date selezionato.
   * Visitatori unici mensili: Conteggia più volte i visitatori che visitano durante diversi mesi dell’intervallo di date selezionato.
   * Visitatori unici trimestrali: Conteggia più volte i visitatori che si recano in diversi trimestri dell’intervallo di date selezionato. I trimestri sono gennaio-marzo, aprile-giugno, luglio-settembre e ottobre-dicembre.
   * Visitatori univoci annuali: Conteggia più volte i visitatori che visitano durante diversi anni di calendario dell’intervallo di date selezionato.
* Tempo trascorso per visita: Utilizza il [tempo trascorso per visita - dimensione intrecciata](/help/components/dimensions/time-spent-per-visit.md) .
* Ora precedente all’evento: Utilizza il [Tempo precedente alla dimensione dell&#39;evento](/help/components/dimensions/time-prior-to-event.md) .
* Acquisti: Contiene rapporti sulle metriche basate sugli acquisti.
   * Imbuto di conversione acquisto: Report su [Visite](/help/components/metrics/visits.md), [Carrelli](/help/components/metrics/carts.md), [Ordini](/help/components/metrics/orders.md), [Entrate](/help/components/metrics/revenue.md)e [Unità](/help/components/metrics/units.md) in un rapporto funnel. Una visualizzazione simile viene realizzata in  Analysis Workspace tramite la visualizzazione [Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Entrate: Tende la metrica [Revenue](/help/components/metrics/revenue.md) nel tempo.
   * Ordini: Tende la metrica [Ordini](/help/components/metrics/orders.md) nel tempo.
   * Unità: Tendenza delle [unità](/help/components/metrics/units.md) metriche nel tempo.
* Carrello: Contiene rapporti sulle metriche del carrello acquisti.
   * Imbuto di conversione del carrello: Report [Istanze](/help/components/metrics/instances.md), [carrelli](/help/components/metrics/carts.md), [Checkout](/help/components/metrics/checkouts.md), [ordini](/help/components/metrics/orders.md)e [ricavi](/help/components/metrics/revenue.md) in un rapporto funnel.
   * Carrelli: Tende i [carrelli](/help/components/metrics/carts.md) delle metriche nel tempo.
   * Viste carrello: Tendenza delle viste [del](/help/components/metrics/cart-views.md) carrello della metrica nel tempo.
   * Aggiunte al carrello: Tendenza delle aggiunte al [carrello nel tempo](/help/components/metrics/cart-additions.md) .
   * Rimozione carrello: Tendenza degli rimozioni del [carrello nel tempo](/help/components/metrics/cart-removals.md) .
   * Checkout: Tende i [checkout](/help/components/metrics/checkouts.md) delle metriche nel tempo.
* Eventi personalizzati: Contiene tutti i rapporti relativi agli [eventi](/help/components/metrics/custom-events.md) personalizzati specifici per l&#39;implementazione.
* Bots: Mostra i rapporti relativi ai bot.
   * Bots: Mostra i bot che frequentano di più il sito. Consultate Regole per i [bot](../../admin/admin/bot-removal/bot-rules.md) nella guida utente di amministrazione.
   * Pagine bot: Mostra le pagine più colpite dai bot.
* In tempo reale: Mostra determinate dimensioni e metriche entro pochi secondi dalla raccolta dei dati. See [Real-time reports](/help/components/c-real-time-reporting/realtime.md) for more information.

## Contenuto del sito

Contiene rapporti sulle dimensioni che in genere visualizzano il contenuto del sito. Ad alcuni di questi rapporti è possibile applicare delle classificazioni. Se si applicano le classificazioni, il rapporto diventa un menu che contiene il rapporto di origine e i rapporti di classificazione.

* Pagine: Utilizza la dimensione [Pagina](/help/components/dimensions/page.md) .
* Sezione Sito: Utilizza la dimensione della sezione [](/help/components/dimensions/site-section.md) Sito.
* Server: Utilizza la dimensione [Server](/help/components/dimensions/server.md) .
* Collegamenti: Contiene rapporti che utilizzano il tracciamento dei collegamenti.
   * Collegamenti di uscita: Utilizza la dimensione del collegamento [](/help/components/dimensions/exit-link.md) Exit.
   * Download di file: Utilizza la dimensione del collegamento [](/help/components/dimensions/download-link.md) Scarica.
   * Collegamenti personalizzati: Utilizza la dimensione del collegamento [](/help/components/dimensions/custom-link.md) personalizzato.
   * Pagine non trovate: Utilizza la dimensione [Pagine non trovata](/help/components/dimensions/pages-not-found.md) .

## Mobile

Contiene rapporti sui rapporti mobili precedenti. Questi report basano i propri dati sulla stringa agente utente. Utilizzano diverse dimensioni [](/help/components/dimensions/mobile-dimensions.md) mobili per i rispettivi rapporti.

* Dispositivi: Utilizza la dimensione del dispositivo [](/help/components/dimensions/mobile-dimensions.md) mobile.
* Tipo di dispositivo: Utilizza la dimensione del tipo [di dispositivo](/help/components/dimensions/mobile-dimensions.md) mobile.
* Produttore: Utilizza la dimensione del produttore [di](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Dimensione schermo: Utilizza la dimensione della schermata [Mobile](/help/components/dimensions/mobile-dimensions.md) .
* Altezza schermo: Utilizza la dimensione dell&#39;altezza [della schermata](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Larghezza schermo: Utilizza la dimensione della larghezza [dello schermo](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Supporto dei cookie: Utilizza la dimensione del supporto [dei cookie](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Supporto per immagini: Utilizza la dimensione di supporto [delle immagini](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Profondità colore: Utilizza la dimensione della profondità [colore](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Supporto audio: Utilizza la dimensione del supporto [audio](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Supporto video: Utilizza la dimensione del supporto [video](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Sistema operativo (obsoleto): Utilizza la dimensione del sistema operativo [Mobile (obsoleto)](/help/components/dimensions/mobile-dimensions.md) .

## Paths (Percorsi)

Contiene rapporti che consentono di visualizzare i dati del percorso per i visitatori.

* Flusso pagina successivo: Utilizza un rapporto sul valore della dimensione della pagina superiore. Le viste percorso sono simili alle [istanze](/help/components/metrics/instances.md). È possibile modificare il valore della dimensione segnalata. Un rapporto simile in  Analysis Workspace è disponibile tramite una visualizzazione [](../analysis-workspace/visualizations/c-flow/flow.md)Flusso.
* Pagina successiva: Prende il valore della dimensione della pagina superiore e mostra le pagine successive alle quali i visitatori sono andati.
* Flusso pagina precedente: Utilizza un rapporto sul valore della dimensione della pagina superiore Un rapporto simile in  Analysis Workspace è disponibile tramite una visualizzazione [](../analysis-workspace/visualizations/c-flow/flow.md)Flusso.
* Pagina precedente: Prende il valore della dimensione della pagina superiore e mostra le pagine di provenienza dei visitatori precedenti.
* Abbandono: Consente di selezionare i valori delle dimensioni di pagina in passaggi, e mostra la proporzione di persone che hanno seguito e non hanno seguito quel percorso. Un rapporto simile in  Analysis Workspace è disponibile tramite una visualizzazione [Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Percorsi completi: Mostra singoli percorsi come valori di dimensione. Ritirato in  Analysis Workspace; utilizzate invece la visualizzazione [](../analysis-workspace/visualizations/c-flow/flow.md) Flusso.
* PathFinder: Fornisce diversi tipi di rapporti che consentono di analizzare i percorsi (ritirati in  Analysis Workspace).
* Lunghezza percorso: Utilizza la dimensione di profondità [della](/help/components/dimensions/visit-depth.md) visita.
* Analisi pagina
   * Riepilogo pagina: Prende il valore della dimensione della pagina superiore e mostra una vista con tendenze. Mostra anche punti di entrata, pagine precedenti, punti di uscita e pagine successive per il valore della dimensione della pagina superiore.
   * Ricarica: Utilizza la dimensione [Pagina](/help/components/dimensions/page.md) con la metrica [Ricarica](/help/components/metrics/reloads.md) .
   * Tempo trascorso sulla pagina: Utilizza la dimensione [Tempo trascorso sulla pagina - Dimensione intrecciata](/help/components/dimensions/time-spent-on-page.md) .
   * Fate clic sulla pagina: Prende il valore della dimensione della pagina superiore e mostra il numero di clic necessari per passare alla pagina in una determinata visita.
* Voci ed uscite
   * Pagine di entrata: Utilizza la dimensione delle pagine [di](/help/components/dimensions/entry-dimensions.md) immissione.
   * Pagine iniziali originali: Utilizza la dimensione originale [della pagina](/help/components/dimensions/entry-dimensions.md) Entry.
   * Visite a pagina singola: Utilizza la dimensione [Pagina](/help/components/dimensions/page.md) con il segmento &quot;Visite di pagina singola&quot; fornito da Adobe.
   * Pagine di uscita: Utilizza la dimensione delle pagine [di](/help/components/dimensions/exit-dimensions.md) uscita.

>[!NOTE]
>
>In questa cartella possono essere visualizzati altri rapporti. Si tratta di altre dimensioni, ad esempio proprietà, in cui il [percorso è abilitato](../../admin/admin/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti.

## Origini di traffico

Contiene un rapporto che fornisce informazioni su dove sono arrivati i visitatori prima di arrivare al sito. Questi rapporti non funzionano correttamente a meno che non impostiate correttamente i filtri [URL](../../admin/admin/internal-url-filter-admin.md) interni nelle impostazioni della suite di rapporti.

* Cerca parole chiave - all: Utilizza la dimensione della parola chiave [](/help/components/dimensions/search-keyword.md) Search.
* Cerca parole chiave - paid: Utilizza la parola chiave [Cerca - dimensione a pagamento](/help/components/dimensions/search-keyword.md) .
* Ricerca parole chiave - naturali: Utilizza la parola chiave [Search - dimensione naturale](/help/components/dimensions/search-keyword.md)
* Motori di ricerca - tutti: Utilizza la dimensione del motore [di](/help/components/dimensions/search-engine.md) ricerca.
* Motori di ricerca - pagati: Utilizza il motore di [ricerca - dimensione a pagamento](/help/components/dimensions/search-engine.md) .
* Motori di ricerca - naturali: Utilizza il motore di [ricerca - dimensione naturale](/help/components/dimensions/search-engine.md) .
* Classificazione di tutte le pagine di ricerca: Utilizza la dimensione di classificazione [della pagina di ricerca](/help/components/dimensions/all-search-page-rank.md) All (Tutte).
* Domini di riferimento: Utilizza la dimensione del dominio [di](/help/components/dimensions/referring-domain.md) riferimento
* Domini di riferimento originali: Utilizza la dimensione dominio [di riferimento](/help/components/dimensions/original-referring-domain.md) originale
* Referenti: Utilizza la dimensione [Referente](/help/components/dimensions/referrer.md) .
* Tipi di referente: Utilizza la dimensione del tipo [](/help/components/dimensions/referrer-type.md) Referente.

## Campagne

Contiene principalmente rapporti intorno alla dimensione del codice [di](/help/components/dimensions/tracking-code.md) tracciamento.

* Imbuto di conversione della campagna: Click-through dei report, [Checkout](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md)e [Entrate](/help/components/metrics/revenue.md) in un report funnel. La metrica click-through è simile alla metrica [Istanze](/help/components/metrics/instances.md) nel contesto della dimensione del codice [di](/help/components/dimensions/tracking-code.md) tracciamento. Una visualizzazione simile viene realizzata in  Analysis Workspace tramite la visualizzazione [Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Codice di tracciamento: Utilizza la dimensione del codice [di](/help/components/dimensions/tracking-code.md) tracciamento.

## Prodotti

Contiene rapporti principalmente sulla dimensione [Prodotto](/help/components/dimensions/product.md) .

* Imbuto di conversione prodotti: Rapporti [Viste](/help/components/metrics/product-views.md)del prodotto, aggiunte [del](/help/components/metrics/cart-additions.md)carrello, [Checkout](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md), [Unità](/help/components/metrics/units.md)[](/help/components/metrics/revenue.md) e Ricaviin un rapporto funnel. Una visualizzazione simile viene realizzata in  Analysis Workspace tramite la visualizzazione [Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Prodotti: Utilizza la dimensione [Prodotti](/help/components/dimensions/product.md) .
* Cross selling: Mostra i prodotti comunemente venduti insieme (ritirati in  Analysis Workspace).
* Categorie: Utilizza la dimensione [Categoria](/help/components/dimensions/category.md) .

## Conservazione dei visitatori

Contiene rapporti sui visitatori che tornano al sito.

* Frequenza di ritorno: Utilizza la dimensione della frequenza [di](/help/components/dimensions/return-frequency.md) ritorno.
* Visite di ritorno: Tendenza della metrica [Visite](/help/components/metrics/visits.md) nel tempo con l&#39;applicazione del segmento &quot;Visite di ritorno&quot; fornito da Adobe.
* Numero visita: Utilizza la dimensione Numero [](/help/components/dimensions/visit-number.md) visita.
* Ciclo di vendita: Cartella per i rapporti relativi all&#39;acquisto.
   * Fedeltà del cliente: Utilizza la dimensione fedeltà [del](/help/components/dimensions/customer-loyalty.md) cliente.
   * Giorni prima del primo acquisto: Utilizza la dimensione [Giorni prima del primo acquisto](/help/components/dimensions/days-before-first-purchase.md) .
   * Giorni dall&#39;ultimo acquisto: Utilizza la dimensione [Giorni dall’ultimo acquisto](/help/components/dimensions/days-since-last-purchase.md) .
   * Clienti unici giornalieri: Tendenza [Visitatori](/help/components/metrics/unique-visitors.md) univoci giornalieri nel tempo con l&#39;applicazione del segmento &quot;acquirenti&quot; fornito da Adobe.
   * Clienti unici settimanali: Tendenza [settimanale dei visitatori](/help/components/metrics/unique-visitors.md) univoci con l&#39;applicazione del segmento &quot;acquirenti&quot; fornito da Adobe.
   * Clienti unici mensili: Tendenza [Mensilmente dei visitatori](/help/components/metrics/unique-visitors.md) univoci con l&#39;applicazione del segmento &quot;acquirenti&quot; fornito da Adobe.
   * Clienti unici trimestrali: Tendenza [Trimestrale dei visitatori](/help/components/metrics/unique-visitors.md) univoci con l&#39;applicazione del segmento &quot;acquirenti&quot; fornito da Adobe. I trimestri sono gennaio-marzo, aprile-giugno, luglio-settembre e ottobre-dicembre.
   * Clienti unici annuali: Tendenze Visitatori [univoci](/help/components/metrics/unique-visitors.md) annuali nel tempo con l&#39;applicazione del segmento &quot;acquirenti&quot; fornito da Adobe.

## Profilo del visitatore

Contiene rapporti sugli utenti che visitano il sito.

* Geosegmentazione: Segnalazioni su dove sono venuti gli hit globali al sito.
   * Paesi: Utilizza la dimensione [Paesi](/help/components/dimensions/countries.md) .
   * Regione: Utilizza la dimensione [Regioni](/help/components/dimensions/regions.md) .
   * Città: Utilizza la dimensione [Città](/help/components/dimensions/cities.md) .
   * Stati Uniti: Utilizza la dimensione degli stati [](/help/components/dimensions/us-states.md) USA.
   * DMA USA: Utilizza la dimensione DMA [](/help/components/dimensions/us-dma.md) USA.
* Lingue: Utilizza la dimensione [Lingua](/help/components/dimensions/language.md) .
* Fusi orari: Utilizza la dimensione del fuso orario (ritirata in  Analysis Workspace). I valori delle dimensioni sono l’offset GMT dell’hit.
* Dominio: Utilizza la dimensione [Domain](/help/components/dimensions/domain.md) .
* Dominio di primo livello: Utilizza la dimensione del dominio di primo livello (ritirata in  Analysis Workspace). Raggruppa la dimensione dei [domini](/help/components/dimensions/domain.md) in categorie di livello superiore, in genere per paese del dominio.
* Tecnologia: Cartella contenente i rapporti relativi al visitatore utilizzato per accedere al sito.
   * Browser: Utilizza la dimensione [Browser](/help/components/dimensions/browser.md) .
   * Tipo di browser: Utilizza la dimensione del tipo [di](/help/components/dimensions/browser-type.md) browser.
   * Larghezza browser: Utilizza la larghezza del [browser - dimensione intrecciata](/help/components/dimensions/browser-width.md) .
   * Altezza browser: Utilizza l&#39;altezza del [browser - dimensione intrecciata](/help/components/dimensions/browser-height.md) .
   * Sistema operativo: Utilizza la dimensione dei sistemi [](/help/components/dimensions/operating-systems.md) operativi.
   * Tipo di sistema operativo: Utilizza la dimensione dei tipi [di sistema](/help/components/dimensions/operating-system-types.md) operativo.
   * Profondità colore monitor: Utilizza la dimensione di profondità [del](/help/components/dimensions/color-depth.md) colore.
   * Risoluzione monitor: Utilizza la dimensione di risoluzione [del](/help/components/dimensions/monitor-resolution.md) monitor.
   * Java: Utilizza la dimensione [Java abilitata](/help/components/dimensions/java-enabled.md) .
   * JavaScript: Utilizza la dimensione abilitata per JavaScript (ritirata in  Analysis Workspace). I valori delle dimensioni sono &quot;Abilitato&quot;, &quot;Disattivato&quot; o &quot;Sconosciuto&quot;, a seconda che nel browser sia attivato JavaScript.
   * Versione JavaScript: utilizza la dimensione della versione JavaScript (ritirata in  Analysis Workspace). I valori delle dimensioni mostrano la versione di JavaScript utilizzata dal browser.
   * Cookie: Utilizza la dimensione [Cookie support](/help/components/dimensions/cookie-support.md) .
   * Tipi di connessione: Utilizza la dimensione del tipo [di](/help/components/dimensions/connection-type.md) connessione.
   * Portatile: Utilizza la dimensione [Mobile](/help/components/dimensions/mobile-dimensions.md) .
* Stato visitatore: Utilizza la dimensione Stato (ritirata in  Analysis Workspace). I valori delle dimensioni provengono dalla [`state`](../../implement/vars/page-vars/state.md) variabile.
* Codice postale del visitatore: Utilizza la dimensione del codice [](/help/components/dimensions/zip-code.md) ZIP.

## Conversione personalizzata

Contiene rapporti specifici per l’implementazione. I rapporti di conversione personalizzati utilizzano [eVar](/help/components/dimensions/evar.md) come dimensione.

## Traffico personalizzato

Contiene rapporti specifici per l’implementazione. I report sul traffico personalizzati utilizzano [prop](/help/components/dimensions/prop.md) come dimensione.

## Canali di marketing

Contiene rapporti che coinvolgono canali [](/help/components/c-marketing-channels/c-getting-started-mchannel.md)Marketing.

* Report panoramica canale: Un rapporto personalizzato specifico per Reporting e  Analytics. Utilizza i canali di marketing come valori di dimensione, con le metriche che utilizzano l&#39;attribuzione del primo o dell&#39;ultimo tocco.
* Primo canale touch: Utilizza la dimensione del [primo canale](/help/components/dimensions/first-touch-channel.md) touch.
* Primo dettaglio del canale touch: Utilizza la dimensione dei dettagli [del](/help/components/dimensions/first-touch-detail.md) primo canale touch.
* Ultimo canale touch: Utilizza la dimensione [Ultimo canale](/help/components/dimensions/last-touch-channel.md) di tocco.
* Ultimo dettaglio canale touch: Utilizza la dimensione [Ultimo dettaglio](/help/components/dimensions/last-touch-detail.md) canale di tocco.

## Segnalibri

Contiene i rapporti contrassegnati come segnalibri. Per ulteriori informazioni, vedere [Segnalibri](bookmarks.md) .

## Dashboard

Contiene le dashboard create dall&#39;utente. Per ulteriori informazioni, consultate [Dashboard](dashboard.md) .

## Target

Contiene le destinazioni create dall&#39;utente. Per ulteriori informazioni, consulta [Destinazioni](targets.md) .

>[!NOTE]
>
>Se non riesci a trovare il rapporto in questa pagina dell&#39;Aiuto, è possibile che l&#39;amministratore abbia rinominato o modificato le cartelle. Consultate Personalizzazione del [menu](/help/admin/admin/customize-menus.md) nella guida utente di amministrazione.
