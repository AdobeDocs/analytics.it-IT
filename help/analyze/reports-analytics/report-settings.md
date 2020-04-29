---
description: Impostazioni che definiscono l’aspetto di tutti i rapporti e le informazioni che mappano le opzioni di menu predefinite alla loro posizione nel menu semplificato.
title: Impostazioni di visualizzazione e navigazione del rapporto
topic: Reports,Reports and analytics
uuid: e7e571ce-a1cf-4714-b400-9571805ceeac
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Impostazioni di visualizzazione e navigazione del rapporto

Impostazioni che definiscono l’aspetto di tutti i rapporti e le informazioni che associano le opzioni di menu predefinite alla loro posizione nel menu semplificato.

## Impostazioni di visualizzazione e navigazione del rapporto {#concept_09832A2CA0FF4982B1AA37C1B635220B}

**[!UICONTROL Analytics]** (Workspace) > **[!UICONTROL Components]** (Progetto) > **[!UICONTROL Report Settings]** (Annulla/Ripeti)

| Elemento | Descrizione |
|--- |--- |
| **Impostazioni generali** |  |
| Includi sezione metriche correlate | Le metriche correlate sono strettamente correlate al rapporto che stai visualizzando (ad esempio, le prime cinque pagine del rapporto visualizzazioni pagina). |
| Mostra media Internet nella sezione dei dettagli | Esprime il valore medio di una determinata statistica, realizzata su diverse migliaia di siti web aziendali. Quando abilitata, questa sezione viene visualizzata come una colonna separata nelle sezioni del riepilogo del rapporto e dei dettagli del rapporto. Questa funzione è utilizzata solo dai report sul traffico nel gruppo tecnologico, nonché dai report sui motori di ricerca, sulle lingue e sui domini. |
| Mostra struttura menu predefinita di Adobe | Ignora le impostazioni in Strumenti di amministrazione, in cui gli amministratori personalizzano i menu dei rapporti in base alle preferenze degli utenti, e di nuovo il menu del rapporto alle impostazioni predefinite. |
| Forza la larghezza delle colonne durante la visualizzazione dei rapporti | Forza la larghezza delle colonne del report a una coerenza esteticamente gradevole. Questa impostazione è utile quando vengono visualizzate più di tre metriche. |
| **Grafici e grafici** |  |
| Evidenzia i fine settimana sui grafici di tendenza | Evidenzia verticalmente le date di fine settimana dei grafici con tendenze dei report. I report con tendenze possono essere molto più facili da valutare quando i fine settimana sono identificati. |
| Includi previsione nel grafico e nel riepilogo | Stima quanto si verificherà in futuro una particolare statistica. La previsione viene visualizzata nella sezione di riepilogo del rapporto quando abilitata. |
| Includi eventi calendario nei rapporti | Monitora le prestazioni del sito rispetto a eventi specifici. Quando attivato, questi eventi vengono visualizzati nei rapporti. |
| Utilizzare i grafici Flash | Abilita grafici Flash nei rapporti. I grafici Flash forniscono immagini più nitide e interattive per i rapporti, ma non consentono di copiare o salvare facilmente le immagini. Per una rapida funzionalità di copia o salvataggio delle immagini, disattivate questa opzione (le immagini saranno in formato .gif). Se deselezionate questa opzione, il pulsante Copia grafico non viene visualizzato nella barra degli strumenti del rapporto. |
| Mostra tutti gli altri dati nei grafici selezionati | Visualizza tutti gli altri sotto i primi cinque raggruppati in un singolo oggetto. (I grafici a barre mostrano le prime cinque pagine Web o altri dati presenti nel rapporto.) |
| Mostra i dati &quot;None&quot;, &quot;Unspecified&quot; e &quot;Typed/Bookmarked&quot; nei grafici dei rapporti | Mostra le metriche in cui nessun valore ha ricevuto credito per la metrica specificata. |
| Mostra sparkline nei report classifica | Visualizza un grafico sparkline nel campo dei totali dei report classifica. Questo fornisce una panoramica rapida della tendenza complessiva senza generare un rapporto separato. |
| **Accelerazione** |  |
| Abilita acceleratore report per visualizzare i report più rapidamente | Abilita l&#39;acceleratore di report, che utilizza un algoritmo basato sul tempo per memorizzare nella cache i report richiesti di recente ed esamina solo gli elementi univoci che si verificano più di frequente, con conseguente consegna ancora più rapida dei report. Memorizzando nella cache i report richiesti per 15 minuti, l&#39;acceleratore di report può recuperare tali report per richieste successive quasi immediatamente. Questa impostazione è utile per spostarsi avanti e indietro, stampare rapporti o per accedere frequentemente agli stessi rapporti. Se disabilitato, il sistema rigenera i rapporti ogni volta che vengono richiesti. |
| Abilita dashboard Accelerator e visualizza le versioni disponibili nella cache | Abilita l’acceleratore del dashboard, che memorizza una versione memorizzata nella cache del dashboard per la visualizzazione successiva. Memorizzando nella cache una vista del dashboard per 24 ore, l&#39;acceleratore del dashboard è in grado di recuperare la visualizzazione quasi istantaneamente perché l&#39;esecuzione intensiva di query e elaborazione del database avviene in anticipo. Se la versione disponibile nella cache ha più di 24 ore, viene generato un nuovo dashboard e viene creata una nuova versione memorizzata nella cache. Analogamente, viene creata una nuova versione memorizzata nella cache ogni volta che aggiornate il dashboard (o qualsiasi altro minirapporto visualizzato sul dashboard). La cache è basata sull&#39;utente. Altri utenti che visualizzano un dashboard condiviso visualizzano una versione basata sul proprio utilizzo dell&#39;acceleratore del dashboard e sull&#39;aggiornamento del dashboard. |
| Abilitare l&#39;accelerazione di rete per migliorare le prestazioni dei report | Velocizza la distribuzione dei dati nella posizione dell&#39;utente ottimizzando il percorso tra l&#39;infrastruttura Adobe e l&#39;ambiente. |
| Abilitare l&#39;accelerazione regionale per un&#39;esperienza utente più rapida in Cina | L&#39;Acceleratore regionale utilizza domini con accelerazione specifici per regione, per fornire un&#39;esperienza utente più rapida all&#39;interno di un&#39;area specifica. Attualmente l&#39;accelerazione regionale è supportata solo dalla Cina. Abilitando questa funzione per gli utenti che non si trovano in Cina l’esperienza utente risulterà più lenta. Dopo aver attivato l&#39;accelerazione regionale, è necessario eseguire di nuovo l&#39;accesso affinché l&#39;impostazione abbia un impatto. Se si desidera disattivare l&#39;acceleratore regionale, deselezionare questa casella di controllo. |
| **Lingua/Valuta/Codifica** |  |
| Separatore migliaia | Selezionare un separatore ogni migliaia (decimale o virgola). Molti paesi utilizzano un decimale per separare il numero delle migliaia. (Questo separatore viene applicato a tutti i numeri all&#39;interno del sistema, non solo alla valuta.) |
| Usa la valuta predefinita della suite di rapporti | Specifica se utilizzare la valuta predefinita della suite di rapporti. |
| Valuta | La valuta in cui si desidera convertire i dati. Quando un valore è selezionato in questa impostazione, i dati memorizzati nel database non vengono modificati, ma vengono visualizzati come un valore convertito in base al tasso di conversione della valuta del giorno corrente. Quando le opzioni di valuta non sono configurate (impostate sulle impostazioni predefinite) non viene eseguita alcuna conversione di valuta, e tutti i valori vengono memorizzati e visualizzati in dollari statunitensi (USD). Per convertire la valuta quando i dati vengono elaborati (prima che vengano visualizzati), contattare il responsabile commerciale di riferimento. |
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
|  | Panoramica del sito | Metriche > Panoramica del sito |
|  | Metriche chiave | Metriche > Metriche chiave |
|  | Visualizzazioni pagina | Metriche > Visualizzazioni pagina |
|  | Visite | Metriche > Visite |
|  | Visitatori | Metriche > Visitatori |
|  | Tempo trascorso per ciascuna visita | Metriche > Tempo trascorso per visita |
|  | Tempo precedente all&#39;evento | Conversione > Tempo precedente all&#39;evento |
|  | Acquisti | Metriche > Acquisti |
|  | Carrello | Metriche > Carrello acquisti |
|  | Eventi personalizzati | Metriche > Eventi personalizzati |
|  | Bot | Pubblico > Bots |
|  | Rilevamento delle anomalie | Metriche > Rilevamento delle anomalie |
|  | Real-Time (Tempo reale) | Metriche > Real-Time |
| **Contenuto del sito** |  |  |
|  | Pagine | Contenuto > Pagine |
|  | Sezione sito | Contenuto > Sezioni del sito |
|  | Server | Contenuto > Server |
|  | Collegamenti | Navigazione > Collegamenti personalizzati; Navigazione > Collegamenti di uscita; Navigazione > ClickMap; Navigazione > Download di file |
|  | Pagine non trovate | Navigazione > Pagine non trovate |
| **Mobile** |  |  |
|  | Dispositivi | Pubblico > Mobile > Dispositivi |
|  | Tipo di dispositivo | Pubblico > Mobile > Tipo di dispositivo |
|  | Produttore | Pubblico > Mobile > Produttore |
|  | Dimensioni dello schermo del dispositivo | Pubblico > Mobile > Dimensione schermo |
|  | Altezza schermo | Pubblico > Mobile > Altezza schermo |
|  | Larghezza schermo | Pubblico > Mobile > Larghezza schermo |
|  | Supporto per cookie | Pubblico > Mobile > Supporto dei cookie |
|  | Supporto immagini | Pubblico > Mobile > Supporto immagini |
|  | Profondità colore | Pubblico > Mobile > Profondità colore |
|  | Supporto audio | Pubblico > Mobile > Supporto audio |
|  | Supporto video | Pubblico > Mobile > Supporto video |
|  | Sistema operativo | Pubblico > Mobile > Sistema operativo |
| **Paths (Percorsi)** |  |  |
|  | Pagine | Navigazione > Percorsi > Pagine |
|  | Termini di ricerca interni | Navigazione > Percorsi > Termini di ricerca interni |
| **Origini del traffico** |  |  |
|  | Cerca parola chiave - Tutto | Origini di traffico > Cerca parola chiave - Tutto |
|  | Parola chiave di ricerca - pagata | Origini di traffico > Cerca parola chiave - pagata |
|  | Parola chiave di ricerca - Naturale | Origini di traffico > Cerca parola chiave - Naturale |
|  | Motori di ricerca - Tutti | Origini di traffico > Motori di ricerca - Tutti |
|  | Motori di ricerca - Pagati | Origini di traffico > Motori di ricerca - Pagati |
|  | Motori di ricerca - Naturale | Sorgenti Di Traffico > Motori Di Ricerca - Naturale |
|  | Classifica per tutte le pagine di ricerca | Origini di traffico > Classificazione di tutte le pagine di ricerca |
|  | Domini di riferimento | Origini di traffico > Domini di riferimento |
|  | Domini di riferimento originali | Origini di traffico > Domini di riferimento originali |
|  | Riferimenti | Origini di traffico > Referenti |
|  | Tipi di referente | Origini di traffico > Tipi di referente |
| **Campagne** |  |  |
|  | Funnel di conversione campagna | Origini di traffico > Campagne > Funnel di conversione campagna |
|  | Codice di tracciamento | Origini di traffico > Campagne > Codice di tracciamento |
| **Prodotti** |  |  |
|  | Funnel di conversione prodotti | Conversion > Products > Products Conversion Funnel |
|  | Prodotti | Conversione > Prodotti > Prodotti |
|  | Vendita incrociata | Conversione > Prodotti > Vendita incrociata |
|  | Categorie | Conversione > Prodotti > Categorie |
| **Conservazione dei visitatori** |  |  |
|  | Restituisci frequenza | Pubblico > Mantenimento visitatori > Frequenza di ritorno |
|  | Visite di ritorno | Pubblico > Mantenimento visitatori > Visite di ritorno |
|  | Visite giornaliere di ritorno | Pubblico > Mantenimento visitatori > Visite giornaliere di ritorno |
|  | Numero visita | Pubblico > Mantenimento visitatori > Numero visita |
|  | Ciclo di vendita | Pubblico > Mantenimento visitatori > Ciclo di vendita |
| **Profilo visitatore** |  |  |
|  | Geosegmentazione | Pubblico > Profilo visitatore > Geosegmentazione |
|  | Lingue | Pubblico > Profilo visitatore > Lingue |
|  | Fusi orari | Pubblico > Profilo visitatore > Fusi orari |
|  | Domains (Domini) | Pubblico > Profilo visitatore > Domini |
|  | Domini di livello principali | Pubblico > Profilo visitatore > Domini di primo livello |
|  | Tecnologia | Pubblico > Profilo visitatore > Tecnologia |
|  | Stato visitatore | Pubblico > Profilo visitatore > Stato visitatore |
|  | Codice postale del visitatore | Pubblico > Profilo visitatore > Codice postale del visitatore |
| **Conversione personalizzata** |  |  |
|  | Conversione personalizzata 1-10 | Conversione > Conversione personalizzata > Conversione personalizzata 1-10 |
|  | Conversione personalizzata 11-20 | Conversione > Conversione personalizzata > Conversione personalizzata 11-20 |
| **Traffico personalizzato** |  |  |
|  | Traffico personalizzato 1-10 | Contenuto > Traffico personalizzato > Traffico personalizzato 1-10 |
| **Test&amp;Target** |  | Conversione > Test&amp;Target |
| **Sondaggio** |  | Pubblico > Sondaggio |
| **Canali marketing** |  |  |
|  | Report Panoramica canale | Origini di traffico > Canali di marketing > Rapporto Panoramica canale |
|  | Primo canale touch | Origini di traffico > Canali di marketing > Primo canale di contatto |
|  | Primo dettaglio canale touch | Origini di traffico > Canali di marketing > Primo dettaglio canale di contatto |
|  | Ultimo canale touch | Origini di traffico > Canali di marketing > Ultimo canale di contatto |
|  | Ultimo dettaglio canale touch | Origini di traffico > Canali di marketing > Ultimo canale di contatto |
| **App mobile** |  |  |
|  | Panoramica dell’app mobile | Contenuto > App mobile > Panoramica app mobile |
|  | Rapporti sul ciclo di vita | Contenuto > App mobile > Rapporti sul ciclo di vita |
| **Report personalizzati** |  |  |
|  | I rapporti personalizzati vengono visualizzati solo da un utente con una configurazione specifica. | Report personalizzati |
|  |  |  |

