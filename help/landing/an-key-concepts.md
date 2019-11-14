---
description: Questa sezione riporta i concetti chiave di Adobe Analytics, una breve descrizione di ogni concetto e un collegamento specifico alla documentazione con informazioni aggiuntive sull'argomento.
title: 'Adobe Analytics: concetti chiave'
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Analytics: concetti chiave

Questa sezione riporta i concetti chiave di Adobe Analytics, una breve descrizione di ogni concetto e un collegamento specifico alla documentazione con informazioni aggiuntive sull'argomento.

## Analytics tools {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Prodotto | Descrizione | Collegamento alla documentazione |
|--- |--- |--- |
| Analysis Workspace | Soluzione browser per la creazione di solidi progetti di analisi personalizzati e la democratizzazione delle informazioni. Offre maggiore flessibilità di reporting e analisi | [adobe.ly/aaworkspacedocs](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/analysis-workspace-features.html) |
| Reporting e analisi (ex SiteCatalyst) | Soluzione browser per reporting e analisi. Strumento di avvio nel pacchetto Analytics. | [Pagina principale Reporting e analisi](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html) |
| Report Builder | Componente aggiuntivo di Excel che consente di creare richieste personalizzate a partire da dati di Adobe Analytics e visualizzarle tramite Microsoft Excel. | [Home del Generatore di report](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/home.html) |
| Analisi ad hoc (precedentemente Discover) | Strumento basato su Java per l'analisi digitale avanzata. | [Pagina principale Analisi ad hoc](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/adhoc-home.html) |
| Workbench dati (ex Insight) | Progettato per raccogliere, elaborare, analizzare e visualizzare dati dalle interazioni dei clienti online e offline su più canali. | [Client Workbench dati](https://marketing.adobe.com/resources/help/en_US/insight/client/) |
| Data Warehouse | Dati grezzi e non ancora elaborati per l’archiviazione e rapporti personalizzati, che puoi eseguire filtrando i dati. Livello non hit. | [Home page di Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) |
| Adobe Mobile Services | Riunisce le funzionalità di marketing mobile di applicazioni per dispositivi mobili da Adobe Experience Cloud, consentendoti di comprendere e migliorare il coinvolgimento degli utenti con le tue applicazioni. | [Pagina principale di Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) |
| Connettori dati Adobe Exchange (già Genesis) | Importa dati di tracciamento da applicazioni di terze parti in Analytics, per dare visibilità completa alle prestazioni in un'unica posizione centrale. | [Home dei Connettori dati](https://marketing.adobe.com/developer/documentation/genesis/c-overview-how-it-works) |
| Dynamic Tag Management (DTM) | Consente di gestire i tag Analytics, Target e altri in tutti i siti, indipendentemente dal numero di domini. | [Home DTM](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/dtm-implementation-overview.html) |
| Adobe Launch | La nuova generazione di funzionalità di gestione tag per siti Web e SDK per dispositivi mobili di Adobe. | [Adobe Launch home](https://docs.adobe.com/content/help/en/launch/using/overview.html) |

## Terminologia chiave {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Fai clic [qui](https://docs.adobe.com/content/help/en/analytics/technotes/terms.html) per un glossario esteso dei termini di Adobe Analytics.

| Termine | Descrizione  | Collegamento alla documentazione |
|--- |--- |--- |
| Prop (traffico personalizzato) | Dimensioni utilizzate per monitorare l'attività di traffico del sito pagina per pagina. Prop non persiste tra le pagine. Applicazioni chiave delle variabili del traffico: <ul><li>Conteggio semplice per trovare il 'più popolare' di un valore specifico</li><li>Visibilità del modo in cui gli utenti attraversano il sito </li></ul><br>Esempi di variabili di traffico: Nome pagina, Sezioni del sito, Browser</br> | [Proprietà](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/traffic-variables/traffic-var.html) |
| eVar (conversione personalizzata) | Dimensioni che persistono per un periodo di tempo personalizzato. Le opzioni di scadenza includono scadenza evento, scadenza visita o scadenza x giorno e devono essere guidate dal tipo di analisi che verrà eseguita su quella variabile.<br>Differenze chiave tra eVar e prop:</br><ul><li>Le proprietà vengono spesso utilizzate per l'analisi dei percorsi perché la persistenza viene rimossa.</li><li>Le eVar vengono spesso utilizzate per l'analisi di conversione.</li></ul><br>Esempi di variabili di conversione: Termini di ricerca interni, Promozioni interne, Campagne esterne (s.campaign)</br> | [eVar](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Eventi/metriche (s.events) | Metriche che misurano le azioni chiave che vogliamo che i nostri visitatori intraprendano sul nostro sito. Vi sono 3 tipi di eventi: Contatore, Numerico e Valuta. Gli eventi sono più utili quando aggiunti ai report variabile di conversione (eVar). eVar fornisce le informazioni qualitative sugli avvenimenti mentre Evento fornisce informazioni quantitative, sempre sugli avvenimenti. <br>Differenze chiave tra eVar ed eventi:</br><ul><li>Le eVar ci dicono chi, cosa o chi ha influenzato la conversione</li><li>Gli eventi misurano quante conversioni avvengono</li></ul><br>Esempi di eventi di conversione: Ordini, Avvii applicazione, Guide, Entrate.</br> | [Eventi](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) |
| Componenti | Dimensioni, metriche, segmenti e unità di tempo (intervalli di date) che puoi trascinare su un progetto. | [Componenti](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) |
| Dimensioni | Raccolta di eVar, prop, classificazioni e valori raccolti standard da Adobe. | [Dimensioni](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-descriptions.html) |
| Metriche | Raccolta di eventi implementati e metriche calcolate. | [Metriche](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html) |
| Metriche calcolate | Possibilità di derivare metriche personalizzate dalle metriche esistenti acquisite tramite l'implementazione. | [Metriche calcolate](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/cm-overview.html) |
| Segmenti | Capacità di generare, gestire, condividere e applicare segmenti di audience potenti e correttamente focalizzati nei tuoi report di Analytics. I segmenti vengono condivisi tra i prodotti Analytics e in Experience Cloud. | [Segmentazione](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html) |
| Ora (intervalli di date) | Possibilità di filtrare la data in qualsiasi periodo di tempo e creare intervalli di date personalizzati che possono essere riutilizzati nell'analisi. | [Intervalli di date](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) |
| Visualizzazioni | Immagini dettagliate che possono contribuire a dare vita ai dati nei tuoi progetti. | [Visualizzazioni](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) |
| Cura | Possibilità di limitare i componenti accessibili in un progetto o in una suite di rapporti virtuale. | [VRS](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-components.html)<br>[curationProject](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)</br><br>[curationComparison](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate-projects-vrs.html) |

## Report chiave

| Report  | Descrizione  | Collegamento alla documentazione |
|--- |--- |--- |
| Elenco completo dimensioni/rapporti | Definizione di tutte le dimensioni/rapporti disponibili in Adobe Analytics. | [Dimensioni](https://marketing.adobe.com/resources/help/en_US/reference/reports_descriptions.html) |
| Advertising Analytics | Analizzare i dati Google e Bing Paid Search affiancati, in Adobe Analytics. Le dimensioni create tramite l'integrazione includono Ad Platform, Keyword, Match Type, ecc. Le metriche create sono Impression AMO, Clic AMO, Costo AMO, Media. Posizione e media. Punteggio di qualità. | [Advertising Analytics](https://docs.adobe.com/help/en/analytics/integration/advertising-analytics/overview.html) |
| Audience Analytics | Arricchisci gli hit di Analytics in entrata con l'iscrizione di un utente ad AAM. puoi incorporare dati di pubblico AAM come informazioni demografiche (ad esempio, genere o livello di reddito), informazioni psicografiche (ad esempio, interessi e hobby), dati CRM e dati sulle impressioni degli annunci in qualsiasi flusso di lavoro Analytics. Le dimensioni create tramite questa integrazione sono Audience ID e Audience Name. | [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) |
| Attribution IQ | Consente di comprendere in che modo il coinvolgimento significativo ha luogo nel percorso del cliente, identificando in modo intelligente i punti di flessione che portano i clienti a raggiungere risultati concreti, ottimizzando efficacemente le iniziative di marketing. I modelli includono primo, ultimo, lineare, partecipazione, j-shape, inversa j-shape, u-shape, stesso tocco, personalizzato e decadimento temporale. | [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html) |
| Detección de anomalías | Un metodo statistico per determinare in che modo una data metrica è cambiata rispetto ai dati precedenti. Per impostazione predefinita, AD è attivato per tutte le visualizzazioni con tendenze in Analysis Workspace. | [Detección de anomalías](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) |
| Analisi contributi | Esplora il "perché" dietro le anomalie che si verificano, eseguendo un'analisi automatizzata di ogni singola metrica e dimensione a cui hai accesso. | [Analisi contributi](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) |
| Analisi per coorte | Una coorte è un gruppo di persone che condividono caratteristiche comuni in un determinato periodo di tempo. L’analisi per coorte consente di analizzare il mantenimento e il cambiamento degli utenti. | [Analisi per coorte](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) |
| Rapporti sul percorso del cliente | Visualizza informazioni sul percorso seguito dagli utenti attraverso il sito o l'app. Prop, eVar ed eventi possono essere utilizzati in questa analisi in Analysis Workspace. | [Percorsi](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)[FalloutAnalysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/flow/flow.html)[FlussoReporting e analisi](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-paths.html) |
| Canali marketing | Report che ti aiuta a capire quali canali esterni veicolano gli utenti sul tuo sito e quali sono più efficaci nel promuovere la conversione. Vengono fornite le viste di attribuzione Primo e Ultimo tocco. Si tratta del miglior report sulle origini del traffico esterno in Adobe Analytics (piuttosto che Origini traffico o Campagne) in quanto consente di avere la visione più completa sia dei canali organici che pagati. | [Canali marketing](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-getting-started-mchannel.html) |
| Mobile | Visualizza informazioni sui siti Web visitati da dispositivi mobili o tablet. | [Rapporto mobile | (https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-mobile.html) |
| App mobile | Visualizza informazioni d'utilizzo base correlate alle tue app mobili. Questi report sono disponibili una volta che la nostra SDK viene implementata e il reporting è attivo.  Adobe Mobile Services ha inoltre creato un'interfaccia per l'app mobile separata in grado di fornire dati sull'app più completi, consentendoti di comprendere e migliorare il coinvolgimento dell'utente nei confronti delle tue app.  Accedi all'interfaccia [qui](https://mobilemarketing.adobe.com). | [Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) | Prodotti | Identifica la modalità in cui i singoli prodotti e i gruppi di prodotti (categorie) contribuiscono alle varie metriche di conversione personali, come Entrate o Checkout. | [Report prodotti](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-products.html) |
| Confronto fra segmenti | Scopre le differenze più importanti dal punto di vista statistico tra i segmenti attraverso un'analisi automatizzata di ogni metrica e dimensione a cui hai accesso. | [Confronto segmenti](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html) |
| Report Contenuto del sito | Visualizza informazioni su quali pagine e aree del tuo sito risultano più attive e quali server vengono utilizzati maggiormente. | [Report Contenuto del sito](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-content.html) |
| Rapporto Metriche del sito | Visualizzano informazioni quantitative sul tuo sito Web come visitatori unici, ordini, entrate, ecc... Ogni metrica può essere collocata in altri report basati su elementi. | [Rapporto Metriche del sito](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-site-metrics.html) |
| Profilo visitatore | Report che ti aiutano a visualizzare i modelli di acquisto dei clienti da varie categorie di profilo come paesi, stati, codici di avviamento postale e domini. | [Profilo visitatore](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-profile.html) |
| Conservazione dei visitatori | Visualizza informazioni sulla fidelizzazione dei tuoi clienti, ad esempio quanti visitatori tornano a visitare il tuo sito e con quale frequenza.  | [Conservazione dei visitatori](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-visitor-retention.html) |
| Collegamento, condivisione e pianificazione del progetto | Metodi per il salvataggio/la condivisione del tuo lavoro con altri nell'interfaccia di Analytics. | [Inviare e pianificare file](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html) |

## Key metrics {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Nome della metrica | Definizione | Collegamento alla documentazione |
|---|---|---|
| Elenco completo delle metriche | Definizione di tutte le metriche in Adobe Analytics. | [Panoramica delle metriche](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-overview.html) |
| Visitatori unici | Il numero di visitatori del sito Web non duplicati nel corso di un periodo di tempo specificato. | [Visitatori unici](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-unique-visitors-v15-dsc.html) |
| Visite | Una sequenza di pagine visualizzate in una sessione. La visita inizia nel momento in cui una persona visualizza per la prima volta una pagina del sito e termina dopo 30 minuti di inattività. | [Visite](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-visit.html) |
| Visualizzazioni pagina | Una visualizzazione di pagina si verifica quando un visitatore visualizza una pagina sul tuo sito Web. | [Visualizzazioni pagina](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-page-view.html) |
| Istanze | Il numero di volte in cui è stata definita una variabile. Ogni volta che Adobe Analytics rileva un valore all’interno di una variabile, le istanze aumentano di un’unità nel rispettivo rapporto. | [Istanze](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-instance.html) |
| Occorrenze | Il numero di volte in cui una variabile è stata definita o persistente. | [Occorrenze](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html) |

## Import options {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Opzione | Descrizione | Collegamento alla documentazione |
|---|---|---|
| Importatore di classificazione | Importa i metadati rispetto alle dimensioni acquisite, attraverso il browser o tramite caricamento FTP. Metodo manuale confrontato al Generatore di regole. | [Importatore di classificazione](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) |
| Generatore di regole | Crea automaticamente classifiche delle dimensioni dei metadati sulla base di regole definite dall'utente. | [Generatore regole di classificazione](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) |
| Attributi cliente | Dati CRM caricati in Experience Cloud per l'utilizzo in Adobe Analytics e Adobe Target. | [Attributi cliente](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) |
| Origini dati | Importa le metriche offline in Analytics in base alle dimensioni o semplicemente per giorno. | [Origini dati](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html) |
| Connettori dati Adobe Exchange | Consulta Strumenti [di Analytics](/help/landing/an-key-concepts.md) |  |
| Integrazioni native | Audience Analytics &amp; Advertising Analytics. | Vedere la sezione "Report chiave". |

## Export options {#concept_C62B688E259141CF92C048E8110464BE}

| Opzione | Descrizione | Collegamento alla documentazione |
|---|---|---|
| Download e pianificazione dell'interfaccia utente | Esportare dati da Analysis Workspace come CSV o PDF | [Scaricare file PDF o CSV](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Consultate Strumenti di Analytics. |
| API di Analytics | Crea le tue query personalizzate dei dati di Analytics. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Consultate Strumenti di Analytics. |  |
| Feed dati di Analytics | La modalità più granulare per estrarre i dati da Analytics. Configurare un feed hit-level da Analytics. | [Feed dati di Analytics](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/get-started/data-feed-overview.html) |

## Data collection and validation {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Metodo/Risorsa | Descrizione  | Collegamento alla documentazione |
|--- |--- |--- |
| Risorse per gli sviluppatori | Documentazione che delinea le librerie disponibili per raccogliere i dati di Analytics in tutte le piattaforme disponibili (Web, app mobili, video, flash, ecc.) | [Documenti per sviluppatori](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Guida all'implementazione | Una descrizione delle variabili di raccolta dati e informazioni sull'implementazione dei codici di raccolta dati in JavaScript. | [Guida all'implementazione](https://docs.adobe.com/content/help/en/analytics/implementation/home.html) |
| Misurazione app (s_code) | Gestione globale delle variabili | [AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html) |
| SDK per le app | Pacchetto personalizzato che include una versione pre-popolata del file di configurazione per le app. | <ul><li>[iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/en/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM e Adobe Launch | Consultate Strumenti di Analytics. |  |
| VISTA | Consente di applicare una logica lato server per modificare o segmentare i dati durante la raccolta. | [Regole VISTA](https://marketing.adobe.com/resources/help/en_US/reference/VISTA.html) |
| Regole di elaborazione | Possibilità di impostare, modificare e copiare variabili nell’interfaccia utente di Analytics per modificare i dati raccolti. | [Regole di elaborazione](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| Opzioni debugger | Sono disponibili diversi debugger e packet sniffer per aiutarti a convalidare la tua implementazione, incluso Adobe Experience Cloud Debugger. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=en) |
| API di inserimento dati | L'API di inserimento dei dati fornisce un meccanismo per la raccolta dei dati lato server e l'invio ai server Experience Cloud. Invece di utilizzare beacon JavaScript su ogni pagina Web per trasmettere i dati dei visitatori ai server Experience Cloud, la raccolta dei dati lato server raccoglie i dati esclusivamente in base alle richieste del browser Web e alle risposte del server Web. | [Passaggi per implementare l'API di inserimento dati di Adobe Analytics tramite POST](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
