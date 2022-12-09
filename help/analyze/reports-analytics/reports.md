---
title: Rapporti
description: Dimensioni e metriche utilizzate da Reports & Analytics per ogni rapporto.
feature: Reports & Analytics Basics
role: User, Admin
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
source-git-commit: 17b5185e5358d661157c20a2504cacdbd4a2cc3d
workflow-type: tm+mt
source-wordcount: '1950'
ht-degree: 100%

---

# Rapporti

{{ra-eol}}

Ogni rapporto in Reports &amp; Analytics utilizza una dimensione dedicata e una metrica predefinita. Puoi modificare la metrica in ciascun rapporto e aggiungere suddivisioni, se necessario. Gli elenchi seguenti forniscono la dimensione utilizzata in ciascun rapporto.

>[!NOTE]
>
>Il menu dei rapporti può avere un aspetto diverso a seconda delle personalizzazioni effettuate da un amministratore nell’organizzazione. Vedi [Personalizzazione del menu](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md) nella guida utente Admin.

>[!IMPORTANT]
>A partire dal **31 dicembre 2023**, Adobe intende interrompere Reports &amp; Analytics e i relativi rapporti e funzioni. A quel punto, Reports &amp; Analytics e tutti i suoi rapporti e programmi cesseranno di funzionare. I rapporti, le visualizzazioni e la tecnologia di base che alimentano Reports &amp; Analytics non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di Reports &amp; Analytics sono disponibili in Analysis Workspace. Dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di Reports &amp; Analytics sono state spostate in Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. Questo avviso spiega il processo di fine del ciclo di vita.

## Metriche del sito

Contiene rapporti che in genere presentano tendenze utilizzando un intervallo di date. Contiene anche rapporti univoci, ad esempio rapporti consigliati e rapporti in tempo reale.

* Rapporti consigliati: crea una dashboard contenente diversi reportlet per approfondimenti immediati.
* Metriche chiave: rapporto che ti consente di generare tendenze fino a cinque metriche alla volta. Genera tendenze su [Visualizzazioni pagina](/help/components/metrics/page-views.md), [Visite](/help/components/metrics/visits.md) e [Visitatori unici](/help/components/metrics/unique-visitors.md) per impostazione predefinita.
* Visualizzazioni di pagina: genera tendenze sulla metrica [Visualizzazioni pagina](/help/components/metrics/page-views.md) nel tempo.
* Visite: genera tendenze sulla metrica [Visite](/help/components/metrics/visits.md) nel tempo.
* Visitatori: genera tendenze su varie metriche [Visitatori unici](/help/components/metrics/unique-visitors.md) nel tempo.
   * Visitatori unici: conta i visitatori una sola volta per l’intero intervallo di date selezionato.
   * Visitatori unici orari: conta i visitatori più volte se visitano in diverse ore dell’intervallo di date selezionato.
   * Visitatori unici giornalieri: conta i visitatori più volte se visitano durante giorni diversi dell’intervallo di date selezionato.
   * Visitatori unici settimanali: conta i visitatori più volte se visitano durante diverse settimane dell’intervallo di date selezionato.
   * Visitatori unici mensili: conta i visitatori più volte se visitano durante diversi mesi dell’intervallo di date selezionato.
   * Visitatori unici trimestrali: conta i visitatori più volte se effettuano visite durante diversi trimestri dell’intervallo di date selezionato. I trimestri sono gennaio-marzo, aprile-giugno, luglio-settembre e ottobre-dicembre.
   * Visitatori unici annuali: conta i visitatori più volte se visitano durante diversi anni di calendario dell’intervallo di date selezionato.
* Tempo trascorso per visita: usa la dimensione [Tempo trascorso per visita - a blocchi](/help/components/dimensions/time-spent-per-visit.md).
* Tempo precedente all’evento: usa la dimensione [Tempo precedente all’evento](/help/components/dimensions/time-prior-to-event.md).
* Acquisti: contiene rapporti sulle metriche basate sugli acquisti.
   * Funnel di conversione acquisto: rapporto su [Visite](/help/components/metrics/visits.md), [Carrelli](/help/components/metrics/carts.md), [Ordini](/help/components/metrics/orders.md), [Entrate](/help/components/metrics/revenue.md) e [Unità](/help/components/metrics/units.md) in un rapporto funnel. Una visualizzazione simile viene ottenuta in Analysis Workspace utilizzando [Visualizzazione di fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Entrate: genera tendenze sulla metrica [Entrate](/help/components/metrics/revenue.md) nel tempo.
   * Ordini: genera tendenze sulla metrica [Ordini](/help/components/metrics/orders.md) nel tempo.
   * Unità: genera tendenze sulla metrica [Unità](/help/components/metrics/units.md) nel tempo.
* Carrello: contiene rapporti sulle metriche del carrello acquisti.
   * Funnel di conversione del carrello: rapporto su [Istanze](/help/components/metrics/instances.md), [Carrelli](/help/components/metrics/carts.md), [Pagamenti](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md) e [Entrate](/help/components/metrics/revenue.md) in un rapporto funnel.
   * Carrelli: genera tendenze sulla metrica [Carrelli](/help/components/metrics/carts.md) nel tempo.
   * Visualizzazioni carrello: genera tendenze sulla metrica [Visualizzazioni del carrello](/help/components/metrics/cart-views.md) nel tempo.
   * Aggiunte al carrello: genera tendenze sulla metrica [Aggiunte al carrello](/help/components/metrics/cart-additions.md) nel tempo.
   * Rimozioni dal carrello: genera tendenze sulla metrica [Rimozioni dal carrello](/help/components/metrics/cart-removals.md) nel tempo.
   * Pagamenti: genera tendenze sulla metrica [Pagamenti](/help/components/metrics/checkouts.md) nel tempo.
* Eventi personalizzati: contiene tutti i rapporti intorno all&#39;oggetto personalizzato [Eventi](/help/components/metrics/custom-events.md) specifici per l&#39;implementazione.
* Bot: mostra rapporti relativi ai bot.
   * Bot: mostra i bot che più frequentano il tuo sito. Vedi [Regole bot](../../admin/admin/bot-removal/bot-rules.md) nella guida utente Admin.
   * Pagine bot: mostra le pagine più visitate dai bot.
* In tempo reale: mostra determinate dimensioni e metriche entro pochi secondi dalla raccolta dei dati. Per ulteriori informazioni, consulta [Rapporti in tempo reale](/help/components/c-real-time-reporting/realtime.md).

## Contenuto del sito

Contiene rapporti sulle dimensioni che in genere visualizzano il contenuto del sito. Puoi applicare le classificazioni ad alcuni di questi rapporti. Se si applicano le classificazioni, un rapporto diventa un menu contenente il rapporto di origine e i rapporti di classificazione.

* Pagine: usa la dimensione [Pagina](/help/components/dimensions/page.md).
* Sezione del sito: usa la dimensione [Sezione del sito](/help/components/dimensions/site-section.md).
* Server: usa la dimensione [Server](/help/components/dimensions/server.md).
* Collegamenti: contiene rapporti che utilizzano il tracciamento dei collegamenti.
   * Collegamenti di uscita: usa la dimensione [Collegamento di uscita](/help/components/dimensions/exit-link.md).
   * Download dei file: usa la dimensione [Collegamento di download](/help/components/dimensions/download-link.md).
   * Collegamenti personalizzati: usa la dimensione [Collegamento personalizzato](/help/components/dimensions/custom-link.md).
   * Pagine non trovate: usa la dimensione [Pagine non trovate](/help/components/dimensions/pages-not-found.md).

## Mobile

Contiene rapporti sui rapporti dei dispositivi mobili legacy. Questi report basano i loro dati sulla stringa dell&#39;agente utente. Utilizzano varie [dimensioni dei dispositivi mobili](/help/components/dimensions/mobile-dimensions.md) per le rispettive relazioni.

* Dispositivi: usa la dimensione [Dispositivo mobile](/help/components/dimensions/mobile-dimensions.md).
* Tipo di dispositivo: usa la dimensione [Tipo di dispositivo mobile](/help/components/dimensions/mobile-dimensions.md).
* Produttore: usa la dimensione [produttore di dispositivi mobili](/help/components/dimensions/mobile-dimensions.md).
* Dimensioni dello schermo: usa la dimensione [Dimensioni schermo del dispositivo mobile](/help/components/dimensions/mobile-dimensions.md).
* Altezza schermo: usa la dimensione [Altezza schermo dispositivo mobile](/help/components/dimensions/mobile-dimensions.md).
* Larghezza schermo: usa la dimensione [Larghezza dello schermo del dispositivo mobile](/help/components/dimensions/mobile-dimensions.md).
* Supporto per cookie: usa la dimensione [Supporto cookie per dispositivi mobili](/help/components/dimensions/mobile-dimensions.md).
* Supporto immagini: usa la dimensione [Supporto per immagini per dispositivi mobili](/help/components/dimensions/mobile-dimensions.md).
* Profondità colore: usa la dimensione [Profondità colore dispositivi mobili](/help/components/dimensions/mobile-dimensions.md).
* Supporto audio: usa la dimensione [Supporto audio per dispositivi mobili](/help/components/dimensions/mobile-dimensions.md).
* Supporto video: usa la dimensione [Supporto video per dispositivi mobili](/help/components/dimensions/mobile-dimensions.md).
* Sistema operativo (obsoleto): usa la dimensione [Sistema operativo mobile (obsoleto)](/help/components/dimensions/mobile-dimensions.md).

## Paths (Percorsi)

Contiene rapporti che ti consentono di visualizzare i dati del percorso per i visitatori.

* Flusso pagina successivo: usa un rapporto di flusso sull’elemento della dimensione della pagina superiore. Le visualizzazioni del percorso sono simili a [Istanze](/help/components/metrics/instances.md). Puoi modificare l’elemento della dimensione segnalato. Un rapporto simile in Analysis Workspace è disponibile utilizzando una [Visualizzazione del flusso](../analysis-workspace/visualizations/c-flow/flow.md).
* Pagina successiva: prende l’elemento dimensione pagina superiore e mostra le pagine successive in cui i visitatori sono andati.
* Flusso pagina precedente: usa un rapporto di flusso sull&#39;elemento dimensione pagina principale. È disponibile un rapporto simile in Analysis Workspace utilizzando una [Visualizzazione del flusso](../analysis-workspace/visualizations/c-flow/flow.md).
* Pagina precedente: prende l’elemento dimensione pagina superiore e mostra le pagine precedenti da cui provengono i visitatori.
* Fallout: consente di selezionare gli elementi dimensionali della pagina in passaggi e mostra la proporzione di persone che hanno seguito o meno quel percorso. Un rapporto simile in Analysis Workspace è disponibile utilizzando una [Visualizzazione di fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Percorsi completi: mostra singoli percorsi come elementi dimensionali. Ritirato in Analysis Workspace; usa invece la [Visualizzazione del flusso](../analysis-workspace/visualizations/c-flow/flow.md).
* PathFinder: fornisce diversi tipi di rapporti che consentono di analizzare i percorsi (ritirati in Analysis Workspace).
* Lunghezza del percorso: usa la dimensione [Profondità della visita](/help/components/dimensions/visit-depth.md).
* Analisi delle pagine
   * Riepilogo pagina: prende l’elemento della dimensione della pagina superiore e mostra una vista con tendenze. Mostra anche punti di ingresso, pagine precedenti, punti di uscita e pagine successive per l’elemento dimensione pagina principale.
   * Ricarica: usa la dimension [Pagina](/help/components/dimensions/page.md) con la metrica [Ricarica](/help/components/metrics/reloads.md).
   * Tempo trascorso sulla pagina: usa la dimensione [Tempo trascorso sulla pagina - a blocchi](/help/components/dimensions/time-spent-on-page.md).
   * Clic sulla pagina: prende l’elemento della dimensione della pagina superiore e mostra il numero di clic necessari per arrivare a quella pagina in una determinata visita.
* Entrate e uscite
   * Pagine di ingresso: us ala dimensione [Pagine di ingresso](/help/components/dimensions/entry-dimensions.md).
   * Pagine iniziali originali: usa la dimensione [Pagina di ingresso originale](/help/components/dimensions/entry-dimensions.md).
   * Visite a pagina singola: usa la dimensione [Pagina](/help/components/dimensions/page.md) con il segmento “Visite a pagina singola” fornito dall’Adobe applicato.
   * Pagine di uscita: usa la dimensione [Esci dalle pagine](/help/components/dimensions/exit-dimensions.md).

>[!NOTE]
>
>Altri rapporti possono essere visualizzati in questa cartella. Sono altre dimensioni, come prop, in cui sono stati [abilitati dei percorsi](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti.

## Origini di traffico

Contiene un rapporto che fornisce indicazioni sulla provenienza dei visitatori, dove si trovavano prima di arrivare al tuo sito. Questi rapporti funzionano correttamente solo se vengono impostati correttamente i [Filtri per URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) nelle impostazioni della suite di rapporti.

* Parole chiave di ricerca - tutto: usa la dimensione [Parola chiave di ricerca](/help/components/dimensions/search-keyword.md).
* Parole chiave di ricerca - a pagamento: usa la dimensione [Parola chiave di ricerca - a pagamento](/help/components/dimensions/search-keyword.md).
* Parole chiave di ricerca - naturale: usa la dimensione [Parola chiave di ricerca - naturale](/help/components/dimensions/search-keyword.md)
* Motori di ricerca - tutti: usa la dimensione [Motore di ricerca](/help/components/dimensions/search-engine.md).
* Motori di ricerca - a pagamento: usa la dimensione [Motore di ricerca - a pagamento](/help/components/dimensions/search-engine.md).
* Motori di ricerca - naturale: usa la dimensione [Motore di ricerca - naturale](/help/components/dimensions/search-engine.md).
* Classificazione di tutte le pagine di ricerca: usa la dimensione [Classificazione di tutte le pagine di ricerca](/help/components/dimensions/all-search-page-rank.md).
* Domini di riferimento: usa la dimensione [Dominio di riferimento](/help/components/dimensions/referring-domain.md)
* Domini di riferimento originali: usa la dimensione [Dominio di riferimento originale](/help/components/dimensions/original-referring-domain.md)
* URL di provenienza: usa la dimensione [Referrer](/help/components/dimensions/referrer.md).
* Tipi di URL di provenienza: usa la dimensione [Tipo di referrer](/help/components/dimensions/referrer-type.md).

## Campagne

Contiene rapporti principalmente relativi alla dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md).

* Funnel di conversione campagna: presenta i click-through, [Pagamenti](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md) e [Ricavi](/help/components/metrics/revenue.md) sotto forma di un rapporto funnel. La metrica dei click-through è simile alla metrica [Istanze](/help/components/metrics/instances.md) nel contesto della dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md). Una visualizzazione simile viene ottenuta in Analysis Workspace utilizzando [Visualizzazione di fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Codice di tracciamento: usa la dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md).

## Prodotti

Contiene rapporti principalmente relativi alla dimensione [Prodotto](/help/components/dimensions/product.md).

* Funnel di conversione prodotti: presenta [Visualizzazioni di prodotti](/help/components/metrics/product-views.md), [Aggiunte al carrello](/help/components/metrics/cart-additions.md), [Pagamenti](/help/components/metrics/checkouts.md), [Ordini](/help/components/metrics/orders.md), [Unità](/help/components/metrics/units.md) e [Ricavi](/help/components/metrics/revenue.md) sotto forma di rapporto funnel. Una visualizzazione simile viene ottenuta in Analysis Workspace utilizzando [Visualizzazione di fallout](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Prodotti: usa la dimensione [Prodotti](/help/components/dimensions/product.md).
* Cross-selling: mostra i prodotti comunemente venduti insieme (ritirato in Analysis Workspace).
* Categorie: usa la dimensione [Categoria](/help/components/dimensions/category.md).

## Conservazione dei visitatori

Contiene rapporti sui visitatori che ritornano al sito.

* Frequenza di ritorno: usa la dimensione [Frequenza di ritorno](/help/components/dimensions/return-frequency.md).
* Visite di ritorno: genera tendenze sulla metrica [Visite](/help/components/metrics/visits.md) nel tempo, con l’applicazione del segmento “Visite di ritorno” fornito da Adobe.
* Numero di visite: usa la dimensione [Numero di visite](/help/components/dimensions/visit-number.md).
* Ciclo di vendita: cartella per i rapporti relativi all’acquisto.
   * Fedeltà del cliente: usa la dimensione [Fedeltà del cliente](/help/components/dimensions/customer-loyalty.md).
   * Giorni prima del primo acquisto: usa la dimensione [Giorni prima del primo acquisto](/help/components/dimensions/days-before-first-purchase.md).
   * Giorni dall’ultimo acquisto: usa la dimensione [Giorni dall’ultimo acquisto](/help/components/dimensions/days-since-last-purchase.md).
   * Clienti univoci giornalieri: genera tendenze su [Visitatori unici giornalieri](/help/components/metrics/unique-visitors.md) nel tempo con l’applicazione del segmento “acquirenti” fornito da Adobe.
   * Clienti univoci settimanali: genera tendenze [Visitatori univoci settimanali](/help/components/metrics/unique-visitors.md) nel tempo con l’applicazione del segmento “acquirenti” fornito da Adobe.
   * Clienti univoci mensili: genera tendenze su [Visitatori univoci mensili](/help/components/metrics/unique-visitors.md) nel tempo con l’applicazione del segmento “acquirenti” fornito da Adobe.
   * Clienti univoci trimestrali: genera tendenze su [Visitatori univoci trimestrali](/help/components/metrics/unique-visitors.md) nel tempo con il segmento “acquirenti” fornito da Adobe applicato. I trimestri sono gennaio-marzo, aprile-giugno, luglio-settembre e ottobre-dicembre.
   * Clienti univoci annuali: genera tendenze su [Visitatori univoci annuali](/help/components/metrics/unique-visitors.md) nel tempo con l’applicazione del segmento “acquirenti” fornito da Adobe applicato.

## Profilo visitatore

Contiene rapporti sugli utenti che visitano il sito.

* Geosegmentazione: segnala da dove provengono gli hit globali per il sito.
   * Paesi: usa la dimensione [Paesi](/help/components/dimensions/countries.md).
   * Area geografica: usa la dimensione [Aree geografiche](/help/components/dimensions/regions.md).
   * Città: usa la dimensione [Città](/help/components/dimensions/cities.md).
   * Stati USA: usa la dimensione [Stati USA](/help/components/dimensions/us-states.md).
   * DMA USA: usa la dimensione [DMA USA](/help/components/dimensions/us-dma.md).
* Lingue: usa la dimensione [Lingua](/help/components/dimensions/language.md).
* Fusi orari: usa la dimensione del fuso orario (ritirata in Analysis Workspace). Questi elementi Dimensione rappresentano la differenza GMT dell’hit.
* Dominio: utilizza la dimensione [Dominio](/help/components/dimensions/domain.md).
* Dominio di livello principale: utilizza la dimensione del dominio di livello principale (ritirato in Analysis Workspace). Raggruppa la dimensione [Domini](/help/components/dimensions/domain.md) in categorie di livello superiore, in genere per paese del dominio.
* Tecnologia: cartella contenente i rapporti relativi alla tecnologia utilizzata dal visitatore per accedere al sito.
   * Browser: utilizza la dimensione [Browser](/help/components/dimensions/browser.md).
   * Tipo di browser: utilizza la dimensione [Tipo di browser](/help/components/dimensions/browser-type.md).
   * Larghezza browser: utilizza la dimensione [Larghezza browser - con bucket](/help/components/dimensions/browser-width.md).
   * Altezza browser: utilizza la dimensione [Altezza browser - con bucket](/help/components/dimensions/browser-height.md).
   * Sistema operativo: utilizza la dimensione [Sistemi operativi](/help/components/dimensions/operating-systems.md).
   * Tipo di sistema operativo: utilizza la dimensione [Tipi di sistemi operativi](/help/components/dimensions/operating-system-types.md).
   * Profondità colore del monitor: utilizza la dimensione [Profondità colore](/help/components/dimensions/color-depth.md).
   * Risoluzione del monitor: utilizza la dimensione [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md).
   * Java: utilizza la dimensione [Java abilitato](/help/components/dimensions/java-enabled.md).
   * JavaScript: utilizza la dimensione JavaScript abilitato (ritirata in Analysis Workspace). Gli elementi dimensione sono “Enabled” (Abilitato, “Disabled” (Disabilitato) o “Unknown” (Sconosciuto), a seconda che JavaScript sia abilitato o meno nel browser).
   * Versione JavaScript: utilizza la dimensione versione JavaScript (ritirata in Analysis Workspace). Gli elementi dimensione mostrano la versione di JavaScript utilizzata dal browser.
   * Cookie: utilizza la dimensione [Supporto cookie](/help/components/dimensions/cookie-support.md).
   * Tipi di connessione: utilizza la dimensione [Tipo di connessione](/help/components/dimensions/connection-type.md).
   * Operatore mobile: utilizza la dimensione [Operatore mobile](/help/components/dimensions/mobile-dimensions.md).
* Stato del visitatore: utilizza la dimensione Stato (ritirata in Analysis Workspace). Gli elementi dimensione provengono dalla variabile [`state`](../../implement/vars/page-vars/state.md).
* Codice postale del visitatore: utilizza la dimensione [Codice postale](/help/components/dimensions/zip-code.md).

## Conversione personalizzata

Contiene rapporti specifici dell’implementazione. I rapporti di conversione personalizzati utilizzano [eVar](/help/components/dimensions/evar.md) come dimensione.

## Traffico personalizzato

Contiene rapporti specifici dell’implementazione. I rapporti sul traffico personalizzati utilizzano [prop](/help/components/dimensions/prop.md) come dimensione.

## Canali di marketing

Contiene rapporti che riguardano i [Canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Rapporto di panoramica sul canale: rapporto personalizzato specifico di Reports &amp; Analytics. Utilizza canali di marketing come elementi dimensione, con metriche che sfruttano l’attribuzione di primo o ultimo contatto.
* Canale di primo contatto: utilizza la dimensione [Canale di primo contatto](/help/components/dimensions/first-touch-channel.md).
* Dettaglio del canale di primo contatto: utilizza la dimensione [Dettaglio canale di primo contatto](/help/components/dimensions/first-touch-detail.md).
* Canale ultimo contatto: utilizza la dimensione [Canale di ultimo contatto](/help/components/dimensions/last-touch-channel.md).
* Dettaglio del canale di ultimo contatto: utilizza la dimensione [Dettaglio del canale di ultimo contatto](/help/components/dimensions/last-touch-detail.md).

## Segnalibri

Contiene i rapporti contrassegnati con segnalibri. Per ulteriori informazioni, consulta [Segnalibri](bookmarks.md).

## Dashboard

Contiene le dashboard che hai creato. Per ulteriori informazioni, consulta [Dashboard](dashboard.md).

## Target

Contiene i target che hai creato. Per ulteriori informazioni, consulta [Target](targets.md).

>[!NOTE]
>
>Se non riesci a trovare il rapporto in questa pagina della guida, è possibile che l’amministratore abbia rinominato o modificato le cartelle. Consulta [Personalizzazione del menu](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md) nella guida utente dell’amministratore.
