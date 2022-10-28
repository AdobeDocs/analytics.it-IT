---
title: Rapporti
description: Dimensioni e metriche utilizzate da Reports & Analytics per ogni rapporto.
feature: Reports & Analytics Basics
role: User, Admin
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
source-git-commit: 4ddc2640aa8b3a22411c86ff8bfe0ecf345a3d63
workflow-type: tm+mt
source-wordcount: '1950'
ht-degree: 3%

---

# Rapporti

{{ra-eol}}

Ogni rapporto in Reporting e analisi utilizza una dimensione dedicata e una metrica predefinita. Puoi modificare la metrica in ciascun rapporto e aggiungere suddivisioni, se necessario. Gli elenchi seguenti forniscono la dimensione utilizzata in ciascun rapporto.

>[!NOTE]
>
>Il menu dei rapporti può avere un aspetto diverso a seconda delle personalizzazioni effettuate da un amministratore nell’organizzazione. Vedi [Personalizzazione del menu](/help/admin/admin/customize-menus.md) nella guida utente Admin.

>[!IMPORTANT]
>A partire dal **31 dicembre 2023**, Adobe intende interrompere Reports &amp; Analytics e i relativi rapporti e funzioni. A quel punto, Reports &amp; Analytics e tutti i suoi rapporti e programmi cesseranno di funzionare. I report, le visualizzazioni e la tecnologia di base che alimentano Reports &amp; Analytics non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di Reports &amp; Analytics sono disponibili in Analysis Workspace. A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di Reports &amp; Analytics sono state spostate in Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. Questo avviso spiega il processo di fine del ciclo di vita.

## Metriche del sito

Contiene rapporti che in genere presentano tendenze utilizzando un intervallo di date. Contiene anche rapporti univoci, ad esempio rapporti consigliati e rapporti in tempo reale.

* Rapporti consigliati: Crea un dashboard contenente diversi minirapporti per approfondimenti immediati.
* Metriche chiave: Report che ti consente di generare tendenze fino a cinque metriche alla volta. Tendenze [Visualizzazioni pagina](/help/components/metrics/page-views.md), [Visite](/help/components/metrics/visits.md)e [Visitatori unici](/help/components/metrics/unique-visitors.md) per impostazione predefinita.
* Visualizzazioni di pagina: Tendenze [Visualizzazioni pagina](/help/components/metrics/page-views.md) nel tempo.
* Visite: Tendenze [Visite](/help/components/metrics/visits.md) nel tempo.
* Visitatori: Tendenze diverse [Visitatori unici](/help/components/metrics/unique-visitors.md) nel tempo.
   * Visitatori unici: Conta i visitatori una sola volta per l’intero intervallo di date selezionato.
   * Visitatori unici orari: Conta i visitatori più volte se visitano in diverse ore dell’intervallo di date selezionato.
   * Visitatori unici giornalieri: Conta i visitatori più volte se visitano durante giorni diversi dell’intervallo di date selezionato.
   * Visitatori unici settimanali: Conta i visitatori più volte se visitano durante diverse settimane dell’intervallo di date selezionato.
   * Visitatori unici mensili: Conta i visitatori più volte se visitano durante diversi mesi dell’intervallo di date selezionato.
   * Visitatori unici trimestrali: Conta i visitatori più volte se effettuano visite durante diversi trimestri dell’intervallo di date selezionato. I trimestri sono gennaio-marzo, aprile-giugno, luglio-settembre e ottobre-dicembre.
   * Visitatori unici annuali: Conta i visitatori più volte se visitano durante diversi anni di calendario dell’intervallo di date selezionato.
* Tempo trascorso per visita: Utilizza il [Tempo trascorso per visita - a blocchi](/help/components/dimensions/time-spent-per-visit.md) dimensione.
* Tempo precedente all’evento: Utilizza il [Tempo precedente all’evento](/help/components/dimensions/time-prior-to-event.md) dimensione.
* Acquisti: Contiene rapporti sulle metriche basate sugli acquisti.
   * Funnel di conversione acquisto: Rapporto su [Visite](/help/components/metrics/visits.md), [Carrelli](/help/components/metrics/carts.md), [Ordini](/help/components/metrics/orders.md), [Entrate](/help/components/metrics/revenue.md)e [Unità](/help/components/metrics/units.md) in un rapporto funnel. Una visualizzazione simile viene ottenuta in Analysis Workspace utilizzando [Visualizzazione Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Entrate Tendenza della metrica [Entrate](/help/components/metrics/revenue.md) nel tempo.
   * Ordini: Tendenza della metrica [Ordini](/help/components/metrics/orders.md) nel tempo.
   * Unità: Tendenza della metrica [Unità](/help/components/metrics/units.md) nel tempo.
* Carrello: Contiene rapporti sulle metriche del carrello acquisti.
   * Funnel di conversione del carrello: Rapporti [Istanze](/help/components/metrics/instances.md), [Carrelli](/help/components/metrics/carts.md), [Pagamenti](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md)e [Entrate](/help/components/metrics/revenue.md) in un rapporto funnel.
   * Carrelli: Tendenza della metrica [Carrelli](/help/components/metrics/carts.md) nel tempo.
   * Visualizzazioni carrello: Tendenza della metrica [Visualizzazioni del carrello](/help/components/metrics/cart-views.md) nel tempo.
   * Aggiunte al carrello: Tendenza della metrica [Aggiunte al carrello](/help/components/metrics/cart-additions.md) nel tempo.
   * Rimozioni dal carrello: Tendenza della metrica [Rimozioni dal carrello](/help/components/metrics/cart-removals.md) nel tempo.
   * Pagamenti: Tendenza della metrica [Pagamenti](/help/components/metrics/checkouts.md) nel tempo.
* Eventi personalizzati: Contiene tutti i rapporti intorno all&#39;oggetto personalizzato [Eventi](/help/components/metrics/custom-events.md) specifica per la tua implementazione.
* Bot: Mostra rapporti relativi ai bot.
   * Bot: Mostra i bot che più frequentano il tuo sito. Vedi [Regole bot](../../admin/admin/bot-removal/bot-rules.md) nella guida utente Admin.
   * Pagine bot: Mostra le pagine più visitate dai bot.
* In tempo reale: Mostra determinate dimensioni e metriche entro pochi secondi dalla raccolta dei dati. Vedi [Rapporti in tempo reale](/help/components/c-real-time-reporting/realtime.md) per ulteriori informazioni.

## Contenuto del sito

Contiene rapporti sulle dimensioni che in genere visualizzano il contenuto del sito. Puoi applicare le classificazioni ad alcuni di questi rapporti. Se si applicano le classificazioni, un rapporto diventa un menu contenente il rapporto di origine e i rapporti di classificazione.

* Pagine: Utilizza il [Pagina](/help/components/dimensions/page.md) dimensione.
* Sezione del sito: Utilizza il [Sezione del sito](/help/components/dimensions/site-section.md) dimensione.
* Server: Utilizza il [Server](/help/components/dimensions/server.md) dimensione.
* Collegamenti: Contiene rapporti che utilizzano il tracciamento dei collegamenti.
   * Collegamenti di uscita: Utilizza il [Collegamento di uscita](/help/components/dimensions/exit-link.md) dimensione.
   * Download dei file: Utilizza il [Collegamento di download](/help/components/dimensions/download-link.md) dimensione.
   * Collegamenti personalizzati: Utilizza il [Collegamento personalizzato](/help/components/dimensions/custom-link.md) dimensione.
   * Pagine non trovate: Utilizza il [Pagine non trovate](/help/components/dimensions/pages-not-found.md) dimensione.

## Mobile

Contiene rapporti sui rapporti mobili legacy. Questi report basano i loro dati sulla stringa dell&#39;agente utente. Utilizzano varie [dimensioni mobili](/help/components/dimensions/mobile-dimensions.md) per le rispettive relazioni.

* Dispositivi: Utilizza il [Dispositivo mobile](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Tipo di dispositivo: Utilizza il [Tipo di dispositivo mobile](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Produttore: Utilizza il [produttore di dispositivi mobili](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Dimensioni dello schermo: Utilizza il [Dimensioni schermo mobile](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Altezza schermo: Utilizza il [Altezza schermo mobile](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Larghezza schermo: Utilizza il [Larghezza dello schermo mobile](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Supporto per cookie: Utilizza il [Supporto cookie per dispositivi mobili](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Supporto immagini: Utilizza il [Supporto per immagini per dispositivi mobili](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Profondità colore: Utilizza il [Profondità colore mobile](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Supporto audio: Utilizza il [Supporto audio per dispositivi mobili](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Supporto video: Utilizza il [Supporto video per dispositivi mobili](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Sistema operativo (obsoleto): Utilizza il [Sistema operativo mobile (obsoleto)](/help/components/dimensions/mobile-dimensions.md) dimensione.

## Paths (Percorsi)

Contiene rapporti che ti consentono di visualizzare i dati del percorso per i visitatori.

* Flusso pagina successivo: Utilizza un rapporto di flusso sull’elemento della dimensione della pagina superiore. Le visualizzazioni del percorso sono simili a [Istanze](/help/components/metrics/instances.md). Puoi modificare l’elemento della dimensione segnalato. Un rapporto simile in Analysis Workspace è disponibile utilizzando un [Visualizzazione a flusso](../analysis-workspace/visualizations/c-flow/flow.md).
* Pagina successiva: Prende l’elemento dimensione pagina superiore e mostra le pagine successive a cui i visitatori sono andati.
* Flusso pagina precedente: Utilizza un rapporto di flusso sull&#39;elemento dimensione pagina principale Un rapporto simile in Analysis Workspace è disponibile utilizzando un [Visualizzazione a flusso](../analysis-workspace/visualizations/c-flow/flow.md).
* Pagina precedente: Prende l’elemento dimensione pagina superiore e mostra le pagine precedenti da cui provengono i visitatori.
* Abbandono: Consente di selezionare gli elementi dimensionali della pagina in passaggi e mostra la proporzione di persone che hanno seguito o meno quel percorso. Un rapporto simile in Analysis Workspace è disponibile utilizzando un [Visualizzazione Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Percorsi completi: Mostra singoli percorsi come elementi dimensionali. in pensione in Analysis Workspace; utilizza [Visualizzazione a flusso](../analysis-workspace/visualizations/c-flow/flow.md) invece.
* PathFinder: Fornisce diversi tipi di rapporti che consentono di analizzare i percorsi (ritirati in Analysis Workspace).
* Lunghezza del percorso: Utilizza il [Profondità della visita](/help/components/dimensions/visit-depth.md) dimensione.
* Analisi delle pagine
   * Riepilogo pagina: Prende l’elemento della dimensione della pagina superiore e mostra una vista con tendenze. Mostra anche punti di ingresso, pagine precedenti, punti di uscita e pagine successive per l’elemento dimensione pagina principale.
   * Ricarica: Utilizza il [Pagina](/help/components/dimensions/page.md) con [Ricarica](/help/components/metrics/reloads.md) metrica.
   * Tempo trascorso sulla pagina: Utilizza il [Tempo trascorso sulla pagina - a blocchi](/help/components/dimensions/time-spent-on-page.md) dimensione.
   * Clic sulla pagina: Prende l’elemento della dimensione della pagina superiore e mostra il numero di clic necessari per arrivare a quella pagina in una determinata visita.
* Entrate e uscite
   * Pagine di ingresso: Utilizza il [Pagine di ingresso](/help/components/dimensions/entry-dimensions.md) dimensione.
   * Pagine iniziali originali: Utilizza il [Pagina di ingresso originale](/help/components/dimensions/entry-dimensions.md) dimensione.
   * Visite a pagina singola: Utilizza il [Pagina](/help/components/dimensions/page.md) con il segmento &quot;Visite a pagina singola&quot; fornito dall’Adobe applicato.
   * Pagine di uscita: Utilizza il [Esci dalle pagine](/help/components/dimensions/exit-dimensions.md) dimensione.

>[!NOTE]
>
>Altri rapporti possono essere visualizzati in questa cartella. Sono altre dimensioni, come le proprietà, in cui hai [percorsi abilitati](../../admin/admin/c-traffic-variables/traffic-var.md) in impostazioni suite di rapporti.

## Origini del traffico

Contiene un rapporto che fornisce indicazioni su dove sono arrivati i visitatori prima di arrivare al tuo sito. Questi rapporti non funzionano correttamente a meno che non vengano impostati correttamente [Filtri URL interni](../../admin/admin/internal-url-filter-admin.md) in impostazioni suite di rapporti.

* Parole chiave di ricerca - tutto: Utilizza il [Parola chiave di ricerca](/help/components/dimensions/search-keyword.md) dimensione.
* Parole chiave di ricerca - paid: Utilizza il [Parola chiave di ricerca - paid](/help/components/dimensions/search-keyword.md) dimensione.
* Parole chiave di ricerca - naturali: Utilizza il [Parola chiave di ricerca - naturale](/help/components/dimensions/search-keyword.md) dimension
* Motori di ricerca - tutti: Utilizza il [Motore di ricerca](/help/components/dimensions/search-engine.md) dimensione.
* Motori di ricerca - a pagamento: Utilizza il [Motore di ricerca - paid](/help/components/dimensions/search-engine.md) dimensione.
* Motori di ricerca - naturali: Utilizza il [Motore di ricerca - naturale](/help/components/dimensions/search-engine.md) dimensione.
* Classificazione di tutte le pagine di ricerca: Utilizza il [Classificazione di tutte le pagine di ricerca](/help/components/dimensions/all-search-page-rank.md) dimensione.
* Domini di riferimento: Utilizza il [Dominio di riferimento](/help/components/dimensions/referring-domain.md) dimension
* Domini di riferimento originali: Utilizza il [Dominio di riferimento originale](/help/components/dimensions/original-referring-domain.md) dimension
* Riferimenti: Utilizza il [Referrer](/help/components/dimensions/referrer.md) dimensione.
* Tipi di referente: Utilizza il [Tipo referrer](/help/components/dimensions/referrer-type.md) dimensione.

## Campagne

Contiene rapporti principalmente intorno al [Codice di tracciamento](/help/components/dimensions/tracking-code.md) dimensione.

* Funnel di conversione campagna: click-through di rapporti, [Pagamenti](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md)e [Entrate](/help/components/metrics/revenue.md) in un rapporto funnel. La metrica di click-through è simile alla [Istanze](/help/components/metrics/instances.md) nel contesto [Codice di tracciamento](/help/components/dimensions/tracking-code.md) dimensione. Una visualizzazione simile viene ottenuta in Analysis Workspace utilizzando [Visualizzazione Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Codice di tracciamento: Utilizza il [Codice di tracciamento](/help/components/dimensions/tracking-code.md) dimensione.

## Prodotti

Contiene rapporti principalmente intorno al [Prodotto](/help/components/dimensions/product.md) dimensione.

* Funnel di conversione prodotti: Rapporti [Visualizzazioni di prodotti](/help/components/metrics/product-views.md), [Aggiunte al carrello](/help/components/metrics/cart-additions.md), [Pagamenti](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md), [Unità](/help/components/metrics/units.md)e [Entrate](/help/components/metrics/revenue.md) in un rapporto funnel. Una visualizzazione simile viene ottenuta in Analysis Workspace utilizzando [Visualizzazione Abbandono](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Prodotti: Utilizza il [Prodotti](/help/components/dimensions/product.md) dimensione.
* Cross-selling: Mostra i prodotti comunemente venduti insieme (in pensione in Analysis Workspace).
* Categorie: Utilizza il [Categoria](/help/components/dimensions/category.md) dimensione.

## Conservazione dei visitatori

Contiene rapporti sui visitatori che ritornano al sito.

* Frequenza di ritorno: Utilizza il [Frequenza di ritorno](/help/components/dimensions/return-frequency.md) dimensione.
* Visite di ritorno: Tendenze [Visite](/help/components/metrics/visits.md) metrica nel tempo con il segmento &quot;Visite di ritorno&quot; fornito dall’Adobe applicato.
* Numero della visita: Utilizza il [Numero di visite](/help/components/dimensions/visit-number.md) dimensione.
* Ciclo di vendita: Cartella per i rapporti relativi all’acquisto.
   * Fedeltà del cliente: Utilizza il [Fedeltà del cliente](/help/components/dimensions/customer-loyalty.md) dimensione.
   * Giorni precedenti al primo acquisto: Utilizza il [Giorni precedenti al primo acquisto](/help/components/dimensions/days-before-first-purchase.md) dimensione.
   * Giorni dall’ultimo acquisto: Utilizza il [Giorni dall’ultimo acquisto](/help/components/dimensions/days-since-last-purchase.md) dimensione.
   * Clienti univoci giornalieri: Tendenze [Visitatori unici giornalieri](/help/components/metrics/unique-visitors.md) nel tempo con il segmento &quot;acquirenti&quot; fornito dall’Adobe applicato.
   * Clienti unici settimanali: Tendenze [Visitatori unici settimanali](/help/components/metrics/unique-visitors.md) nel tempo con il segmento &quot;acquirenti&quot; fornito dall’Adobe applicato.
   * Clienti unici mensili: Tendenze [Visitatori unici mensili](/help/components/metrics/unique-visitors.md) nel tempo con il segmento &quot;acquirenti&quot; fornito dall’Adobe applicato.
   * Clienti unici trimestrali: Tendenze [Visitatori unici trimestrali](/help/components/metrics/unique-visitors.md) nel tempo con il segmento &quot;acquirenti&quot; fornito dall’Adobe applicato. I trimestri sono gennaio-marzo, aprile-giugno, luglio-settembre e ottobre-dicembre.
   * Clienti unici annuali: Tendenze [Visitatori unici annuali](/help/components/metrics/unique-visitors.md) nel tempo con il segmento &quot;acquirenti&quot; fornito dall’Adobe applicato.

## Profilo visitatore

Contiene rapporti sugli utenti che visitano il sito.

* Geosegmentazione: Segnala da dove provengono gli hit globali per il sito.
   * Paesi: Utilizza il [Paesi](/help/components/dimensions/countries.md) dimensione.
   * Regione: Utilizza il [Aree geografiche](/help/components/dimensions/regions.md) dimensione.
   * Città: Utilizza il [Città](/help/components/dimensions/cities.md) dimensione.
   * Stati Uniti: Utilizza il [Stati Uniti](/help/components/dimensions/us-states.md) dimensione.
   * DMA USA: Utilizza il [DMA USA](/help/components/dimensions/us-dma.md) dimensione.
* Lingue: Utilizza il [Lingua](/help/components/dimensions/language.md) dimensione.
* Fusi orari: Utilizza la dimensione del fuso orario (ritirata in Analysis Workspace). Gli elementi Dimension sono l&#39;offset GMT dell&#39;hit.
* Dominio: Utilizza il [Dominio](/help/components/dimensions/domain.md) dimensione.
* Dominio di livello principale: Utilizza la dimensione del dominio di primo livello (ritirato in Analysis Workspace). Raggruppa le [Domini](/help/components/dimensions/domain.md) in categorie di livello superiore, in genere per paese del dominio.
* Tecnologia: Cartella contenente i rapporti relativi all’accesso al sito da parte del visitatore.
   * Browser: Utilizza il [Browser](/help/components/dimensions/browser.md) dimensione.
   * Tipo di browser: Utilizza il [Tipo di browser](/help/components/dimensions/browser-type.md) dimensione.
   * Larghezza browser: Utilizza il [Larghezza browser - a blocchi](/help/components/dimensions/browser-width.md) dimensione.
   * Altezza browser: Utilizza il [Altezza browser - a blocchi](/help/components/dimensions/browser-height.md) dimensione.
   * Sistema operativo: Utilizza il [Sistemi operativi](/help/components/dimensions/operating-systems.md) dimensione.
   * Tipo di sistema operativo: Utilizza il [Tipi di sistemi operativi](/help/components/dimensions/operating-system-types.md) dimensione.
   * Profondità colore del monitor: Utilizza il [Profondità colore](/help/components/dimensions/color-depth.md) dimensione.
   * Risoluzione del monitor: Utilizza il [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md) dimensione.
   * Java: Utilizza il [Java abilitato](/help/components/dimensions/java-enabled.md) dimensione.
   * JavaScript: Utilizza la dimensione abilitata per JavaScript (ritirata in Analysis Workspace). Gli elementi di Dimension sono &quot;Abilitato&quot;, &quot;Disabilitato&quot; o &quot;Sconosciuto&quot;, a seconda che il browser abbia abilitato JavaScript.
   * Versione JavaScript: utilizza la dimensione di versione JavaScript (ritirata in Analysis Workspace). Gli elementi di Dimension mostrano la versione di JavaScript utilizzata dal browser.
   * Cookie: Utilizza il [Supporto per cookie](/help/components/dimensions/cookie-support.md) dimensione.
   * Tipi di connessione: Utilizza il [Tipo di connessione](/help/components/dimensions/connection-type.md) dimensione.
   * Operatore di telefonia mobile: Utilizza il [Operatore mobile](/help/components/dimensions/mobile-dimensions.md) dimensione.
* Stato del visitatore: Utilizza la dimensione Stato (ritirata in Analysis Workspace). Gli elementi Dimension provengono da [`state`](../../implement/vars/page-vars/state.md) variabile.
* CAP del visitatore: Utilizza il [Codice postale](/help/components/dimensions/zip-code.md) dimensione.

## Conversione personalizzata

Contiene rapporti specifici per l’implementazione. I rapporti di conversione personalizzati utilizzano [eVar](/help/components/dimensions/evar.md) come dimensione.

## Traffico personalizzato

Contiene rapporti specifici per l’implementazione. I rapporti sul traffico personalizzati utilizzano [proprietà](/help/components/dimensions/prop.md) come dimensione.

## Canali di marketing

Contiene rapporti che riguardano [Canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Rapporto di panoramica sul canale: Un rapporto personalizzato specifico per Reports &amp; Analytics. Utilizza canali di marketing come elementi dimensionali, con metriche che utilizzano l’attribuzione di primo o ultimo contatto.
* Canale di primo contatto: Utilizza il [Canale di primo contatto](/help/components/dimensions/first-touch-channel.md) dimensione.
* Dettaglio del canale di primo contatto: Utilizza il [Dettaglio del canale di primo contatto](/help/components/dimensions/first-touch-detail.md) dimensione.
* Canale ultimo contatto: Utilizza il [Canale di ultimo contatto](/help/components/dimensions/last-touch-channel.md) dimensione.
* Dettaglio del canale di ultimo contatto: Utilizza il [Dettaglio del canale di ultimo contatto](/help/components/dimensions/last-touch-detail.md) dimensione.

## Segnalibri

Contiene i rapporti contrassegnati come segnalibri. Vedi [Segnalibri](bookmarks.md) per ulteriori informazioni.

## Dashboard

Contiene le dashboard create dall’utente. Vedi [Dashboard](dashboard.md) per ulteriori informazioni.

## Target

Contiene le destinazioni create. Vedi [Target](targets.md) per ulteriori informazioni.

>[!NOTE]
>
>Se non riesci a trovare il rapporto in questa pagina della guida, è possibile che l&#39;amministratore abbia rinominato o modificato le cartelle. Vedi [Personalizzazione del menu](/help/admin/admin/customize-menus.md) nella guida utente Admin.
