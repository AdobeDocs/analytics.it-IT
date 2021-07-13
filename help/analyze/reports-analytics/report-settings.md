---
description: Impostazioni che definiscono la modalità di visualizzazione di tutti i rapporti e informazioni che mappano le opzioni di menu predefinite alla loro posizione nel menu semplificato.
title: Impostazioni di visualizzazione e navigazione del rapporto
uuid: e7e571ce-a1cf-4714-b400-9571805ceeac
role: User, Admin
exl-id: 2c2d4d59-b189-42e0-887e-77dc7a48721a
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '1464'
ht-degree: 9%

---

# Impostazioni di visualizzazione e navigazione del rapporto

Impostazioni che definiscono la modalità di visualizzazione di tutti i rapporti e informazioni che mappano le opzioni di menu predefinite alla loro posizione nel menu semplificato.

## Impostazioni di visualizzazione e navigazione del rapporto {#concept_09832A2CA0FF4982B1AA37C1B635220B}

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL All Components]** > **[!UICONTROL Report settings]**

| Elemento | Descrizione |
|--- |--- |
| **Impostazioni generali** |  |
| Includi sezione metriche correlate | Le metriche correlate sono strettamente correlate al rapporto che stai visualizzando (ad esempio, le prime cinque pagine del rapporto visualizzazioni pagina). |
| Mostra media Internet nella sezione dei dettagli | Esprime il valore medio di una data statistica, scattata su diverse migliaia di siti web aziendali. Quando abilitata, questa sezione viene visualizzata come una colonna separata nelle sezioni di riepilogo dei rapporti e dei dettagli dei rapporti . Questa funzione è utilizzata solo dai rapporti sul traffico nel gruppo tecnologico, nonché dai rapporti sui motori di ricerca, sulle lingue e sui domini. |
| Mostra struttura menu predefinita di Adobe | Ignora le impostazioni in Strumenti di amministrazione, in cui gli amministratori personalizzano i menu dei rapporti in base alle preferenze degli utenti, restituendo il menu del rapporto alle impostazioni predefinite. |
| Forza la larghezza delle colonne durante la visualizzazione dei rapporti | Forza la larghezza delle colonne del report a una coerenza esteticamente piacevole. Questa impostazione è utile quando vengono visualizzate più di tre metriche. |
| **Grafici e grafici** |  |
| Evidenziare i fine settimana sui grafici di tendenza | Evidenzia verticalmente le date del fine settimana dei grafici dei rapporti con tendenze. I rapporti con tendenze possono essere molto più facili da valutare quando vengono identificati i fine settimana. |
| Includi previsione nel grafico e nel riepilogo | Stima di quanto si verificherà in futuro una particolare statistica. La previsione viene visualizzata nella sezione di riepilogo del rapporto quando abilitata. |
| Includere eventi calendario nei rapporti | Tiene traccia delle prestazioni del sito rispetto a eventi specifici. Quando abilitato, questi eventi vengono visualizzati sui rapporti. |
| Utilizzare i grafici dei Flash | Abilita grafici Flash nei rapporti. I grafici a Flash forniscono immagini più nitide e interattive per i rapporti, ma non consentono di copiare o salvare facilmente le immagini. Per una rapida funzionalità di copia o salvataggio delle immagini, disattiva questa opzione (le immagini saranno in formato .gif). Se deselezioni questa opzione, il pulsante Copia grafico non viene visualizzato nella barra degli strumenti del rapporto. |
| Mostra i dati &quot;Tutti gli altri&quot; nei grafici selezionati | Visualizza tutti gli altri sotto i primi cinque raggruppati in un singolo oggetto. (I grafici a barre mostrano le cinque pagine web principali o altri dati presenti nel rapporto.) |
| Mostra i dati &quot;Nessuno&quot;, &quot;Non specificato&quot; e &quot;Digitato/Segnalibro&quot; nei grafici dei rapporti | Mostra le metriche in cui non è stato ricevuto alcun valore dal credito per la metrica specificata. |
| Mostra grafici sparkline nei report classifica | Visualizza un grafico sparkline nel campo dei totali dei rapporti classificati. Questo fornisce una rapida vista della tendenza generale senza generare un rapporto separato. |
| **Accelerazione** |  |
| Attiva Report Accelerator per visualizzare i report più rapidamente | Abilita l’acceleratore di report, che utilizza un algoritmo basato sul tempo per memorizzare in cache i report richiesti di recente e esamina solo gli elementi univoci più frequenti, con conseguente consegna ancora più rapida dei report. Memorizzando nella cache i rapporti richiesti per 15 minuti, l’acceleratore di report può recuperare quei rapporti per le richieste successive quasi istantaneamente. Questa impostazione è utile quando si naviga avanti e indietro, si stampano i rapporti o si accede frequentemente agli stessi rapporti. Se disabilitata, i rapporti vengono rigenerati ogni volta che vengono richiesti. |
| Abilita Dashboard Accelerator e visualizza le versioni disponibili nella cache | Abilita l&#39;acceleratore del dashboard, che memorizza una versione cache del dashboard per la visualizzazione successiva. Memorizzando in cache una vista del dashboard per 24 ore, l&#39;acceleratore del dashboard è in grado di recuperare tale visualizzazione quasi istantaneamente perché l&#39;intensa attività di query ed elaborazione del database viene eseguita in anticipo. Se la versione cache disponibile ha più di 24 ore, viene generato un nuovo dashboard e viene creata una nuova versione cache. Allo stesso modo, viene creata una nuova versione cache ogni volta che aggiorni il dashboard (o qualsiasi minirapporti visualizzato sul dashboard). La cache è basata sull’utente. Altri utenti che visualizzano una dashboard condivisa visualizzano una versione basata sul proprio utilizzo dell&#39;acceleratore della dashboard e sull&#39;aggiornamento della dashboard. |
| Abilita l&#39;accelerazione di rete per migliorare le prestazioni dei rapporti | Consente di velocizzare la distribuzione dei dati nella posizione ottimizzando il percorso tra l’infrastruttura Adobe e l’ambiente. |
| Attiva l&#39;accelerazione regionale per un&#39;esperienza utente più rapida in Cina | L&#39;Acceleratore regionale utilizza domini accelerati specifici per l&#39;area geografica, per fornire un&#39;esperienza utente più rapida all&#39;interno di una regione specifica. Attualmente l&#39;accelerazione regionale è sostenuta solo dalla Cina. Se abiliti questa funzione per gli utenti che non si trovano in Cina, l’esperienza utente risulterà più lenta. Dopo aver abilitato l’accelerazione regionale, è necessario accedere nuovamente per avere un impatto sull’impostazione. Se si desidera disattivare l&#39;Acceleratore regionale, deselezionare questa casella di controllo. |
| **Lingua/Valuta/Codifica** |  |
| Separatore delle migliaia | Selezionare un separatore per ogni migliaia (decimale o virgola). Molti paesi utilizzano un decimale per separare il numero di migliaia. (Questo separatore viene applicato a tutti i numeri in tutto il sistema, non solo alla valuta.) |
| Utilizza la valuta predefinita della suite di rapporti | Specifica se utilizzare la valuta predefinita della suite di rapporti. |
| Valuta | La valuta in cui si desidera convertire i dati. Quando in questa impostazione viene selezionato un valore, i dati memorizzati nel database non vengono interessati, ma vengono visualizzati come valore convertito in base al tasso di conversione della valuta del giorno corrente. Quando le opzioni di valuta non sono configurate (impostate sulle impostazioni predefinite) non si verifica alcuna conversione di valuta e tutti i valori vengono memorizzati e visualizzati in dollari statunitensi (USD). Per convertire la valuta quando i dati vengono elaborati (prima della visualizzazione), contatta il tuo account manager. |
| Codifica pianificata dei rapporti | SHIFT-JIS per la codifica dei caratteri giapponesi. EUC-JP per codice Unix esteso, principalmente per giapponese, coreano e cinese semplificato. |
| Carattere separatore CSV | Il carattere da utilizzare per separare i valori CSV. |

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
|  | Visualizzazioni pagina | Metriche > Visualizzazioni di pagina |
|  | Visite | Metriche > Visite |
|  | Visitatori | Metriche > Visitatori |
|  | Tempo trascorso per ciascuna visita | Metriche > Tempo trascorso per visita |
|  | Tempo precedente all’evento | Conversione > Tempo precedente all’evento |
|  | Acquisti | Metriche > Acquisti |
|  | Carrello | Metriche > Carrello acquisti |
|  | Eventi personalizzati | Metriche > Eventi personalizzati |
|  | Bot | Pubblico > Bot |
|  | Rilevamento delle anomalie | Metriche > Rilevamento delle anomalie |
|  | Tempo reale | Metriche > In Tempo Reale |
| **Contenuto del sito** |  |  |
|  | Pagine | Contenuto > Pagine |
|  | Sezione sito | Contenuto > Sezioni del sito |
|  | Server | Contenuto > Server |
|  | Collegamenti | Navigazione > Collegamenti personalizzati; Navigazione > Collegamenti di uscita; Navigazione > ClickMap; Navigazione > Download di file |
|  | Pagine non trovate | Navigazione > Pagine non trovate |
| **Mobile** |  |  |
|  | Dispositivi | Pubblico > Dispositivi mobili > Dispositivi |
|  | Tipo di dispositivo | Pubblico > Mobile > Tipo di dispositivo |
|  | Produttore | Pubblico > Mobile > Produttore |
|  | Dimensioni dello schermo del dispositivo | Pubblico > Mobile > Screen Size |
|  | Altezza schermo | Pubblico > Mobile > Screen Height |
|  | Larghezza schermo | Pubblico > Mobile > Screen Width |
|  | Supporto per cookie | Pubblico > Mobile > Supporto per cookie |
|  | Supporto immagini | Pubblico > Mobile > Supporto immagini |
|  | Profondità colore | Pubblico > Mobile > Profondità colore |
|  | Supporto audio | Pubblico > Mobile > Supporto audio |
|  | Supporto video | Pubblico > Mobile > Supporto video |
|  | Sistema operativo | Pubblico > Mobile > Sistema operativo |
| **Paths (Percorsi)** |  |  |
|  | Pagine | Navigazione > Percorsi > Pagine |
|  | Termini di ricerca interni | Navigazione > Percorsi > Termini di ricerca interni |
| **Origini del traffico** |  |  |
|  | Parola chiave di ricerca - Tutto | Origini del traffico > Cerca parola chiave - Tutto |
|  | Parola chiave di ricerca - Pagato | Origini del traffico > Cerca parola chiave - Pagato |
|  | Parola chiave di ricerca - Naturale | Origini del traffico > Cerca parola chiave - Naturale |
|  | Motori di ricerca - Tutti | Origini del traffico > Motori di ricerca - Tutti |
|  | Motori di ricerca - Pagati | Origini del traffico > Motori di ricerca - Pagati |
|  | Motori di ricerca - Naturale | Origini del traffico > Motori di ricerca - Naturale |
|  | Classifica di tutte le pagine di ricerca | Origini del traffico > Classifica di tutte le pagine di ricerca |
|  | Domini di riferimento | Origini del traffico > Domini di riferimento |
|  | Domini di riferimento originali | Origini del traffico > Domini di riferimento originali |
|  | Riferimenti | Origini del traffico > Riferimenti |
|  | Tipi di riferimento | Origini del traffico > Tipi di referente |
| **Campagne** |  |  |
|  | Funnel di conversione campagna | Origini del traffico > Campagne > Funnel di conversione campagna |
|  | Codice di tracciamento | Origini del traffico > Campagne > Codice di tracciamento |
| **Prodotti** |  |  |
|  | Funnel di conversione prodotti | Conversione > Prodotti > Funnel di conversione prodotti |
|  | Prodotti | Conversione > Prodotti > Prodotti |
|  | Vendita incrociata | Conversione > Prodotti > Vendita incrociata |
|  | Categorie | Conversione > Prodotti > Categorie |
| **Conservazione dei visitatori** |  |  |
|  | Frequenza di ritorno | Pubblico > Conservazione visitatori > Frequenza di ritorno |
|  | Visite di ritorno | Pubblico > Conservazione visitatori > Visite di ritorno |
|  | Visite giornaliere di ritorno | Pubblico > Conservazione dei visitatori > Visite giornaliere di ritorno |
|  | Numero di visite | Pubblico > Conservazione visitatori > Numero visita |
|  | Ciclo di vendita | Pubblico > Conservazione dei visitatori > Ciclo di vendita |
| **Profilo visitatore** |  |  |
|  | Geosegmentazione | Pubblico > Profilo visitatore > Geosegmentazione |
|  | Lingue | Pubblico > Profilo visitatore > Lingue |
|  | Fusi orari | Pubblico > Profilo visitatore > Fusi orari |
|  | Domains (Domini) | Pubblico > Profilo visitatore > Domini |
|  | Domini di livello principali | Pubblico > Profilo visitatore > Domini di primo livello |
|  | Tecnologia | Pubblico > Profilo visitatore > Tecnologia |
|  | Stato visitatore | Pubblico > Profilo visitatore > Stato visitatore |
|  | Codice postale/ZIP del visitatore | Pubblico > Profilo visitatore > Codice postale/ZIP del visitatore |
| **Conversione personalizzata** |  |  |
|  | Conversione personalizzata 1-10 | Conversione > Conversione personalizzata > Conversione personalizzata 1-10 |
|  | Conversione personalizzata 11-20 | Conversione > Conversione personalizzata > Conversione personalizzata 11-20 |
| **Traffico personalizzato** |  |  |
|  | Traffico personalizzato 1-10 | Contenuto > Traffico personalizzato > Traffico personalizzato 1-10 |
| **Test&amp;Target** |  | Conversione > Test&amp;Target |
| **Sondaggio** |  | Pubblico > Sondaggio |
| **Canali marketing** |  |  |
|  | Rapporto panoramica canale | Origini del traffico > Canali di marketing > Rapporto Panoramica canale |
|  | Canale primo contatto | Origini del traffico > Canali di marketing > Canale primo contatto |
|  | Dettaglio del canale di primo contatto | Origini del traffico > Canali di marketing > Dettaglio del canale di primo contatto |
|  | Canale ultimo contatto | Origini del traffico > Canali di marketing > Canale ultimo contatto |
|  | Dettaglio canale ultimo contatto | Origini del traffico > Canali di marketing > Dettaglio canale ultimo contatto |
| **App mobile** |  |  |
|  | Panoramica dell’app mobile | Contenuto > App mobile > Panoramica app mobile |
|  | Rapporti sul ciclo di vita | Contenuto > App mobile > Rapporti sul ciclo di vita |
| **Report personalizzati** |  |  |
|  | I rapporti personalizzati vengono visualizzati solo se sono impostati. | Report personalizzati |
|  |  |  |
