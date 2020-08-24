---
description: Questa sezione riporta i concetti chiave di Adobe Analytics, una breve descrizione di ogni concetto e un collegamento specifico alla documentazione con informazioni aggiuntive sull'argomento.
title: 'Adobe Analytics: concetti chiave'
translation-type: tm+mt
source-git-commit: 68826433e028825fc43c948d32456416b9d2a13e
workflow-type: tm+mt
source-wordcount: '1864'
ht-degree: 98%

---


# Adobe Analytics: concetti chiave

Questa sezione riporta i concetti chiave di Adobe Analytics, una breve descrizione di ogni concetto e un collegamento specifico alla documentazione con informazioni aggiuntive sull&#39;argomento.

## Strumenti Analytics {#concept_833EDD4EB056491DA1BC5A3A45FE285B}

| Prodotto | Descrizione | Collegamento alla documentazione |
| --- | --- | --- |
| Analysis Workspace | Soluzione browser per la creazione di solidi progetti di analisi personalizzati e la democratizzazione delle informazioni. Offre maggiore flessibilità nella creazione dei report rispetto ad Reports and Analytics | [Analysis Workspace home](/help/analyze/analysis-workspace/home.md) |
| Reports and Analytics (ex SiteCatalyst) | Soluzione browser per la generazione di rapporti e analisi. Strumento di avvio nel pacchetto Analytics. | [Reports and Analytics home](/help/analyze/reports-analytics/getting-started.md) |
| Report Builder | Componente aggiuntivo per Excel che consente di creare richieste personalizzate a partire da dati di Adobe Analytics e di visualizzarle con Microsoft Excel. | [Pagina principale di Report Builder](/help/analyze/report-builder/home.md) |
| Ad Hoc Analysis (precedentemente Discover) | Strumento basato su Java per l&#39;analisi digitale avanzata. | [Pagina principale di Ad Hoc Analysis](/help/analyze/ad-hoc-analysis/adhoc-home.md) |
| Data Workbench (precedentemente Insight) | Progettato per raccogliere, elaborare, analizzare e visualizzare dati dalle interazioni dei clienti online e offline su più canali. | [Client Data Workbench](https://docs.adobe.com/content/help/it-IT/data-workbench/using/client/t-open-ins.html) |
| Data Warehouse | Dati grezzi e non ancora elaborati per l’archiviazione e rapporti personalizzati, che puoi eseguire filtrando i dati. Non a livello hit. | [Pagina principale di Data Warehouse](/help/export/data-warehouse/data-warehouse.md) |
| Adobe Mobile Services | Riunisce le funzionalità di marketing di applicazioni per dispositivi mobili da Adobe Experience Cloud, consentendoti di comprendere e migliorare il coinvolgimento degli utenti con le applicazioni. | [Pagina principale di Mobile Services](https://docs.adobe.com/content/help/it-IT/mobile-services/using/home.html) |
| Data Connectors Adobe Exchange (precedentemente Genesis) | Importa dati di rilevamento da applicazioni di terze parti in Analytics, per offrire visibilità end-to-end alle prestazioni in un&#39;unica posizione centrale. | [Pagina principale dei Data Connectors](/help/import/data-connectors/data-connectors-eol.md) |
| Dynamic Tag Management (DTM) | Consente di gestire i tag Analytics, Target e altri tag in tutti i siti, indipendentemente dal numero di domini. | [Pagina principale di DTM](/help/implement/other/dtm/dtm-implementation-overview.md) |
| Adobe Launch | La nuova generazione di funzionalità di gestione tag per siti Web e SDK per dispositivi mobili di Adobe. | [Pagina principale di Adobe Launch](https://docs.adobe.com/content/help/it-IT/launch/using/overview.html) |

## Terminologia chiave {#concept_E473ACBB8E4A42B4AC005538AC12F154}

Fai clic [qui](/help/technotes/terms.md) per un glossario esteso dei termini di Adobe Analytics.

| Termine | Descrizione | Collegamento alla documentazione |
| --- | --- | --- |
| Proprietà (traffico personalizzato) | Dimensioni utilizzate per monitorare il traffico sul sito pagina per pagina. Prop non persiste tra le pagine. Applicazioni chiave delle variabili del traffico: <ul> <li>Conteggio semplice per trovare il &quot;più popolare&quot; di un valore specifico</li> <li>Visibilità del modo in cui gli utenti si muovono all&#39;interno del tuo sito</li> </ul> <br>Esempi di variabili di traffico: Nome pagina, Sezioni del sito, Browser. | [Proprietà](/help/admin/admin/c-traffic-variables/traffic-var.md) |
| eVar (conversione personalizzata) | Dimensioni che persistono per un periodo di tempo personalizzato dall&#39;utente. Le opzioni di scadenza includono scadenza evento, scadenza visita o scadenza x giorno e devono essere guidate dal tipo di analisi che verrà eseguita su quella variabile. <br> Differenze chiave tra eVar e proprietà: <ul> <li>Le proprietà vengono spesso utilizzate per l&#39;analisi dei percorsi perché la persistenza viene rimossa.</li> <li>Le eVar vengono spesso utilizzate per l&#39;analisi di conversione.</li> </ul> <br>Esempi di variabili di conversione: Termini di ricerca interni, Promozioni interne, Campagne esterne (s.campaign). | [eVar](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) |
| Eventi/metriche (s.events) | Metriche che misurano le azioni chiave che vorremmo fossero intraprese dai nostri visitatori sul nostro sito. Vi sono 3 tipi di eventi: Contatore, Numerico e Valuta. Gli eventi sono più utili quando aggiunti ai report variabile di conversione (eVar). eVar fornisce le informazioni qualitative sugli avvenimenti mentre Evento fornisce informazioni quantitative, sempre sugli avvenimenti. <br> Differenze chiave tra eVar ed eventi: <ul> <li>Le eVar ci dicono chi o cosa ha influito sulla conversione</li> <li>Gli eventi misurano quante conversioni avvengono</li> </ul> <br> Esempi di eventi di conversione: Ordini, Avvii applicazione, Guide, Entrate. | [Eventi](/help/admin/admin/c-success-events/success-event.md) |
| Componenti | Dimensioni, metriche, segmenti e granularità temporali (intervalli di date) da trascinare su un progetto. | [Componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| Dimensioni | Raccolta di eVar, proprietà, classificazioni e valori raccolti standard di Adobe. | [Dimensioni](/help/components/dimensions/overview.md) |
| Metriche | Raccolta di eventi implementati e metriche calcolate. | [Metriche](/help/analyze/analysis-workspace/components/apply-create-metrics.md) |
| Metriche calcolate | Possibilità di derivare metriche personalizzate dalle metriche esistenti acquisite tramite l&#39;implementazione. | [Metriche calcolate](/help/components/c-calcmetrics/cm-overview.md) |
| Segmenti | Capacità di generare, gestire, condividere e applicare segmenti di audience potenti e correttamente focalizzati nei tuoi report di Analytics. I segmenti sono condivisi tra i diversi prodotti Analytics e possono essere condivisi con l’intera soluzione Experience Cloud. | [Segmentazione](/help/components/segmentation/seg-home.md) |
| Tempo (intervalli di date) | Possibilità di filtrare la data in qualsiasi periodo di tempo e creare intervalli di date personalizzati che possono essere riutilizzati nell&#39;analisi. | [Intervalli di date](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) |
| Visualizzazioni | Immagini dettagliate che possono contribuire a dare vita ai dati nei tuoi progetti. | [Visualizzazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| Cura | Possibilità di limitare i componenti accessibili in un progetto o in una suite di rapporti virtuali. | [Cura VRS](/help/components/vrs/vrs-components.md) <br> [Cura del progetto](/help/analyze/analysis-workspace/curate-share/curate.md) <br> [Confronto](/help/analyze/analysis-workspace/curate-share/curate-projects-vrs.md) |

## Rapporti chiave

| Rapporto | Descrizione | Collegamento alla documentazione |
| --- | --- | --- |
| Elenco completo dimensioni/rapporti | Definizione di tutte le dimensioni/rapporti disponibili in Adobe Analytics. | [Dimensioni](/help/components/dimensions/overview.md) |
| Advertising Analytics | Analizza i dati Google e di ricerca a pagamento di Bing affiancati, all&#39;interno di Adobe Analytics. Le dimensioni create tramite l&#39;integrazione includono la piattaforma di annunci, parola chiave, tipo corrispondenza, ecc. Le metriche create sono impressioni AMO, clic AMO, costo AMO, media posizione e media punteggio di qualità. | [Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) |
| Audience Analytics | Arricchisci gli hit di Analytics in entrata con l&#39;iscrizione all&#39;audience degli utenti in AAM. puoi incorporare in un flusso di lavoro Analytics dati sul pubblico da AAM come informazioni demografiche (ad esempio, genere o fascia di reddito), informazioni psicografiche (ad esempio, interessi e hobby), dati CRM o dati di impressioni di annunci. Le dimensioni create tramite questa integrazione sono ID audience e Nome audience. | [Audience Analytics](/help/integrate/c-audience-analytics/mc-audiences-aam.md) |
| Attribution IQ | Consente di comprendere come si verifica un coinvolgimento significativo lungo il percorso del cliente, identificando in modo intelligente i punti di flesso che conducono i clienti verso gli obiettivi desiderati, ottimizzando in modo efficace le attività di marketing. I modelli includono primo, ultimo, lineare, partecipazione, a forma di J, a forma di J inversa, a forma di U, stesso contatto, personalizzato e decadimento nel tempo. | [Attribution IQ](/help/analyze/analysis-workspace/c-panels/attribution.md) |
| Rilevamento delle anomalie | Un metodo statistico per determinare come una particolare metrica è cambiata in relazione ai dati precedenti. Per impostazione predefinita, AD è attivato per tutte le visualizzazioni con tendenze in Analysis Workspace. | [Rilevamento delle anomalie](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Analisi contributi | Esplora il motivo alla base delle anomalie che si verificano, eseguendo un&#39;analisi automatizzata di ogni singola metrica e dimensione a cui hai accesso. | [Analisi contributi](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Analisi per coorte | Una coorte è un gruppo di persone che condividono le stesse caratteristiche per un determinato periodo di tempo. L’analisi per coorte consente di analizzare la conservazione e l&#39;abbandono degli utenti. | [Analisi per coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |
| Rapporti sul percorso del cliente | Visualizza informazioni sul percorso seguito dagli utenti attraverso il sito o l&#39;app. In questa analisi di Analysis Workspace è possibile utilizzare Proprietà, eVar ed eventi. | [Analysis Workspace Fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) <br> [Analysis Workspace Flow](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) <br> [Percorso Reports and Analytics](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
| Canali marketing | Report che ti aiuta a capire quali canali esterni veicolano gli utenti sul tuo sito e quali sono più efficaci nel promuovere la conversione. Vengono fornite le viste di attribuzione Primo e Ultimo tocco. Si tratta del miglior report sulle origini del traffico esterno in Adobe Analytics (piuttosto che Origini traffico o Campagne) in quanto consente di avere la visione più completa sia dei canali organici che pagati. | [Canali marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) |
| Mobile | Visualizza informazioni sui siti Web visitati da dispositivi mobili o tablet. | [Rapporti sui dispositivi mobili](/help/components/dimensions/mobile-dimensions.md) |
| App mobile | Visualizza informazioni d&#39;utilizzo base correlate alle tue app mobili. Questi report sono disponibili una volta che la nostra SDK viene implementata e il reporting è attivo.  Adobe Mobile Services ha inoltre creato un&#39;interfaccia per l&#39;app mobile separata in grado di fornire dati sull&#39;app più completi, consentendoti di comprendere e migliorare il coinvolgimento dell&#39;utente nei confronti delle tue app.  Accedi all&#39;interfaccia [qui](https://mobilemarketing.adobe.com). | [Adobe Mobile Services](https://docs.adobe.com/content/help/it-IT/mobile-services/using/home.html) |
| Prodotti | Identifica la modalità in cui i singoli prodotti e i gruppi di prodotti (categorie) contribuiscono alle varie metriche di conversione personali, come Entrate o Checkout. | [Rapporto sui prodotti](/help/components/dimensions/product.md) |
| Confronto fra segmenti | Scopre le differenze più importanti dal punto di vista statistico tra i segmenti attraverso un&#39;analisi automatizzata di ogni metrica e dimensione a cui hai accesso. | [Confronto segmenti](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) |
| Rapporto sul contenuto del sito | Visualizza informazioni su quali pagine e aree del tuo sito risultano più attive e quali server vengono utilizzati maggiormente. | [Rapporto sul contenuto del sito](/help/components/dimensions/page.md) |
| Rapporto sulle metriche del sito | Visualizzano informazioni quantitative sul tuo sito Web come visitatori unici, ordini, entrate, ecc... Ogni metrica può essere collocata in altri report basati su elementi. | [Rapporto sulle metriche del sito](/help/components/metrics/overview.md) |
| Profilo visitatore | Report che ti aiutano a visualizzare i modelli di acquisto dei clienti da varie categorie di profilo come paesi, stati, codici di avviamento postale e domini. | [Profilo visitatore](/help/components/dimensions/language.md) |
| Conservazione dei visitatori | Visualizza informazioni sulla fidelizzazione dei tuoi clienti, ad esempio quanti visitatori tornano a visitare il tuo sito e con quale frequenza. | [Conservazione dei visitatori](/help/components/dimensions/customer-loyalty.md) |
| Collegamento, condivisione e pianificazione del progetto | Metodi per il salvataggio/la condivisione del tuo lavoro con altri nell&#39;interfaccia di Analytics. | [Invio e programmazione di file](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md) |

## Metriche chiave {#concept_392819DC275C48688E2CE4ABD4C5EE43}

| Nome della metrica | Definizione | Collegamento alla documentazione |
| --- | --- | --- |
| Elenco completo delle metriche | Definizione di tutte le metriche in Adobe Analytics. | [Panoramica delle metriche](/help/components/metrics/overview.md) |
| Visitatori unici | Il numero di visitatori del sito Web non duplicati nel corso di un periodo di tempo specificato. | [Visitatori unici](/help/components/metrics/unique-visitors.md) |
| Visite | Una sequenza di pagine visualizzate in una sessione. La visita inizia nel momento in cui una persona visualizza per la prima volta una pagina del sito e termina dopo 30 minuti di inattività. | [Visite](/help/components/metrics/visits.md) |
| Visualizzazioni pagina | Una visualizzazione di pagina si verifica quando un visitatore visualizza una pagina sul tuo sito Web. | [Visualizzazioni pagina](/help/components/metrics/page-views.md) |
| Istanze | Il numero di volte in cui è stata definita una variabile. Ogni volta che Adobe Analytics rileva un valore all’interno di una variabile, le istanze aumentano di un’unità nel rispettivo rapporto. | [Istanze](/help/components/metrics/instances.md) |
| Occorrenze | Il numero di volte che una variabile è stata definita o è persistita. | [Occorrenze](/help/components/metrics/occurrences.md) |

## Opzioni di importazione {#concept_7C6DF03B5F9149E2A77F36C739432059}

| Opzione | Descrizione | Collegamento alla documentazione |
| --- | --- | --- |
| Importatore di classificazione | Importa i metadati rispetto alle dimensioni acquisite, attraverso il browser o tramite caricamento FTP. Metodo manuale confrontato al Generatore di regole. | [Importatore di classificazione](/help/components/classifications/importer/c-working-with-saint.md) |
| Generatore di regole | Crea automaticamente classifiche delle dimensioni dei metadati sulla base di regole definite dall&#39;utente. | [Generatore regole di classificazione](/help/components/classifications/crb/classification-rule-builder.md) |
| Attributi cliente | Dati CRM caricati in Experience Cloud per l&#39;utilizzo in Adobe Analytics e Adobe Target. | [Attributi cliente](https://docs.adobe.com/content/help/it-IT/core-services/interface/customer-attributes/attributes.html) |
| Origini dati | Importa le metriche in modalità offline in Analytics secondo le dimensioni o semplicemente per giorno. | [Origini dati](/help/import/c-data-sources/datasrc-home.md) |
| Data Connectors Adobe Exchange | Consulta [Strumenti di Analytics.](/help/import/data-connectors/data-connectors-eol.md) |  |
| Integrazioni native | Audience Analytics e Advertising Analytics. | Vedi la sezione &quot;Rapporti chiave&quot;. |

## Opzioni di esportazione {#concept_C62B688E259141CF92C048E8110464BE}

| Opzione | Descrizione | Collegamento alla documentazione |
| --- | --- | --- |
| Download e pianificazione dell&#39;interfaccia utente | Esporta dati da Analysis Workspace in formato CSV o PDF. | [Scaricare file PDF o CSV](/help/analyze/analysis-workspace/curate-share/download-send.md) |
| Report Builder | Consulta gli Strumenti di Analytics. |  |
| API di Analytics | Crea le tue query personalizzate dei dati di Analytics. | <ul><li>[API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)</li><li>[API 1.4](https://github.com/AdobeDocs/analytics-1.4-apis)</li></ul> |
| Data Warehouse | Consulta gli Strumenti di Analytics. |  |
| Feed dati di Analytics | La modalità più granulare per estrarre i dati da Analytics. Configurare un feed hit-level da Analytics. | [Feed dati di Analytics](/help/export/analytics-data-feed/data-feed-overview.md) |

## Raccolta e convalida dei dati {#concept_E07350D4CA5047DAA7D81F762F29606A}

| Metodo/Risorsa | Descrizione | Collegamento alla documentazione |
| --- | --- | --- |
| Risorse per gli sviluppatori | Documentazione che indica le librerie disponibili per la raccolta di dati di Analytics in tutte le piattaforme disponibili (Web, app mobili, video, flash, ecc.) | [Documenti per sviluppatori](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| Guida all&#39;implementazione | Una descrizione delle variabili di raccolta dati e informazioni sull&#39;implementazione dei codici di raccolta dati in JavaScript. | [Guida all&#39;implementazione](/help/implement/home.md) |
| Misurazione app (s_code) | Gestione globale delle variabili. | [AppMeasurement](/help/implement/js/migrate-from-hcode.md) |
| SDK per le app | Pacchetto personalizzato che include una versione pre-popolata del file di configurazione per le app. | <ul><li>[iOS](https://docs.adobe.com/content/help/it-IT/mobile-services/ios/overview.html)</li><li>[Android](https://docs.adobe.com/content/help/it-IT/mobile-services/android/getting-started-android/requirements.html)</li></ul> |
| DTM e Adobe Launch | Consulta gli Strumenti di Analytics. |  |
| VISTA | Consente di applicare una logica lato server per modificare o segmentare i dati durante la raccolta. | [Regole VISTA](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md) |
| Regole di elaborazione | Possibilità di impostare, modificare e copiare variabili nell’interfaccia utente di Analytics per modificare i dati raccolti. | [Regole di elaborazione](/help/admin/admin/c-processing-rules/processing-rules.md) |
| Opzioni debugger | Sono disponibili diversi debugger e sniffer pacchetti per aiutarti a convalidare la tua implementazione, tra cui il debugger Adobe Experience Cloud. | [Adobe Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj?hl=it) |
| API di inserimento dati | L&#39;API di inserimento dati fornisce un meccanismo per la raccolta dei dati lato server e l&#39;invio ai server Experience Cloud. Invece di utilizzare beacon JavaScript su ogni pagina Web per trasmettere i dati dei visitatori ai server Experience Cloud, la raccolta dei dati lato server raccoglie i dati esclusivamente in base alle richieste del browser Web e alle risposte del server Web. | [Passaggi per implementare l&#39;API di inserimento dati di Adobe Analytics tramite POST](https://helpx.adobe.com/it/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
