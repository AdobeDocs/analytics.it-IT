---
description: Impostazioni che definiscono il modo in cui vengono visualizzati tutti i rapporti e le informazioni che presentano le opzioni di menu predefinite nella posizione desiderata nel menu semplificato.
seo-description: Impostazioni che definiscono il modo in cui vengono visualizzati tutti i rapporti e le informazioni che presentano le opzioni di menu predefinite nella posizione desiderata nel menu semplificato.
seo-title: Impostazioni di visualizzazione e navigazione
solution: Analytics
title: Impostazioni di visualizzazione e navigazione
topic: Report, reporting e analisi
uuid: e 7 e 571 ce-a 1 cf -4714-b 400-9571805 ceeac
translation-type: tm+mt
source-git-commit: 612cbb694f16b5b4fcbf2d9cae55bc52103cc0b9

---


# Impostazioni di visualizzazione e navigazione

Impostazioni che definiscono il modo in cui vengono visualizzati tutti i rapporti e le informazioni che mappa le opzioni di menu predefinite nella posizione desiderata nel menu semplificato.

## Report display settings and navigation {#concept_09832A2CA0FF4982B1AA37C1B635220B}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Report Settings]**

<!--Meike, I replaced this table with one from https://marketing.adobe.com/resources/help/en_US/sc/user/report_settings.html -bob -->

| Elemento | Descrizione |
|--- |--- |
| **Impostazioni generali** |  |
| Includi sezione metriche correlate | Le metriche correlate sono correlate al rapporto che stai visualizzando (ad esempio, le cinque pagine principali nel report Visualizzazioni pagina). |
| Mostra media Internet nella sezione dei dettagli | Esprime il valore medio di una determinata statistica, eseguita su più migliaia di siti Web aziendali. Quando abilitata, questa sezione viene visualizzata come una colonna separata nel riepilogo dei report e nelle sezioni dei dettagli del rapporto. Questa funzione è utilizzata solo dai rapporti sul traffico nel gruppo tecnologico, oltre che sui motori di ricerca, le lingue e i rapporti sui domini. |
| Mostra la struttura del menu predefinita di Adobe | Ignora le impostazioni in Strumenti di amministrazione, in cui gli amministratori personalizzano i menu dei rapporti in modo da adattarli alle preferenze utente, rimandando il menu del rapporto alle impostazioni predefinite. |
| Forza le larghezze di colonna durante la visualizzazione dei rapporti | Forza le larghezze di colonna dei report a una coerenza esteticamente gradevole. Questa impostazione è utile quando sono visualizzate più di tre metriche. |
| **Grafici e grafici** |  |
| Evidenziazione dei fine settimana sui grafici di tendenza | Evidenzia in verticale le date fine dei grafici dei report con tendenze. I report con tendenze possono essere molto più facili da valutare quando vengono identificati i fine settimana. |
| Includi previsione nel grafico e nel riepilogo | Stima la quantità di statistica che si verifica in futuro. La previsione viene visualizzata nella sezione di riepilogo dei report quando abilitata. |
| Includere eventi calendario nei rapporti | Tiene traccia delle prestazioni del sito relative a eventi specifici. Quando sono attivati, questi eventi vengono visualizzati nei rapporti. |
| Usare i grafici Flash | Abilita i grafici Flash nei rapporti. I grafici Flash offrono immagini più nitide e interattive per i rapporti, ma non consentono di copiare o salvare facilmente le immagini. Per copiare o salvare le immagini rapidamente, disattivate questa opzione (le immagini saranno in formato. gif). Se deselezionate questa opzione, il pulsante del grafico Copia non viene visualizzato nella barra degli strumenti del rapporto. |
| Mostra i dati di tutti gli altri nei grafici selezionati | Visualizza tutti gli altri sotto le cinque cinque raggruppate in un singolo oggetto. (i grafici a barre mostrano le cinque pagine Web o altri dati all'interno del rapporto.) |
| Mostrare i dati "Nessuno", "Non specificato" e "Typed/Bookmarked" nei grafici dei report | Mostra le metriche in cui non è stato ricevuto alcun valore per la metrica specificata. |
| Mostra sparkline sui report classifica | Visualizza una sparkline nel campo dei totali dei report classifica. Questo fornisce una visualizzazione rapida della tendenza complessiva senza generare un rapporto separato. |
| **Accelerazione** |  |
| Abilitare Report Accelerator per visualizzare i rapporti più rapidamente | Abilita l'acceleratore del report, che utilizza un algoritmo basato sul tempo per memorizzare nella cache i report richiesti di recente e esamina solo gli elementi univoci che si verificano in modo più frequente, dando luogo a una distribuzione ancora più rapida dei report. Memorizzando nella cache i rapporti richiesti per 15 minuti, l'acceleratore di report può recuperare tali rapporti per le richieste successive quasi istantaneamente. Questa impostazione è utile per navigare avanti e indietro, per stampare i rapporti o per accedere spesso agli stessi rapporti. Se disattivato, il sistema rigenera i rapporti ogni volta che vengono richiesti. |
| Attivare l'acceleratore dashboard e visualizzare le versioni memorizzate nella cache | Abilita l'acceleratore dashboard, che memorizza una versione memorizzata nella cache del dashboard per la visualizzazione successiva. Grazie alla memorizzazione nella cache di una visualizzazione del dashboard per 24 ore, l'acceleratore dashboard è in grado di recuperare questa visualizzazione quasi istantaneamente, in quanto la query di database e l'elaborazione sono già in anticipo. Se la versione memorizzata nella cache è superiore a 24 ore, viene generata una nuova dashboard e viene creata una nuova versione memorizzata nella cache. Analogamente, una nuova versione memorizzata nella cache viene creata ogni volta che aggiornate il dashboard (o un qualsiasi minirapporto visualizzato nel dashboard). La cache è basata su utente. Altri utenti che visualizzano una dashboard condivisa visualizzano una versione in base al loro utilizzo del dashboard e all'aggiornamento del dashboard. |
| Attivazione dell'accelerazione di rete per migliorare le prestazioni dei rapporti | Consente di velocizzare la distribuzione dei dati nella posizione, ottimizzando il percorso tra l'infrastruttura Adobe e l'ambiente. |
| Attivazione dell'accelerazione regionale per un'esperienza utente più rapida in Cina | L'Acceleratore regionale utilizza domini con accelerazione specifici per regione, per fornire un'esperienza utente più veloce all'interno di un'area specifica. L'accelerazione attualmente regionale è supportata solo per la Cina. L'abilitazione di questa funzione per gli utenti che non si trovano in Cina darà luogo a un'esperienza utente più lenta. Dopo aver attivato l'accelerazione regionale, dovete effettuare nuovamente l'accesso affinché abbia un impatto. Se desiderate disattivare l'acceleratore regionale, deselezionate questa casella di controllo. |
| **Lingua/Valuta/Codifica** |  |
| Separatore migliaia | Selezionare un separatore ogni migliaia (decimale o virgola). Molti paesi usano un decimale per separare le migliaia. Questo separatore viene applicato a tutti i numeri del sistema, non solo alla valuta. |
| Utilizzo della valuta predefinita della suite di rapporti | Specifica se utilizzare la valuta predefinita della suite di rapporti. |
| Valuta | La valuta alla quale vuoi convertire i dati. Quando si seleziona un valore in questa impostazione, i dati memorizzati nel database non vengono modificati, ma vengono visualizzati come un valore convertito in base al tasso di conversione della valuta corrente. Quando le opzioni della valuta non sono configurate (impostazione predefinita), non viene eseguita alcuna conversione valuta e tutti i valori vengono memorizzati e visualizzati negli USD (USD). Per convertire la valuta durante l'elaborazione dei dati (prima che venga visualizzata), contatta il tuo responsabile commerciale. |
| Codifica report pianificata | MAIUSC-JIS per codifica caratteri giapponese. EUC-JP per codice Unix esteso, principalmente per giapponese, coreano e cinese semplificato. |
| Carattere separatore CSV | Il carattere che desiderate usare per separare i valori CSV. |

## Menu di navigazione {#concept_1525EE52F8094535B4240F03B70DD75D}

<!-- 

nav_menu.xml

 -->

Se si utilizza il menu predefinito, la tabella seguente semplifica l'individuazione delle opzioni del menu nel menu semplificato.

| Posizione nel menu predefinito | Posizione nel menu semplificato |
|---|---|
| **Metriche del sito** |  |  |
|  | Panoramica del sito | Metriche &gt; Panoramica sul sito |
|  | Metriche chiave | Metriche &gt; Metriche chiave |
|  | Visualizzazioni pagina | Metriche &gt; Visualizzazioni pagina |
|  | Visite | Metriche &gt; Visite |
|  | Visitatori | Metriche &gt; Visitatori |
|  | Tempo trascorso per visita | Metriche &gt; Tempo trascorso per visita |
|  | Tempo precedente all'evento | Conversione &gt; Tempo prima dell'evento |
|  | Acquisti | Metriche &gt; Acquisti |
|  | Carrello acquisti | Metriche &gt; Carrello acquisti |
|  | Eventi personalizzati | Metriche &gt; Eventi personalizzati |
|  | Bot | Pubblico &gt; Bots |
|  | Rilevamento delle anomalie | Metriche &gt; Rilevamento anomalie |
|  | Real-Time (Tempo reale) | Metriche &gt; Real-Time (Tempo reale) |
| **Contenuto del sito** |  |  |
|  | Pagine | Contenuto &gt; Pagine |
|  | Sezione sito | Contenuto &gt; Sezioni del sito |
|  | Server | Contenuto &gt; Server |
|  | Collegamenti | Navigazione &gt; Collegamenti personalizzati; Navigazione &gt; Esci da collegamenti; Navigazione &gt; clickmap; Navigazione &gt; Download file |
|  | Pagine non trovate | Navigazione &gt; Pagine non trovate |
| **Mobile** |  |  |
|  | Dispositivi | Pubblico &gt; Mobile &gt; Dispositivi |
|  | Tipo di dispositivo | Pubblico &gt; Mobile &gt; Tipo dispositivo |
|  | Produttore | Pubblico &gt; Mobile &gt; Produttore |
|  | Dimensioni schermo | Pubblico &gt; Mobile &gt; Dimensione schermo |
|  | Altezza schermo | Pubblico &gt; Mobile &gt; Altezza schermo |
|  | Larghezza schermo | Pubblico &gt; Mobile &gt; Larghezza schermo |
|  | Supporto cookie | Pubblico &gt; Mobile &gt; Supporto cookie |
|  | Supporto immagini | Pubblico &gt; Mobile &gt; Supporto immagini |
|  | Profondità colore | Pubblico &gt; Mobile &gt; Profondità colore |
|  | Supporto audio | Pubblico &gt; Mobile &gt; Supporto audio |
|  | Supporto video | Pubblico &gt; Mobile &gt; Supporto video |
|  | Versione | Pubblico &gt; Mobile &gt; Sistema operativo |
| **Paths (Percorsi)** |  |  |
|  | Pagine | Navigazione &gt; Percorsi &gt; Pagine |
|  | Termini di ricerca interni | Navigazione &gt; Percorsi &gt; Termini di ricerca interni |
| **Origini del traffico** |  |  |
|  | Cerca parola chiave - Tutto | Origini traffico &gt; Cerca parola chiave - Tutti |
|  | Parola chiave Cerca - Pagamento | Origini di traffico &gt; Cerca parola chiave - Paid |
|  | Ricerca parola chiave - Naturale | Origini di traffico &gt; Cerca parola chiave - Naturale |
|  | Motori di ricerca - Tutti | Origini traffico &gt; Motori di ricerca - Tutti |
|  | Motori di ricerca - Paid | Origini traffico &gt; Motori di ricerca - Paid |
|  | Motori di ricerca - Naturale | Origini traffico &gt; Motori di ricerca - Naturale |
|  | Classificazione pagina di ricerca | Origini di traffico &gt; Tutta la classificazione pagina di ricerca |
|  | Domini di riferimento | Origini traffico &gt; Domini di riferimento |
|  | Domini di riferimento originali | Origini traffico &gt; Domini di riferimento originali |
|  | Referenti | Origini traffico &gt; Referenti |
|  | Tipi di riferimenti | Origini traffico &gt; Tipi di riferimenti |
| **Campagne** |  |  |
|  | Funnel di conversione campagna | Origini di traffico &gt; Campagne &gt; Funnel di conversione campagna |
|  | Codice di tracciamento | Origini di traffico &gt; Campagne &gt; Codice di tracciamento |
| **Prodotti** |  |  |
|  | Funnel di conversione prodotti | Conversione &gt; Prodotti &gt; Funnel di conversione prodotti |
|  | Variabile   | Conversione &gt; Prodotti &gt; Prodotti |
|  | Cross-sell | Conversione &gt; Prodotti &gt; Cross Selling |
|  | Categorie | Conversione &gt; Prodotti &gt; Categorie |
| **Conservazione dei visitatori** |  |  |
|  | Restituisci frequenza | Pubblico &gt; Mantenimento visitatore &gt; Restituisci frequenza |
|  | Visite di ritorno | Pubblico &gt; Mantenimento visitatore &gt; Visita di ritorno |
|  | Visite giornaliere di ritorno | Pubblico &gt; Conservazione visitatore &gt; Visite giornaliere |
|  | Numero visita | Pubblico &gt; Mantenimento visitatore &gt; Numero visita |
|  | Ciclo di vendita | Pubblico &gt; Mantenimento visitatore &gt; Ciclo di vendita |
| **Profilo visitatore** |  |  |
|  | Geosegmentazione | Pubblico &gt; Profilo visitatore &gt; Geosegmentazione |
|  | Lingue | Pubblico &gt; Profilo visitatore &gt; Lingue |
|  | Fusi orari | Pubblico &gt; Profilo visitatore &gt; Fuso orario |
|  | Domains (Domini) | Pubblico &gt; Profilo visitatore &gt; Domini |
|  | Domini di livello principale | Pubblico &gt; Profilo visitatore &gt; Domini di livello principale |
|  | Tecnologia | Pubblico &gt; Profilo visitatore &gt; Tecnologia |
|  | Stato visitatore | Pubblico &gt; Profilo visitatore &gt; Stato visitatore |
|  | CAP/Codice postale | Pubblico &gt; Profilo visitatore &gt; CAP visitatore/CAP |
| **Conversione personalizzata** |  |  |
|  | Conversione personalizzata 1-10 | Conversione &gt; Conversione personalizzata &gt; Conversione personalizzata 1-10 |
|  | Conversione personalizzata 11-20 | Conversione &gt; Conversione personalizzata &gt; Conversione personalizzata 11-20 |
| ** Traffico personalizzato** |  |  |
|  | Traffico personalizzato 1-10 | Contenuto &gt; Custom Traffic &gt; Custom Traffic 1-10 |
| ** Test &amp; Target** |  | Conversione &gt; Test &amp; Target |
| **Sondaggio** |  | Pubblico &gt; Sondaggio |
| **Canali marketing** |  |  |
|  | Report Panoramica canale | Origini traffico &gt; Canali di marketing &gt; Rapporto panoramica canale |
|  | Primo canale touch | Origini traffico &gt; Canali marketing &gt; Primo canale touch |
|  | Primo dettaglio canale touch | Origini traffico &gt; Canali di marketing &gt; Dettagli sul primo canale touch |
|  | Ultimo canale touch | Origini traffico &gt; Canali di marketing &gt; Ultimo canale touch |
|  | Dettagli ultimo canale touch | Origini traffico &gt; Canali di marketing &gt; Ultimo dettaglio canale |
| **App mobile** |  |  |
|  | Panoramica app mobile | Contenuto &gt; App mobile &gt; Panoramica app mobile |
|  | Rapporti sul ciclo di vita | Contenuto &gt; App mobile &gt; Rapporti sul ciclo di vita |
| **Report personalizzati ** |  |  |
|  | I rapporti personalizzati sono disponibili solo per qualsiasi configurazione. | Report personalizzati |
|  |  |  |

