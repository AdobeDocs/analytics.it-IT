---
title: Rapporti
description: Dimensioni e metriche utilizzate da Reports & Analytics per ogni rapporto.
feature: Nozioni di base su Reports & Analytics
role: Business Practitioner, Administrator
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
translation-type: tm+mt
source-git-commit: cddf2a76ca36914f133379959b7cbb5246bdd695
workflow-type: tm+mt
source-wordcount: '1866'
ht-degree: 0%

---

# Rapporti

Ogni rapporto in Reporting e analisi utilizza una dimensione dedicata e una metrica predefinita. Puoi modificare la metrica in ciascun rapporto e aggiungere suddivisioni, se necessario. Gli elenchi seguenti forniscono la dimensione utilizzata in ciascun rapporto.

>[!NOTE]
>
>Il menu dei rapporti può avere un aspetto diverso a seconda delle personalizzazioni effettuate da un amministratore nell’organizzazione. Consulta [Personalizzazione del menu](/help/admin/admin/customize-menus.md) nella guida utente Admin.

## Metriche del sito

Contiene rapporti che in genere presentano tendenze utilizzando un intervallo di date. Contiene anche rapporti univoci, ad esempio rapporti consigliati e rapporti in tempo reale.

* Rapporti consigliati: Crea un dashboard contenente diversi minirapporti per approfondimenti immediati.
* Metriche chiave: Report che ti consente di generare tendenze fino a cinque metriche alla volta. Tendenze [Visualizzazioni pagina](/help/components/metrics/page-views.md), [Visite](/help/components/metrics/visits.md) e [Visitatori unici](/help/components/metrics/unique-visitors.md) per impostazione predefinita.
* Visualizzazioni di pagina: Tendenza della metrica [Visualizzazioni pagina](/help/components/metrics/page-views.md) nel tempo.
* Visite: Tendenza della metrica [Visite](/help/components/metrics/visits.md) nel tempo.
* Visitatori: Tendenza di varie metriche [Visitatori unici](/help/components/metrics/unique-visitors.md) nel tempo.
   * Visitatori unici: Conta i visitatori una sola volta per l’intero intervallo di date selezionato.
   * Visitatori unici orari: Conta i visitatori più volte se visitano in diverse ore dell’intervallo di date selezionato.
   * Visitatori unici giornalieri: Conta i visitatori più volte se visitano durante giorni diversi dell’intervallo di date selezionato.
   * Visitatori unici settimanali: Conta i visitatori più volte se visitano durante diverse settimane dell’intervallo di date selezionato.
   * Visitatori unici mensili: Conta i visitatori più volte se visitano durante diversi mesi dell’intervallo di date selezionato.
   * Visitatori unici trimestrali: Conta i visitatori più volte se effettuano visite durante diversi trimestri dell’intervallo di date selezionato. I trimestri sono gennaio-marzo, aprile-giugno, luglio-settembre e ottobre-dicembre.
   * Visitatori unici annuali: Conta i visitatori più volte se visitano durante diversi anni di calendario dell’intervallo di date selezionato.
* Tempo trascorso per visita: Utilizza la dimensione [Tempo trascorso per visita - bucket](/help/components/dimensions/time-spent-per-visit.md) .
* Tempo precedente all’evento: Utilizza la dimensione [Tempo precedente alla dimensione evento](/help/components/dimensions/time-prior-to-event.md).
* Acquisti: Contiene rapporti sulle metriche basate sugli acquisti.
   * Funnel di conversione acquisto: Report su [Visite](/help/components/metrics/visits.md), [Carrelli](/help/components/metrics/carts.md), [Ordini](/help/components/metrics/orders.md), [Entrate](/help/components/metrics/revenue.md) e [Unità](/help/components/metrics/units.md) in un rapporto funnel. Una visualizzazione simile è possibile in Analysis Workspace utilizzando la visualizzazione [Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Entrate Tendenza della metrica [Entrate](/help/components/metrics/revenue.md) nel tempo.
   * Ordini: Tende la metrica [Ordini](/help/components/metrics/orders.md) nel tempo.
   * Unità: Tende la metrica [Unità](/help/components/metrics/units.md) nel tempo.
* Carrello: Contiene rapporti sulle metriche del carrello acquisti.
   * Funnel di conversione del carrello: Report [Istanze](/help/components/metrics/instances.md), [Carrelli](/help/components/metrics/carts.md), [Pagamenti](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md) e [Entrate](/help/components/metrics/revenue.md) in un rapporto funnel.
   * Carrelli: Tende la metrica [Carts](/help/components/metrics/carts.md) nel tempo.
   * Visualizzazioni carrello: Tendenza della metrica [Visualizzazioni carrello](/help/components/metrics/cart-views.md) nel tempo.
   * Aggiunte al carrello: Tende la metrica [Aggiunte al carrello](/help/components/metrics/cart-additions.md) nel tempo.
   * Rimozioni dal carrello: Tende la metrica [Rimozioni dal carrello](/help/components/metrics/cart-removals.md) nel tempo.
   * Pagamenti: Tendenza della metrica [Pagamenti](/help/components/metrics/checkouts.md) nel tempo.
* Eventi personalizzati: Contiene tutti i rapporti relativi a [Eventi](/help/components/metrics/custom-events.md) personalizzati specifici per la tua implementazione.
* Bot: Mostra rapporti relativi ai bot.
   * Bot: Mostra i bot che più frequentano il tuo sito. Consulta [Regole bot](../../admin/admin/bot-removal/bot-rules.md) nella guida utente Admin.
   * Pagine bot: Mostra le pagine più visitate dai bot.
* In tempo reale: Mostra determinate dimensioni e metriche entro pochi secondi dalla raccolta dei dati. Per ulteriori informazioni, consulta [Rapporti in tempo reale](/help/components/c-real-time-reporting/realtime.md) .

## Contenuto del sito

Contiene rapporti sulle dimensioni che in genere visualizzano il contenuto del sito. Puoi applicare le classificazioni ad alcuni di questi rapporti. Se si applicano le classificazioni, un rapporto diventa un menu contenente il rapporto di origine e i rapporti di classificazione.

* Pagine: Utilizza la dimensione [Pagina](/help/components/dimensions/page.md).
* Sezione del sito: Utilizza la dimensione [Sezione sito](/help/components/dimensions/site-section.md) .
* Server: Utilizza la dimensione [Server](/help/components/dimensions/server.md).
* Collegamenti: Contiene rapporti che utilizzano il tracciamento dei collegamenti.
   * Collegamenti di uscita: Utilizza la dimensione [Collegamento di uscita](/help/components/dimensions/exit-link.md).
   * Download dei file: Utilizza la dimensione [Download link](/help/components/dimensions/download-link.md) .
   * Collegamenti personalizzati: Utilizza la dimensione [Collegamento personalizzato](/help/components/dimensions/custom-link.md).
   * Pagine non trovate: Utilizza la dimensione [Pagine non trovate](/help/components/dimensions/pages-not-found.md).

## Mobile

Contiene rapporti sui rapporti mobili legacy. Questi report basano i loro dati sulla stringa dell&#39;agente utente. Utilizzano varie [dimensioni mobili](/help/components/dimensions/mobile-dimensions.md) per i rispettivi rapporti.

* Dispositivi: Utilizza la dimensione [Dispositivo mobile](/help/components/dimensions/mobile-dimensions.md).
* Tipo di dispositivo: Utilizza la dimensione [Tipo di dispositivo mobile](/help/components/dimensions/mobile-dimensions.md) .
* Produttore: Utilizza la dimensione [produttore mobile](/help/components/dimensions/mobile-dimensions.md) .
* Dimensioni dello schermo: Utilizza la dimensione [Dimensioni schermo mobile](/help/components/dimensions/mobile-dimensions.md).
* Altezza schermo: Utilizza la dimensione [Altezza schermo mobile](/help/components/dimensions/mobile-dimensions.md).
* Larghezza schermo: Utilizza la dimensione [Larghezza schermo mobile](/help/components/dimensions/mobile-dimensions.md).
* Supporto per cookie: Utilizza la dimensione [Supporto cookie per dispositivi mobili](/help/components/dimensions/mobile-dimensions.md) .
* Supporto immagini: Utilizza la dimensione [Supporto immagini mobile](/help/components/dimensions/mobile-dimensions.md).
* Profondità colore: Utilizza la dimensione [Profondità colore mobile](/help/components/dimensions/mobile-dimensions.md).
* Supporto audio: Utilizza la dimensione [Supporto audio mobile](/help/components/dimensions/mobile-dimensions.md) .
* Supporto video: Utilizza la dimensione [Supporto video mobile](/help/components/dimensions/mobile-dimensions.md) .
* Sistema operativo (obsoleto): Utilizza la dimensione [Sistema operativo mobile (obsoleto)](/help/components/dimensions/mobile-dimensions.md) .

## Paths (Percorsi)

Contiene rapporti che ti consentono di visualizzare i dati del percorso per i visitatori.

* Flusso pagina successivo: Utilizza un rapporto di flusso sull’elemento della dimensione della pagina superiore. Le visualizzazioni del percorso sono simili a [Istanze](/help/components/metrics/instances.md). Puoi modificare l’elemento della dimensione segnalato. Un rapporto simile in Analysis Workspace è disponibile utilizzando una [visualizzazione Flusso](../analysis-workspace/visualizations/c-flow/flow.md).
* Pagina successiva: Prende l’elemento dimensione pagina superiore e mostra le pagine successive a cui i visitatori sono andati.
* Flusso pagina precedente: Utilizza un rapporto di flusso sull&#39;elemento dimensione pagina principale Un rapporto simile in Analysis Workspace è disponibile utilizzando una [visualizzazione di flusso](../analysis-workspace/visualizations/c-flow/flow.md).
* Pagina precedente: Prende l’elemento dimensione pagina superiore e mostra le pagine precedenti da cui provengono i visitatori.
* Abbandono: Consente di selezionare gli elementi dimensionali della pagina in passaggi e mostra la proporzione di persone che hanno seguito o meno quel percorso. Un rapporto simile in Analysis Workspace è disponibile utilizzando una [visualizzazione Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Percorsi completi: Mostra singoli percorsi come elementi dimensionali. in pensione in Analysis Workspace; utilizza invece la [visualizzazione Flusso](../analysis-workspace/visualizations/c-flow/flow.md).
* PathFinder: Fornisce diversi tipi di rapporti che consentono di analizzare i percorsi (ritirati in Analysis Workspace).
* Lunghezza del percorso: Utilizza la dimensione [Profondità visita](/help/components/dimensions/visit-depth.md).
* Analisi delle pagine
   * Riepilogo pagina: Prende l’elemento della dimensione della pagina superiore e mostra una vista con tendenze. Mostra anche punti di ingresso, pagine precedenti, punti di uscita e pagine successive per l’elemento dimensione pagina principale.
   * Ricarica: Utilizza la dimensione [Pagina](/help/components/dimensions/page.md) con la metrica [Ricarica](/help/components/metrics/reloads.md).
   * Tempo trascorso sulla pagina: Utilizza la dimensione [Tempo trascorso sulla pagina - bucket](/help/components/dimensions/time-spent-on-page.md) .
   * Clic sulla pagina: Prende l’elemento della dimensione della pagina superiore e mostra il numero di clic necessari per arrivare a quella pagina in una determinata visita.
* Entrate e uscite
   * Pagine di ingresso: Utilizza la dimensione [Pagine di ingresso](/help/components/dimensions/entry-dimensions.md) .
   * Pagine iniziali originali: Utilizza la dimensione [Originale pagina di ingresso](/help/components/dimensions/entry-dimensions.md).
   * Visite a pagina singola: Utilizza la dimensione [Pagina](/help/components/dimensions/page.md) con il segmento &quot;Visite a pagina singola&quot; fornito dall’Adobe applicato.
   * Pagine di uscita: Utilizza la dimensione [Pagine di uscita](/help/components/dimensions/exit-dimensions.md).

>[!NOTE]
>
>Altri rapporti possono essere visualizzati in questa cartella. Si tratta di altre dimensioni, ad esempio proprietà, in cui il percorso [è abilitato](../../admin/admin/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti.

## Origini del traffico

Contiene un rapporto che fornisce indicazioni su dove sono arrivati i visitatori prima di arrivare al tuo sito. Questi rapporti non funzionano correttamente a meno che tu non abbia impostato correttamente [Filtri URL interni](../../admin/admin/internal-url-filter-admin.md) nelle impostazioni della suite di rapporti.

* Parole chiave di ricerca - tutto: Utilizza la dimensione [Parola chiave di ricerca](/help/components/dimensions/search-keyword.md).
* Parole chiave di ricerca - paid: Utilizza la dimensione [Parola chiave di ricerca - paid](/help/components/dimensions/search-keyword.md) .
* Parole chiave di ricerca - naturali: Utilizza la dimensione [Parola chiave di ricerca - natural](/help/components/dimensions/search-keyword.md)
* Motori di ricerca - tutti: Utilizza la dimensione [Motore di ricerca](/help/components/dimensions/search-engine.md).
* Motori di ricerca - a pagamento: Utilizza la dimensione [Motore di ricerca - paid](/help/components/dimensions/search-engine.md) .
* Motori di ricerca - naturali: Utilizza la dimensione [Motore di ricerca - natural](/help/components/dimensions/search-engine.md) .
* Classificazione di tutte le pagine di ricerca: Utilizza la dimensione [All search page rank](/help/components/dimensions/all-search-page-rank.md) .
* Domini di riferimento: Utilizza la dimensione [Dominio di riferimento](/help/components/dimensions/referring-domain.md)
* Domini di riferimento originali: Utilizza la dimensione [Dominio di riferimento originale](/help/components/dimensions/original-referring-domain.md)
* Riferimenti: Utilizza la dimensione [Referrer](/help/components/dimensions/referrer.md) .
* Tipi di referente: Utilizza la dimensione [Tipo referente](/help/components/dimensions/referrer-type.md).

## Campagne

Contiene principalmente rapporti relativi alla dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md).

* Funnel di conversione campagna: Report click-through, [Pagamenti](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md) e [Entrate](/help/components/metrics/revenue.md) in un rapporto funnel. La metrica di click-through è simile alla metrica [Istanze](/help/components/metrics/instances.md) nel contesto della dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md) . Una visualizzazione simile è possibile in Analysis Workspace utilizzando la visualizzazione [Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Codice di tracciamento: Utilizza la dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md).

## Prodotti

Contiene principalmente rapporti relativi alla dimensione [Prodotto](/help/components/dimensions/product.md).

* Funnel di conversione prodotti: Report [Visualizzazioni prodotto](/help/components/metrics/product-views.md), [Aggiunte carrello](/help/components/metrics/cart-additions.md), [Pagamenti](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md), [Unità](/help/components/metrics/units.md) e [Entrate](/help/components/metrics/revenue.md) in un rapporto funnel. Una visualizzazione simile è possibile in Analysis Workspace utilizzando la visualizzazione [Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Prodotti: Utilizza la dimensione [Prodotti](/help/components/dimensions/product.md).
* Cross-selling: Mostra i prodotti comunemente venduti insieme (in pensione in Analysis Workspace).
* Categorie: Utilizza la dimensione [Categoria](/help/components/dimensions/category.md).

## Conservazione dei visitatori

Contiene rapporti sui visitatori che ritornano al sito.

* Frequenza di ritorno: Utilizza la dimensione [Frequenza di ritorno](/help/components/dimensions/return-frequency.md).
* Visite di ritorno: Tende la metrica [Visite](/help/components/metrics/visits.md) nel tempo con il segmento &quot;Visite di ritorno&quot; fornito dall’Adobe applicato.
* Numero della visita: Utilizza la dimensione [Numero visita](/help/components/dimensions/visit-number.md).
* Ciclo di vendita: Cartella per i rapporti relativi all’acquisto.
   * Fedeltà del cliente: Utilizza la dimensione [Fedeltà cliente](/help/components/dimensions/customer-loyalty.md) .
   * Giorni precedenti al primo acquisto: Utilizza la dimensione [Giorni precedenti al primo acquisto](/help/components/dimensions/days-before-first-purchase.md).
   * Giorni dall’ultimo acquisto: Utilizza la dimensione [Giorni dall&#39;ultimo acquisto](/help/components/dimensions/days-since-last-purchase.md).
   * Clienti univoci giornalieri: Tendenze [Visitatori unici giornalieri](/help/components/metrics/unique-visitors.md) nel tempo con il segmento &quot;acquirenti&quot; fornito dall’Adobe applicato.
   * Clienti unici settimanali: Tendenze [Visitatori unici settimanali](/help/components/metrics/unique-visitors.md) nel tempo con il segmento &quot;acquirenti&quot; fornito dall’Adobe applicato.
   * Clienti unici mensili: Tendenze [Visitatori unici mensili](/help/components/metrics/unique-visitors.md) nel tempo con il segmento &quot;acquirenti&quot; fornito dall’Adobe applicato.
   * Clienti unici trimestrali: Tendenze [Visitatori unici trimestrali](/help/components/metrics/unique-visitors.md) nel tempo con il segmento &quot;acquirenti&quot; fornito dall’Adobe applicato. I trimestri sono gennaio-marzo, aprile-giugno, luglio-settembre e ottobre-dicembre.
   * Clienti unici annuali: Tendenze [Visitatori unici annuali](/help/components/metrics/unique-visitors.md) nel tempo con il segmento &quot;acquirenti&quot; fornito dall’Adobe applicato.

## Profilo visitatore

Contiene rapporti sugli utenti che visitano il sito.

* Geosegmentazione: Segnala da dove provengono gli hit globali per il sito.
   * Paesi: Utilizza la dimensione [Nazioni](/help/components/dimensions/countries.md) .
   * Regione: Utilizza la dimensione [Regioni](/help/components/dimensions/regions.md).
   * Città: Utilizza la dimensione [Città](/help/components/dimensions/cities.md).
   * Stati Uniti: Utilizza la dimensione [Stati Uniti](/help/components/dimensions/us-states.md) .
   * DMA USA: Utilizza la dimensione [DMA](/help/components/dimensions/us-dma.md) US.
* Lingue: Utilizza la dimensione [Lingua](/help/components/dimensions/language.md).
* Fusi orari: Utilizza la dimensione del fuso orario (ritirata in Analysis Workspace). Gli elementi Dimension sono l&#39;offset GMT dell&#39;hit.
* Dominio: Utilizza la dimensione [Dominio](/help/components/dimensions/domain.md).
* Dominio di livello principale: Utilizza la dimensione del dominio di primo livello (ritirato in Analysis Workspace). Raggruppa la dimensione [domini](/help/components/dimensions/domain.md) in categorie di livello superiore, in genere per paese del dominio.
* Tecnologia: Cartella contenente i rapporti relativi all’accesso al sito da parte del visitatore.
   * Browser: Utilizza la dimensione [Browser](/help/components/dimensions/browser.md).
   * Tipo di browser: Utilizza la dimensione [Tipo di browser](/help/components/dimensions/browser-type.md).
   * Larghezza browser: Utilizza la dimensione [Larghezza browser - bucket](/help/components/dimensions/browser-width.md).
   * Altezza browser: Utilizza la dimensione [Altezza browser - bucket](/help/components/dimensions/browser-height.md).
   * Sistema operativo: Utilizza la dimensione [Sistemi operativi](/help/components/dimensions/operating-systems.md).
   * Tipo di sistema operativo: Utilizza la dimensione [Tipi di sistema operativo](/help/components/dimensions/operating-system-types.md).
   * Profondità colore del monitor: Utilizza la dimensione [Profondità colore](/help/components/dimensions/color-depth.md).
   * Risoluzione del monitor: Utilizza la dimensione [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md).
   * Java: Utilizza la dimensione [Java enabled](/help/components/dimensions/java-enabled.md).
   * JavaScript: Utilizza la dimensione abilitata per JavaScript (ritirata in Analysis Workspace). Gli elementi di Dimension sono &quot;Abilitato&quot;, &quot;Disabilitato&quot; o &quot;Sconosciuto&quot;, a seconda che il browser abbia abilitato JavaScript.
   * Versione JavaScript: utilizza la dimensione di versione JavaScript (ritirata in Analysis Workspace). Gli elementi di Dimension mostrano la versione di JavaScript utilizzata dal browser.
   * Cookie: Utilizza la dimensione [Supporto cookie](/help/components/dimensions/cookie-support.md) .
   * Tipi di connessione: Utilizza la dimensione [Tipo di connessione](/help/components/dimensions/connection-type.md).
   * Operatore di telefonia mobile: Utilizza la dimensione [Mobile carrier](/help/components/dimensions/mobile-dimensions.md) .
* Stato del visitatore: Utilizza la dimensione Stato (ritirata in Analysis Workspace). Gli elementi di Dimension provengono dalla variabile [`state`](../../implement/vars/page-vars/state.md) .
* CAP del visitatore: Utilizza la dimensione [Codice postale](/help/components/dimensions/zip-code.md).

## Conversione personalizzata

Contiene rapporti specifici per l’implementazione. I rapporti di conversione personalizzati utilizzano [eVar](/help/components/dimensions/evar.md) come dimensione.

## Traffico personalizzato

Contiene rapporti specifici per l’implementazione. I rapporti sul traffico personalizzati utilizzano [props](/help/components/dimensions/prop.md) come dimensione.

## Canali di marketing

Contiene rapporti che coinvolgono [canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Rapporto di panoramica sul canale: Un rapporto personalizzato specifico per Reports &amp; Analytics. Utilizza canali di marketing come elementi dimensionali, con metriche che utilizzano l’attribuzione di primo o ultimo contatto.
* Canale di primo contatto: Utilizza la dimensione [Canale di primo contatto](/help/components/dimensions/first-touch-channel.md).
* Dettaglio del canale di primo contatto: Utilizza la dimensione [Dettaglio canale di primo contatto](/help/components/dimensions/first-touch-detail.md) .
* Canale ultimo contatto: Utilizza la dimensione [Canale ultimo contatto](/help/components/dimensions/last-touch-channel.md) .
* Dettaglio del canale di ultimo contatto: Utilizza la dimensione [Dettaglio del canale di ultimo contatto](/help/components/dimensions/last-touch-detail.md) .

## Segnalibri

Contiene i rapporti contrassegnati come segnalibri. Per ulteriori informazioni, consulta [Segnalibri](bookmarks.md) .

## Dashboard

Contiene le dashboard create dall’utente. Per ulteriori informazioni, consulta [Dashboard](dashboard.md) .

## Target

Contiene le destinazioni create. Per ulteriori informazioni, consulta [Target](targets.md) .

>[!NOTE]
>
>Se non riesci a trovare il rapporto in questa pagina della guida, è possibile che l&#39;amministratore abbia rinominato o modificato le cartelle. Consulta [Personalizzazione del menu](/help/admin/admin/customize-menus.md) nella guida utente Admin.
