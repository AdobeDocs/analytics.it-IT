---
description: Impostazioni che definiscono l’aspetto di tutti i rapporti e le informazioni che mappano le opzioni di menu predefinite alla loro posizione nel menu semplificato.
solution: Analytics
title: Impostazioni di visualizzazione e navigazione del rapporto
topic: Reports,Reports and analytics
uuid: e7e571ce-a1cf-4714-b400-9571805ceeac
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Impostazioni di visualizzazione e navigazione del rapporto

Impostazioni che definiscono l’aspetto di tutti i rapporti e le informazioni che associano le opzioni di menu predefinite alla loro posizione nel menu semplificato.

## Impostazioni di visualizzazione e navigazione del rapporto {#concept_09832A2CA0FF4982B1AA37C1B635220B}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Report Settings]**

<!--Meike, I replaced this table with one from https://marketing.adobe.com/resources/help/en_US/sc/user/report_settings.html -bob -->

| Elemento | Descrizione |
|--- |--- |
| **Impostazioni generali** |  |
| Includi sezione metriche correlate | Le metriche correlate sono strettamente correlate al rapporto che stai visualizzando (ad esempio, le prime cinque pagine del rapporto visualizzazioni pagina). |
| Mostra media Internet nella sezione dei dettagli | Esprime il valore medio di una determinata statistica, realizzata su diverse migliaia di siti web aziendali. Quando abilitata, questa sezione viene visualizzata come una colonna separata nelle sezioni di riepilogo e dettagli del rapporto. Questa funzione è utilizzata solo dai report sul traffico nel gruppo tecnologico, nonché dai report sui motori di ricerca, sulle lingue e sui domini. |
| Mostra struttura menu predefinita di Adobe | Ignora le impostazioni in Strumenti di amministrazione, in cui gli amministratori personalizzano i menu dei rapporti in base alle preferenze degli utenti, e di nuovo il menu del rapporto alle impostazioni predefinite. |
| Forza la larghezza delle colonne durante la visualizzazione dei rapporti | Forza la larghezza delle colonne del report a una coerenza esteticamente gradevole. Questa impostazione è utile quando vengono visualizzate più di tre metriche. |
| **Grafici e grafici** |  |
| Evidenzia i fine settimana sui grafici di tendenza | Evidenzia verticalmente le date del fine settimana dei grafici con tendenze dei report. I report con tendenze possono essere molto più facili da valutare quando i fine settimana sono identificati. |
| Includi previsione nel grafico e nel riepilogo | Stima quanto si verificherà in futuro una particolare statistica. La previsione viene visualizzata nella sezione di riepilogo del rapporto quando abilitata. |
| Includi eventi calendario nei rapporti | Monitora le prestazioni del sito rispetto a eventi specifici. Quando attivato, questi eventi vengono visualizzati nei rapporti. |
| Utilizzare i grafici Flash | Abilita grafici Flash nei rapporti. I grafici Flash forniscono immagini più nitide e interattive per i rapporti, ma non consentono di copiare o salvare facilmente le immagini. Per una rapida funzionalità di copia o salvataggio delle immagini, disattivate questa opzione (le immagini saranno in formato .gif). Se deselezionate questa opzione, il pulsante Copia grafico non viene visualizzato nella barra degli strumenti del rapporto. |
| Mostra i dati "Tutti gli altri" nei grafici selezionati | Visualizza tutti gli altri sotto i primi cinque raggruppati in un singolo oggetto. (I grafici a barre mostrano le prime cinque pagine Web o altri dati presenti nel rapporto.) |
| Mostra i dati "None", "Unspecified" e "Typed/Bookmarked" nei grafici dei rapporti | Mostra le metriche in cui nessun valore ha ricevuto credito per la metrica specificata. |
| Mostra sparkline nei report classifica | Visualizza un grafico sparkline nel campo dei totali dei report classifica. Questo fornisce una panoramica rapida della tendenza complessiva senza generare un rapporto separato. |
| **Accelerazione** |  |
| Abilita acceleratore report per visualizzare i report più rapidamente | Abilita l'acceleratore di report, che utilizza un algoritmo basato sul tempo per memorizzare nella cache i report richiesti di recente ed esamina solo gli elementi univoci che si verificano più di frequente, con conseguente consegna ancora più rapida dei report. Memorizzando nella cache i report richiesti per 15 minuti, l'acceleratore di report può recuperare tali report per richieste successive quasi immediatamente. Questa impostazione è utile per spostarsi avanti e indietro, stampare rapporti o per accedere frequentemente agli stessi rapporti. Se disabilitato, il sistema rigenera i rapporti ogni volta che vengono richiesti. |
| Abilita dashboard Accelerator e visualizza le versioni disponibili nella cache | Abilita l’acceleratore del dashboard, che memorizza una versione memorizzata nella cache del dashboard per la visualizzazione successiva. Memorizzando nella cache una vista del dashboard per 24 ore, l'acceleratore del dashboard è in grado di recuperare la visualizzazione quasi istantaneamente perché l'esecuzione intensiva di query e elaborazione del database avviene in anticipo. Se la versione disponibile nella cache ha più di 24 ore, viene generato un nuovo dashboard e viene creata una nuova versione memorizzata nella cache. Analogamente, viene creata una nuova versione memorizzata nella cache ogni volta che aggiornate il dashboard (o qualsiasi altro minirapporto visualizzato sul dashboard). La cache è basata sull'utente. Altri utenti che visualizzano un dashboard condiviso visualizzano una versione basata sul proprio utilizzo dell'acceleratore del dashboard e sull'aggiornamento del dashboard. |
| Abilitare l'accelerazione di rete per migliorare le prestazioni dei report | Velocizza la distribuzione dei dati nella tua posizione ottimizzando il percorso tra l'infrastruttura Adobe e l'ambiente. |
| Abilitare l'accelerazione regionale per un'esperienza utente più rapida in Cina | L'Acceleratore regionale utilizza domini con accelerazione specifici per regione, per fornire un'esperienza utente più rapida all'interno di un'area specifica. Attualmente l'accelerazione regionale è supportata solo dalla Cina. Abilitando questa funzione per gli utenti che non si trovano in Cina l’esperienza utente risulterà più lenta. Dopo aver attivato l'accelerazione regionale, è necessario eseguire di nuovo l'accesso affinché l'impostazione abbia un impatto. Se si desidera disattivare l'acceleratore regionale, deselezionare questa casella di controllo. |
| **Lingua/Valuta/Codifica** |  |
| Separatore migliaia | Selezionare un separatore ogni migliaia (decimale o virgola). Molti paesi utilizzano un decimale per separare il numero delle migliaia. (Questo separatore viene applicato a tutti i numeri all'interno del sistema, non solo alla valuta.) |
| Usa la valuta predefinita della suite di rapporti | Specifica se utilizzare la valuta predefinita della suite di rapporti. |
| Valuta | La valuta in cui si desidera convertire i dati. Quando un valore è selezionato in questa impostazione, i dati memorizzati nel database non vengono modificati, ma vengono visualizzati come un valore convertito in base al tasso di conversione della valuta del giorno corrente. Se le opzioni di valuta non sono configurate (impostate sulle impostazioni predefinite) non viene eseguita alcuna conversione di valuta e tutti i valori vengono memorizzati e visualizzati in dollari statunitensi (USD). Per convertire la valuta quando i dati vengono elaborati (prima che vengano visualizzati), contattare il responsabile commerciale. |
| Codifica report pianificata | SHIFT-JIS per la codifica dei caratteri giapponesi. EUC-JP per il codice Unix esteso, principalmente per giapponese, coreano e cinese semplificato. |
| Carattere separatore CSV | Il carattere da usare per separare i valori CSV. |

## Menu di navigazione {#concept_1525EE52F8094535B4240F03B70DD75D}

<!-- 

nav_menu.xml

 -->

Se si utilizza il menu predefinito, la tabella seguente semplifica la ricerca delle opzioni di menu nel menu semplificato.

| Posizione nel menu predefinito | Posizione nel menu semplificato |
|---|---|
| **Metriche del sito** |  |  |
|  | Panoramica del sito | Metriche &gt; Panoramica del sito |
|  | Metriche chiave | Metriche &gt; Metriche chiave |
|  | Visualizzazioni pagina | Metriche &gt; Visualizzazioni pagina |
|  | Visite | Metriche &gt; Visite |
|  | Visitatori | Metriche &gt; Visitatori |
|  | Tempo trascorso per ciascuna visita | Metriche &gt; Tempo trascorso per visita |
|  | Tempo precedente all'evento | Conversione &gt; Tempo precedente all'evento |
|  | Acquisti | Metriche &gt; Acquisti |
|  | Carrello | Metriche &gt; Carrello acquisti |
|  | Eventi personalizzati | Metriche &gt; Eventi personalizzati |
|  | Bot | Pubblico &gt; Bots |
|  | Detección de anomalías | Metriche &gt; Rilevamento delle anomalie |
|  | Real-Time (Tempo reale) | Metriche &gt; Tempo reale |
| **Contenuto del sito** |  |  |
|  | Pagine | Contenuto &gt; Pagine |
|  | Sezione sito | Contenuto &gt; Sezioni del sito |
|  | Server | Contenuto &gt; Server |
|  | Collegamenti | Navigazione &gt; Collegamenti personalizzati; Navigazione &gt; Collegamenti di uscita; Navigazione &gt; ClickMap; Navigazione &gt; Download di file |
|  | Pagine non trovate | Navigazione &gt; Pagine non trovate |
| **Mobile** |  |  |
|  | Dispositivi | Pubblico &gt; Mobile &gt; Dispositivi |
|  | Tipo di dispositivo | Pubblico &gt; Mobile &gt; Tipo di dispositivo |
|  | Produttore | Pubblico &gt; Mobile &gt; Produttore |
|  | Dimensioni dello schermo del dispositivo | Pubblico &gt; Mobile &gt; Dimensione schermo |
|  | Altezza schermo | Pubblico &gt; Mobile &gt; Altezza schermo |
|  | Larghezza schermo | Pubblico &gt; Mobile &gt; Larghezza schermo |
|  | Supporto per cookie | Pubblico &gt; Mobile &gt; Supporto dei cookie |
|  | Supporto immagini | Pubblico &gt; Mobile &gt; Supporto immagini |
|  | Profondità colore | Pubblico &gt; Mobile &gt; Profondità colore |
|  | Supporto audio | Pubblico &gt; Mobile &gt; Supporto audio |
|  | Supporto video | Pubblico &gt; Mobile &gt; Supporto video |
|  | Versione | Pubblico &gt; Mobile &gt; Sistema operativo |
| **Paths (Percorsi)** |  |  |
|  | Pagine | Navigazione &gt; Percorsi &gt; Pagine |
|  | Termini di ricerca interni | Navigazione &gt; Percorsi &gt; Termini di ricerca interni |
| **Origini del traffico** |  |  |
|  | Cerca parola chiave - Tutto | Origini di traffico &gt; Cerca parola chiave - Tutto |
|  | Parola chiave di ricerca - pagata | Origini di traffico &gt; Cerca parola chiave - pagata |
|  | Parola chiave di ricerca - Naturale | Origini di traffico &gt; Cerca parola chiave - Naturale |
|  | Motori di ricerca - Tutti | Origini di traffico &gt; Motori di ricerca - Tutti |
|  | Motori di ricerca - Pagati | Origini di traffico &gt; Motori di ricerca - Pagati |
|  | Motori di ricerca - Naturale | Sorgenti Di Traffico &gt; Motori Di Ricerca - Naturale |
|  | Classificazione pagina di ricerca | Origini di traffico &gt; Classificazione di tutte le pagine di ricerca |
|  | Domini di riferimento | Origini di traffico &gt; Domini di riferimento |
|  | Domini di riferimento originali | Origini di traffico &gt; Domini di riferimento originali |
|  | Riferimenti | Origini di traffico &gt; Referenti |
|  | Tipi di referente | Origini di traffico &gt; Tipi di referente |
| **Campagne** |  |  |
|  | Funnel di conversione campagna | Origini di traffico &gt; Campagne &gt; Funnel di conversione campagna |
|  | Codice di tracciamento | Origini di traffico &gt; Campagne &gt; Codice di tracciamento |
| **Prodotti** |  |  |
|  | Funnel di conversione prodotti | Conversion &gt; Products &gt; Products Conversion Funnel |
|  | Prodotti | Conversione &gt; Prodotti &gt; Prodotti |
|  | Vendita incrociata | Conversione &gt; Prodotti &gt; Vendita incrociata |
|  | Categorie | Conversione &gt; Prodotti &gt; Categorie |
| **Conservazione dei visitatori** |  |  |
|  | Restituisci frequenza | Pubblico &gt; Mantenimento visitatori &gt; Frequenza di ritorno |
|  | Visite di ritorno | Pubblico &gt; Mantenimento visitatori &gt; Visite di ritorno |
|  | Visite giornaliere di ritorno | Pubblico &gt; Mantenimento visitatori &gt; Visite giornaliere di ritorno |
|  | Numero visita | Pubblico &gt; Mantenimento visitatori &gt; Numero visita |
|  | Ciclo di vendita | Pubblico &gt; Mantenimento visitatori &gt; Ciclo di vendita |
| **Profilo visitatore** |  |  |
|  | Geosegmentazione | Pubblico &gt; Profilo visitatore &gt; Geosegmentazione |
|  | Lingue | Pubblico &gt; Profilo visitatore &gt; Lingue |
|  | Fusi orari | Pubblico &gt; Profilo visitatore &gt; Fusi orari |
|  | Domains (Domini) | Pubblico &gt; Profilo visitatore &gt; Domini |
|  | Domini di livello principali | Pubblico &gt; Profilo visitatore &gt; Domini di primo livello |
|  | Tecnologia | Pubblico &gt; Profilo visitatore &gt; Tecnologia |
|  | Stato visitatore | Pubblico &gt; Profilo visitatore &gt; Stato visitatore |
|  | CAP visitatore | Pubblico &gt; Profilo visitatore &gt; Codice postale del visitatore |
| **Conversione personalizzata** |  |  |
|  | Conversione personalizzata 1-10 | Conversione &gt; Conversione personalizzata &gt; Conversione personalizzata 1-10 |
|  | Conversione personalizzata 11-20 | Conversione &gt; Conversione personalizzata &gt; Conversione personalizzata 11-20 |
| **Traffico personalizzato** |  |  |
|  | Traffico personalizzato 1-10 | Contenuto &gt; Traffico personalizzato &gt; Traffico personalizzato 1-10 |
| **Test&amp;Target** |  | Conversione &gt; Test&amp;Target |
| **Sondaggio** |  | Pubblico &gt; Sondaggio |
| **Canali marketing** |  |  |
|  | Report Panoramica canale | Origini di traffico &gt; Canali di marketing &gt; Rapporto Panoramica canale |
|  | Primo canale touch | Origini di traffico &gt; Canali di marketing &gt; Primo canale di contatto |
|  | Primo dettaglio canale touch | Origini di traffico &gt; Canali di marketing &gt; Primo dettaglio canale di contatto |
|  | Ultimo canale touch | Origini di traffico &gt; Canali di marketing &gt; Ultimo canale di contatto |
|  | Ultimo dettaglio canale touch | Origini di traffico &gt; Canali di marketing &gt; Ultimo canale di contatto |
| **App mobile** |  |  |
|  | Panoramica app mobile | Contenuto &gt; App mobile &gt; Panoramica app mobile |
|  | Rapporti sul ciclo di vita | Contenuto &gt; App mobile &gt; Rapporti sul ciclo di vita |
| **Report personalizzati** |  |  |
|  | I rapporti personalizzati vengono visualizzati solo da un utente con una configurazione specifica. | Report personalizzati |
|  |  |  |

