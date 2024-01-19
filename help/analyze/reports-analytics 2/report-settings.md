---
description: Impostazioni che definiscono la modalità di visualizzazione di tutti i rapporti e informazioni che mappano le opzioni di menu predefinite alla relativa posizione nel menu semplificato.
title: Impostazioni di visualizzazione e navigazione del rapporto
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 2c2d4d59-b189-42e0-887e-77dc7a48721a
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '1478'
ht-degree: 7%

---

# Impostazioni di visualizzazione e navigazione del rapporto

{{ra-eol}}

Impostazioni che definiscono la modalità di visualizzazione di tutti i rapporti e informazioni che mappano le opzioni di menu predefinite alla relativa posizione nel menu semplificato.

## Impostazioni di visualizzazione e navigazione del rapporto {#concept_09832A2CA0FF4982B1AA37C1B635220B}

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All Components]** > **[!UICONTROL Report settings]**

| Elemento | Descrizione |
|--- |--- |
| **Impostazioni generali** |  |
| Sezione Includi metriche correlate | Le metriche correlate sono strettamente correlate al rapporto che stai visualizzando (ad esempio, le prime cinque pagine del rapporto Visualizzazioni pagina). |
| Mostra media Internet nella sezione dei dettagli | Esprime il valore medio di una data statistica, rilevato su diverse migliaia di siti web aziendali. Quando questa opzione è attivata, questa sezione viene visualizzata come una colonna separata nelle sezioni riepilogo e dettagli report. Questa funzione viene utilizzata solo dai rapporti sul traffico nel gruppo di tecnologie, nonché dai rapporti sui motori di ricerca, sulle lingue e sui domini. |
| Mostra struttura di menu predefinita di Adobe | Ignora le impostazioni in Strumenti di amministrazione, in cui gli amministratori personalizzano i menu dei rapporti in base alle preferenze dell’utente, ripristinando le impostazioni predefinite del menu dei rapporti. |
| Forza la larghezza delle colonne durante la visualizzazione dei report | Forza le larghezze delle colonne dei rapporti a una coerenza esteticamente gradevole. Questa impostazione è utile quando vengono visualizzate più di tre metriche. |
| **Grafici e grafici** |  |
| Evidenzia i fine settimana nei grafici di tendenza | Evidenzia verticalmente le date del fine settimana dei grafici dei rapporti con tendenze. I rapporti con tendenze possono essere molto più facili da valutare quando vengono identificati i fine settimana. |
| Includi previsione in grafico e riepilogo | Stima quanto si verificherà una particolare statistica in futuro. Se abilitata, la previsione viene visualizzata nella sezione di riepilogo del rapporto. |
| Includi eventi calendario nei report | Tiene traccia delle prestazioni del sito relative a eventi specifici. Quando sono abilitati, questi eventi vengono visualizzati nei rapporti. |
| Utilizzare i grafici dei Flash | Abilita i grafici di Flash nei rapporti. I grafici di Flash forniscono immagini più nitide e interattive per i rapporti, ma non consentono di copiare o salvare facilmente le immagini. Per la funzionalità di copia o salvataggio rapido delle immagini, disattiva questa opzione (le immagini saranno in formato .gif). Se deselezioni questa opzione, il pulsante Copia grafico non viene visualizzato nella barra degli strumenti del rapporto. |
| Mostra dati &quot;Tutti gli altri&quot; nei grafici selezionati | Visualizza tutti gli altri sotto i primi cinque raggruppati in un singolo oggetto. I grafici a barre mostrano le prime cinque pagine web o altri dati all’interno del rapporto. |
| Mostra dati &quot;None&quot;, &quot;Unspecified&quot; e &quot;Typed/Bookmarked&quot; (Nessuno) nei grafici dei rapporti | Mostra le metriche per le quali nessun valore ha ricevuto credito per la metrica specificata. |
| Mostra grafici sparkline nei report classificati | Visualizza un grafico sparkline nel campo dei totali dei rapporti classificati. In questo modo viene fornita una visualizzazione rapida della tendenza generale, senza generare un rapporto separato. |
| **Accelerazione** |  |
| Abilitare Report Accelerator per visualizzare più rapidamente i rapporti | Abilita l’acceleratore di report, che utilizza un algoritmo basato sul tempo per memorizzare in cache i rapporti richiesti di recente ed esamina solo gli elementi univoci che si verificano più frequentemente, consentendo una distribuzione ancora più rapida dei rapporti. Memorizzando nella cache i rapporti richiesti per 15 minuti, l’acceleratore di rapporti può recuperarli per le richieste successive quasi istantaneamente. Questa impostazione è utile quando si naviga avanti e indietro, si stampano i report o si accede frequentemente agli stessi report. Se l’opzione è disattivata, il sistema rigenera i rapporti ogni volta che vengono richiesti. |
| Abilita Dashboard Accelerator e visualizza le versioni memorizzate nella cache disponibili | Abilita l&#39;acceleratore del dashboard, che memorizza una versione memorizzata nella cache del dashboard per la visualizzazione successiva. Memorizzando nella cache una vista del dashboard per 24 ore, l’acceleratore del dashboard è in grado di recuperarla quasi istantaneamente, perché le operazioni intensive di query ed elaborazione del database vengono eseguite in anticipo. Se la versione cache disponibile risale a più di 24 ore fa, viene generato un nuovo dashboard e viene creata una nuova versione cache. Allo stesso modo, viene creata una nuova versione cache ogni volta che si aggiorna la dashboard (o qualsiasi reportlet visualizzato nella dashboard). La cache è basata sull&#39;utente. Gli altri utenti che visualizzano un dashboard condiviso visualizzano una versione basata sull’utilizzo dell’acceleratore del dashboard e sull’aggiornamento del dashboard. |
| Attiva accelerazione di rete per migliorare le prestazioni del rapporto | Accelera la distribuzione dei dati nella posizione desiderata ottimizzando il percorso tra l&#39;infrastruttura Adobe e l&#39;ambiente. |
| Accelerazione regionale per un&#39;esperienza utente più rapida in Cina | L’acceleratore regionale utilizza domini accelerati specifici per regione, per fornire un’esperienza utente più rapida all’interno di una regione specifica. Attualmente l&#39;accelerazione regionale è sostenuta solo per la Cina. Se abiliti questa funzione per gli utenti non residenti in Cina, l’esperienza utente risulterà più lenta. Dopo aver abilitato l’accelerazione regionale, devi effettuare di nuovo l’accesso affinché l’impostazione abbia un impatto. Se si desidera disattivare l&#39;acceleratore regionale, deselezionare questa casella di controllo. |
| **Lingua/valuta/codifica** |  |
| Separatore migliaia | Seleziona un separatore per ogni migliaia (decimale o virgola). Molti paesi utilizzano un decimale per separare il numero delle migliaia. Questo separatore viene applicato a tutti i numeri nel sistema, non solo alla valuta. |
| Utilizzare la valuta predefinita della suite di rapporti | Specifica se utilizzare la valuta predefinita della suite di rapporti. |
| Valuta | Valuta in cui si desidera convertire i dati. Quando si seleziona un valore in questa impostazione, i dati memorizzati nel database non vengono interessati, ma vengono visualizzati come valori convertiti in base al tasso di conversione della valuta del giorno corrente. Quando le opzioni di valuta non sono configurate (impostate sui valori predefiniti) non viene eseguita alcuna conversione di valuta e tutti i valori vengono memorizzati e visualizzati in dollari USA (USD). Per convertire la valuta quando i dati vengono elaborati (prima che vengano visualizzati), contatta il team dell’account di Adobe. |
| Codifica report pianificata | SHIFT-JIS per la codifica di caratteri giapponese. EUC-JP per codice Unix esteso, principalmente per giapponese, coreano e cinese semplificato. |
| Carattere separatore CSV | Carattere da utilizzare per separare i valori CSV. |

## Menu di navigazione {#concept_1525EE52F8094535B4240F03B70DD75D}

<!-- 

nav_menu.xml

 -->

Se si è abituati al menu di default, la tabella riportata di seguito semplifica la ricerca delle opzioni di menu nel menu semplificato.

| Posizione nel menu predefinito | Posizione nel menu semplificato |
|---|---|
| **Metriche del sito** |  |  |
|   | Panoramica del sito | Metriche > Panoramica sito |
|   | Metriche chiave | Metriche > Metriche chiave |
|   | Visualizzazioni pagina | Metriche > Visualizzazioni pagina |
|   | Visite | Metriche > Visite |
|   | Visitatori | Metriche > Visitatori |
|   | Tempo trascorso per visita | Metriche > Tempo trascorso per visita |
|   | Tempo precedente all’evento | Conversione > Tempo precedente all’evento |
|   | Acquisti | Metriche > Acquisti |
|   | Carrello | Metriche > Carrello |
|   | Eventi personalizzati | Metriche > Eventi personalizzati |
|   | Bot | Pubblico > Bot |
|   | Rilevamento delle anomalie | Metriche > Rilevamento delle anomalie |
|   | Tempo reale | Metriche > Tempo reale |
| **Contenuto del sito** |  |  |
|   | Pagine | Contenuto > Pagine |
|   | Sezione sito | Contenuto > Sezioni del sito |
|   | Server | Contenuto > Server |
|   | Collegamenti | Navigazione > Collegamenti personalizzati; Navigazione > Collegamenti di uscita; Navigazione > ClickMap; Navigazione > Download dei file |
|   | Pagine non trovate | Navigazione > Pagine non trovate |
| **Mobile** |  |  |
|   | Dispositivi | Pubblico > Mobile > Dispositivi |
|   | Tipo di dispositivo | Pubblico > Mobile > Tipo di dispositivo |
|   | Produttore | Pubblico > Mobile > Produttore |
|   | Dimensioni dello schermo | Pubblico > Mobile > Dimensioni schermo |
|   | Altezza schermo | Pubblico > Mobile > Altezza schermo |
|   | Larghezza schermo | Pubblico > Mobile > Larghezza schermo |
|   | Supporto per cookie | Pubblico > Mobile > Supporto per cookie |
|   | Supporto immagini | Pubblico > Mobile > Supporto immagini |
|   | Profondità colore | Pubblico > Mobile > Profondità colore |
|   | Supporto audio | Pubblico > Mobile > Supporto audio |
|   | Supporto video | Pubblico > Mobile > Supporto video |
|   | Sistema operativo | Pubblico > Mobile > Sistema operativo |
| **Paths (Percorsi)** |  |  |
|   | Pagine | Navigazione > Percorsi > Pagine |
|   | Termini di ricerca interni | Navigazione > Percorsi > Termini di ricerca interni |
| **Origini del traffico** |  |  |
|   | Parola chiave di ricerca - Tutto | Origini traffico > Parola chiave di ricerca - Tutto |
|   | Parola chiave di ricerca - A pagamento | Origini traffico > Parola chiave di ricerca - A pagamento |
|   | Parola chiave di ricerca - Naturale | Origini traffico > Parola chiave di ricerca - Naturale |
|   | Motori di ricerca - Tutti | Origini traffico > Motori di ricerca - Tutto |
|   | Motori di ricerca - A pagamento | Origini traffico > Motori di ricerca - A pagamento |
|   | Motori di ricerca - Naturale | Origini traffico > Motori di ricerca - Naturale |
|   | Classificazione di tutte le pagine di ricerca | Traffic Sources (Origini traffico) > All Search Page Ranking (Classificazione di tutte le pagine di ricerca) |
|   | Domini di riferimento | Origini traffico > Domini di riferimento |
|   | Domini di riferimento originali | Origini traffico > Domini di riferimento originali |
|   | Riferimenti | Origini traffico > Riferimenti |
|   | Tipi di referrer | Origini traffico > Tipi di referrer |
| **Campagne** |  |  |
|   | Funnel di conversione campagna | Origini traffico > Campagne > Funnel di conversione campagna |
|   | Codice di tracciamento | Origini traffico > Campagne > Codice di tracciamento |
| **Prodotti** |  |  |
|   | Funnel di conversione prodotti | Conversione > Prodotti > Funnel di conversione prodotti |
|   | Prodotti | Conversione > Prodotti > Prodotti |
|   | Cross-selling | Conversione > Prodotti > Cross-selling |
|   | Categorie | Conversione > Prodotti > Categorie |
| **Conservazione dei visitatori** |  |  |
|   | Frequenza di ritorno | Pubblico > Conservazione dei visitatori > Frequenza di ritorno |
|   | Visite di ritorno | Pubblico > Conservazione dei visitatori > Visite di ritorno |
|   | Visite giornaliere di ritorno | Pubblico > Conservazione dei visitatori > Visite giornaliere di ritorno |
|   | Numero di visite | Pubblico > Conservazione dei visitatori > Numero di visite |
|   | Ciclo di vendita | Pubblico > Conservazione dei visitatori > Ciclo di vendita |
| **Profilo visitatore** |  |  |
|   | Geosegmentazione | Pubblico > Profilo visitatore > GeoSegmentation |
|   | Lingue | Pubblico > Profilo visitatore > Lingue |
|   | Fusi orari | Pubblico > Profilo visitatore > Fusi orari |
|   | Domini | Pubblico > Profilo visitatore > Domini |
|   | Domini di primo livello | Pubblico > Profilo visitatore > Domini di primo livello |
|   | Tecnologia | Pubblico > Profilo visitatore > Tecnologia |
|   | Stato visitatore | Pubblico > Profilo visitatore > Stato visitatore |
|   | CAP visitatore | Pubblico > Profilo visitatore > CAP visitatore |
| **Conversione personalizzata** |  |  |
|   | Conversione personalizzata 1-10 | Conversione > Conversione personalizzata > Conversione personalizzata 1-10 |
|   | Conversione personalizzata 11-20 | Conversione > Conversione personalizzata > Conversione personalizzata 11-20 |
| **Traffico personalizzato** |  |  |
|   | Traffico personalizzato 1-10 | Contenuto > Traffico personalizzato > Traffico personalizzato 1-10 |
| **Test&amp;Target** |  | Conversione > Test&amp;Target |
| **Sondaggio** |  | Pubblico > Sondaggio |
| **Canali marketing** |  |  |
|   | Rapporto panoramica canale | Origini traffico > Canali di marketing > Rapporto panoramica canale |
|   | Canale di primo contatto | Origini di traffico > Canali di marketing > Canale primo contatto |
|   | Dettaglio canale di primo contatto | Origini del traffico > Canali di marketing > Dettagli canale di primo contatto |
|   | Canale ultimo contatto | Origini traffico > Canali marketing > Canale ultimo contatto |
|   | Dettaglio canale ultimo contatto | Origini traffico > Canali di marketing > Dettagli canale di ultimo contatto |
| **App mobile** |  |  |
|   | Panoramica dell’app mobile | Contenuto > App mobile > Panoramica app mobile |
|   | Rapporti sul ciclo di vita | Contenuto > App mobile > Rapporti sul ciclo di vita |
| **Rapporti personalizzati** |  |  |
|   | I rapporti personalizzati vengono visualizzati solo se hai configurato qualcosa. | Rapporti personalizzati |
|   |  |  |
