---
description: Informazioni generali su Adobe Analytics, incluse informazioni sull’interfaccia di Analytics e informazioni introduttive per amministratori, analisti, utenti e sviluppatori.
title: Panoramica di Adobe Analytics
feature: Analytics Basics
hide: true
hidefromtoc: true
source-git-commit: f2f1d21989b609bf069da28b3b90785ccd14ef19
workflow-type: tm+mt
source-wordcount: '5045'
ht-degree: 35%

---

# Panoramica di Adobe Analytics

Adobe Analytics consente alle organizzazioni di raccogliere dati e ottenere informazioni fruibili da qualsiasi interazione con i clienti digitali. Grazie ad analisi approfondite, rapporti versatili e funzioni di analisi predittiva, le organizzazioni possono contare su basi solide per creare esperienze migliori per i propri clienti.

## Vantaggi chiave

Di seguito sono riportati alcuni dei modi principali in cui Adobe Analytics aiuta le organizzazioni a ottenere informazioni critiche per servire meglio i propri clienti.

Per ulteriori dettagli sui vantaggi offerti da Adobe Analytics, vedi [Pagina prodotto Adobe Analytics](https://business.adobe.com/products/analytics/adobe-analytics.html).

### Analisi web

Adobe Analytics fornisce la segmentazione complessa e gli strumenti predittivi seguenti per l’analisi del traffico web:

* [Analisi ad hoc in Analysis Workspace](/help/analyze/analysis-workspace/home.md)

* [Analisi del flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)

* [Segmentazione avanzata](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)

### Analisi di marketing

Adobe Analytics aiuta le organizzazioni a capire dove i clienti interagiscono con i loro marchi, quali canali preferiscono i clienti e quali esperienze trovano accoglienza.

Le seguenti funzioni chiave di Adobe Analytics forniscono queste funzionalità di marketing:

* Raccolta di dati multicanale

* [Integrazione dei dati offline](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en)

* [Analisi ad hoc in Analysis Workspace](/help/analyze/analysis-workspace/home.md)

### Attribution

Attribution consente alle organizzazioni di vedere in che modo le diverse interazioni all’interno del percorso di clienti influiscono sulla conversione. Oltre a fornire opzioni di attribuzione più tradizionali, come modelli Lineari o First Touch, Attribution in Adobe Analytics utilizza anche l’apprendimento automatico e modelli statistici avanzati per comprendere l’impatto preciso di ogni contatto.

Per ulteriori informazioni, consulta [Modelli di attribuzione e intervalli di lookback](/help/analyze/analysis-workspace/attribution/models.md).


### Analisi predittiva

L’analisi predittiva utilizza l’apprendimento automatico e la modellazione statistica avanzata per analizzare i dati dei clienti, trovare modelli e prevedere il comportamento futuro, ad esempio l’abbandono o la probabilità di conversione. Consente agli analisti di dati di sfruttare enormi set di dati che altrimenti potrebbero andare sprecati.

Le seguenti funzioni chiave di Adobe Analytics forniscono queste funzionalità predittive:

* [Rilevamento delle anomalie](#anomaly-detection)

* [Analisi contributi](#contribution-analysis)

* [Avvisi intelligenti](#intelligent-alerts)

## Prerequisiti per l’utilizzo di Adobe Analytics

Prima di poter utilizzare Adobe Analytics, è necessario disporre di:

* Una licenza Adobe Analytics valida

  Adobe Analytics richiede una licenza per il sito. Per ulteriori informazioni, contatta il tuo Account Manager Adobe. <!--is this phrased correctly? Is this important? -->

* Un browser supportato

  Ogni utente che accede ad Adobe Analytics deve utilizzare un browser supportato. Per ulteriori informazioni, vedere [Requisiti di sistema di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/admin-overview/sys-reqs.html?lang=en).

<!-- are there more? -->

## Interfaccia di Analytics

L’interfaccia di Adobe Analytics è costituita dalle seguenti aree principali:

### Scheda Area di lavoro

Il [!UICONTROL Workspace] mostra la scheda [!UICONTROL Projects] per impostazione predefinita, mostra la cartella Azienda, le cartelle personali create, i progetti e le scorecard per dispositivi mobili.

1. In Adobe Analytics, seleziona la [!UICONTROL **Workspace**] scheda.

   ![Scheda Area di lavoro](assets/landing-all2.png)

Per ulteriori informazioni sulle funzioni disponibili nella [!UICONTROL Workspace] , vedere [Pagina di destinazione di Adobe Analytics](/help/analyze/landing.md).

### Scheda Rapporti

A partire dal 31 dicembre 2023, Adobe intende interrompere Reports &amp; Analytics e i relativi rapporti e funzioni.

Invece, utilizza [!UICONTROL **Rapporti**] area nella barra a sinistra sulla [!UICONTROL **Workspace**] scheda. Per ulteriori informazioni, consulta *Passare alla scheda Rapporti* in [Pagina di destinazione di Adobe Analytics](/help/analyze/landing.md).

### Scheda Componenti

Il [!UICONTROL Components] La scheda include funzioni che consentono di perfezionare e abilitare l’analisi dei dati.

1. In Adobe Analytics, seleziona la [!UICONTROL **Componenti**] , quindi seleziona [!UICONTROL **Tutti i componenti**].

   ![Scheda Area di lavoro](assets/components-tab.png)

2. Seleziona una delle seguenti funzioni del prodotto per configurarla:


   | Funzionalità del prodotto | Funzione | Ulteriori informazioni |
   |---------|----------|----------|
   | Segmenti  | Adobe Analytics ti consente di creare, gestire, condividere e applicare segmenti di pubblico efficaci e mirati ai tuoi rapporti utilizzando le funzionalità di Analytics, Adobe Experience Cloud, Adobe Target e altri prodotti Adobe integrati. | [Segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=it) |
   | Metriche calcolate | Le metriche calcolate e avanzate calcolate (o derivate) sono metriche personalizzate che puoi creare dalle metriche esistenti.  Consentono ad addetti al marketing, product manager e analisti di porre domande sui dati senza dover modificare l’implementazione di Analytics. | [Metriche calcolata e metriche calcolata avanzata (derivate)](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/cm-overview.html?lang=it) |
   | Intervalli di date | Analysis Workspace include un elenco di intervalli di date predefiniti che gli utenti possono utilizzare per la creazione di analisi. Inoltre, puoi creare intervalli di date personalizzati e renderli disponibili agli utenti in Analysis Workspace. | [Creare intervalli di date personalizzati](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=it) <!-- should create an article in the Components Guide for managing/creating date ranges. This article in the Tools Guide needs updating. --> |
   | Suite di rapporti virtuali | Le suite di rapporti virtuali segmentano i dati di Adobe Analytics in modo da poter controllare l’accesso a ciascun segmento. | [Panoramica delle suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=it) |
   | Avvisi | Gli avvisi intelligenti consentono un controllo più granulare sugli avvisi e integrano il rilevamento delle anomalie con il sistema di avvisi. | [Avvisi intelligenti](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=en) |
   | Target | I target consentono di misurare le prestazioni del sito web e monitorare l’avanzamento rispetto agli obiettivi target. Quando crei le destinazioni, selezioni le metriche attributo o le eVar da misurare oppure puoi scegliere di misurare l’intero sito rispetto alla metrica selezionata. <p>Le destinazioni fanno parte di Reports &amp; Analytics. Ulteriori informazioni sull’[Annuncio sulla fine del ciclo di vita](https://express.adobe.com/page/6WnF8JK6IRDhf/) di Reports &amp; Analytics.</p> | [Target](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/targets.html?lang=en) |
   | Eventi calendario | Per i report con tendenze nel tempo, gli eventi calendario consentono di visualizzare graficamente gli eventi e vedere se campagne o altri eventi hanno influito sul traffico del sito, sulle entrate o su qualsiasi altra metrica. | [Eventi calendario](https://experienceleague.adobe.com/docs/analytics/components/t-calendar-event.html?lang=en) |
   | Annotazioni | Le annotazioni in Workspace consentono di comunicare in modo efficace dettagli sui dati contestuali a beneficio degli utenti in tutta l’organizzazione. Consentono di collegare gli eventi del calendario a dimensioni e metriche specifiche. | [Gestire le annotazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/annotations/manage-annotations.html?lang=en) |
   | Set di classificazione | I set di classificazione forniscono un’unica interfaccia per gestire classificazioni e regole. <p>Una classificazione è un modo per classificare i dati delle variabili di Analytics e visualizzarli in modi diversi quando si generano i rapporti. Puoi stabilire una relazione tra un valore di variabile e i metadati correlati a tale valore. Le classificazioni possono essere utilizzate sulla maggior parte delle dimensioni personalizzate, come codice di tracciamento, prop ed eVar.</p> | [Panoramica sui set di classificazione](https://experienceleague.adobe.com/docs/analytics/components/classifications/sets/overview.html?lang=it) |
   | Posizioni | Per importare i dati di classificazione Adobe Analytics da una destinazione cloud, devi innanzitutto aggiungere e configurare il percorso in cui desideri raccogliere i dati di classificazione. Puoi creare, modificare o eliminare le posizioni. | [Gestione posizioni](https://experienceleague.adobe.com/docs/analytics/components/locations/locations-manager.html?lang=en) |
   | Progetti programmati | Durante la gestione dei progetti pianificati, puoi modificare ed eliminare pianificazioni di progetto ricorrenti; cercare una pianificazione nella barra di ricerca o utilizzando le opzioni di filtro nella barra a sinistra; e filtrare per tag, pianificazioni approvate, proprietari e altro ancora. | [Progetti programmati](/help/components/scheduled-projects-manager.md) |
   | Segnalibri | I segnalibri consentono di accedere ai rapporti più utilizzati. I segnalibri creati vengono aggiunti all’Experience Cloud e sono disponibili in funzionalità integrate come connettori dati. <p>I segnalibri fanno parte di Reports &amp; Analytics. Ulteriori informazioni sull’[Annuncio sulla fine del ciclo di vita](https://express.adobe.com/page/6WnF8JK6IRDhf/) di Reports &amp; Analytics. | [Gestione segnalibri](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/bookmarks.html?lang=en) |
   | Dashboard | Le dashboard vengono create per visualizzare le metriche e fornire funzionalità di analisi interattiva con i dati. Facendo clic sugli elementi all’interno di una dashboard, puoi segmentare i dati in modo rapido e semplice per derivare informazioni dall’analisi. <p>I dashboard fanno parte della Data Workbench. Ulteriori informazioni sulla Data Workbench [Annuncio sulla fine del ciclo di vita](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=en). | [Gestione dashboard](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/dashboard-manage.html?lang=en) |
   | Rapporti pianificati | Gli utenti a livello di amministratore possono visualizzare e gestire i rapporti pianificati in tutta l’organizzazione. | [Coda dei report pianificati](https://experienceleague.adobe.com/docs/analytics/components/scheduled-reports-admin.html?lang=en) |
   | Impostazioni dei rapporti | Queste impostazioni si riferiscono ai prodotti Adobe Analytics precedenti, che escludono Analysis Workspace e i relativi componenti. Per apportare modifiche alle impostazioni di Analysis Workspace, vai a Componenti > Preferenze. |  |
   | Preferenze | Gestisci le impostazioni di Analysis Workspace e dei relativi componenti per tutti i nuovi progetti o pannelli creati. I progetti e i pannelli esistenti non sono interessati. | [Preferenze](/help/analyze/analysis-workspace/user-preferences.md) |

   {style="table-layout:auto"}

### Scheda Strumenti

<!-- The Tools tab ... -->

1. In Adobe Analytics, seleziona la [!UICONTROL **Strumenti**] , quindi seleziona [!UICONTROL **Tutti gli strumenti**].

   ![Scheda Area di lavoro](assets/tools-tab.png)

2. Seleziona una delle seguenti funzioni del prodotto per configurarla:

   | Funzionalità del prodotto | Funzione | Ulteriori informazioni |
   |---------|----------|----------|
   | Data Warehouse | Data Warehouse rimanda alla copia dei dati di Analytics per l’archiviazione e i rapporti personalizzati, che si possono eseguire filtrando i dati. <p>Request Manager consente di visualizzare, duplicare e ridefinire le priorità delle richieste.</p> | [Gestire le richieste di Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=en) |
   | Activity Map | Activity Map è progettato per classificare l’attività di collegamento utilizzando le sovrapposizioni visive e fornire una dashboard di analisi in tempo reale per monitorare il coinvolgimento del pubblico delle pagine web. Consente di impostare visualizzazioni diverse per identificare visivamente l’accelerazione dell’attività del cliente, quantificare le iniziative di marketing e agire in base alle esigenze e ai comportamenti del pubblico. | [Panoramica di Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=it) |
   | Recommendations Classic | Recommendations è una funzione di Adobe Target che consente di visualizzare automaticamente prodotti, servizi o contenuti che potrebbero interessare i visitatori in base alle loro attività precedenti, preferenze o ad altri criteri. | [Raccomandazioni](https://experienceleague.adobe.com/docs/target/using/recommendations/recommendations.html?lang=en) |
   | Search&amp;Promote |  |  |
   | Mobile Services |  |  |
   | Dashboard di Analytics (app mobile) | L’app delle dashboard di Adobe Analytics fornisce ovunque e in qualsiasi momento informazioni provenienti da Adobe Analytics. Attraverso l’app, gli utenti possono visualizzare scorecard intuitive che crei utilizzando l’interfaccia utente desktop di Adobe Analytics. | L’app delle dashboard di Adobe Analytics nell’App Store iOS o nel Google Play store |
   | Report Builder | Adobe Report Builder è un componente aggiuntivo per Microsoft Excel. Consente di generare richieste personalizzate partendo da dati di Adobe Analytics, che puoi inserire in fogli di lavoro Excel. Le richieste possono fare riferimento in maniera dinamica a celle presenti nel tuo foglio di lavoro, inoltre hai la possibilità di aggiornare e personalizzare la presentazione dei dati da parte del Report Builder. | [Che cos’è Report Builder?](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=it) |

   {style="table-layout:auto"}

### Scheda Amministrazione

La scheda Amministratore include funzioni e opzioni di configurazione per l’amministrazione di Adobe Analytics.

1. In Adobe Analytics, seleziona la [!UICONTROL **Amministratore**] , quindi seleziona [!UICONTROL **Tutti gli amministratori**].

   ![Scheda Area di lavoro](assets/admin-tab.png)

2. Seleziona una delle seguenti funzioni del prodotto per configurarla:

   | Funzionalità del prodotto | Funzione | Ulteriori informazioni |
   |---------|----------|----------|
   | Utenti e risorse di Analytics | Mentre la maggior parte delle funzioni di gestione di utenti e prodotti sono ora disponibili solo nel [Adobe Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html), le funzioni amministrative di trasferimento delle risorse da un utente all’altro e di impostazione di una data di scadenza per un account utente sono disponibili solo nell’area di amministrazione di Adobe Analytics. | [Trasferimento di risorse utente o impostazione delle scadenze dell&#39;account](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=en) |
   | Migrazione degli ID utente | La migrazione degli ID utente di Analytics permette agli amministratori di trasferire facilmente gli account utente in Gestione utenti di Analytics ad Adobe Admin Console. | [Migrazione degli utenti di Analytics al Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/migrate-users/c-migration-tool.html?lang=it) |
   | Pagina principale gestione utenti (legacy) | La gestione di utenti e prodotti è stata spostata in Adobe Admin Console. Utilizza Adobe Admin Console per iniziare a gestire le autorizzazioni per gli utenti di Adobe Analytics. | [Analytics in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=it) |
   | Gruppi (legacy) | La gestione dei gruppi è stata spostata in Adobe Admin Console. Utilizza Adobe Admin Console per iniziare a gestire i gruppi per Adobe Analytics. | [Analytics in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=it) |
   | Accesso alle suite di rapporti | Il metodo per concedere l’accesso agli strumenti della suite di rapporti è stato spostato in Adobe Admin Console. Utilizza Adobe Admin Console per concedere l’accesso alla suite di rapporti agli utenti di Adobe Analytics. | [Autorizzazioni del profilo di prodotto per gli strumenti Report Suite](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/report-suite-tools.html?lang=en) |
   | Pagina principale degli strumenti di amministrazione |  |  |
   | Suite di rapporti | Consente di definire le regole che disciplinano il modo in cui i dati vengono elaborati in una suite di rapporti. | [Report Suite Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/report-suites-admin.html?lang=en) |
   | Utenti e risorse di Analytics | La gestione di utenti e risorse è stata spostata in Adobe Admin Console. Utilizza Adobe Admin Console per iniziare a gestire le autorizzazioni per gli utenti di Adobe Analytics. | [Analytics in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=it) |
   | Importazione classificazioni | Utilizza l’importazione per caricare le classificazioni in Adobe Analytics. È inoltre possibile esportare i dati per l’aggiornamento prima di un’importazione. | [Panoramica sull’importazione di classificazioni](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html?lang=en) |
   | Generatore di regole di classificazione | Invece di mantenere e caricare le classificazioni ogni volta che i codici di tracciamento cambiano, puoi creare classificazioni automatiche basate su regole e applicarle su più suite di rapporti. | [Flusso di lavoro di Generatore regole di classificazione](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-rulebuilder/classification-rule-builder.html?lang=en) |
   | Origini dati | Utilizzare Gestione origini dati per creare, modificare o disattivare origini dati. È inoltre possibile utilizzare questa interfaccia per tenere traccia dello stato dei file caricati nei percorsi FTP delle origini dati. | [Gestione delle origini dati](https://experienceleague.adobe.com/docs/analytics/import/data-sources/manage.html?lang=en) |
   | Gestione codici | Code Manager consente di scaricare il codice di raccolta dati per piattaforme web e mobili | [Gestore codici](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=it) |
   | Gestione del traffico | La pagina Gestione del traffico consente di specificare le modifiche previste per il volume di traffico. Queste impostazioni consentono ad Adobe di allocare le risorse appropriate per garantire che il traffico possa essere monitorato ed elaborato in modo tempestivo. | [Panoramica sulla gestione del traffico](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/traffic-management/traffic-management.html?lang=en) |
   | Utilizzo delle chiamate server | Una chiamata al server, nota anche come “hit” o “richiesta di immagine”, è un’istanza in cui i dati vengono inviati ai server di Adobe per essere elaborati. È disponibile un dashboard dell’utilizzo delle chiamate al server che tiene traccia dei dati di consumo delle chiamate al server e li confronta con il limite contrattuale. È possibile impostare avvisi per evitare interruzioni. | [Panoramica sull’utilizzo delle chiamate server](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
   | Registri | I file di registro sono utili per capire quando gli utenti accedono al sistema e per monitorarne l’accesso e l’utilizzo, le suite di rapporti e le modifiche dell’amministratore. | [Registri](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=it) |
   | Advertising Analytics | Configura Adobe Analytics per mostrare affiancati tutti i dati di Google e di Bing Paid Search. | [Configurare Advertising Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/advertising-analytics-config.html?lang=en) |
   | Feed di dati | I feed di dati offrono un modo potente per estrarre dati grezzi da Adobe Analytics. Puoi utilizzare i dati non elaborati in altre piattaforme al di fuori di Adobe, in base alle esigenze della tua organizzazione. | [Panoramica sui feed dati di Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=it) |
   | Escludi per indirizzo IP | Puoi escludere dai rapporti i dati di indirizzi IP specifici, ad esempio attività interne al sito web, test del sito e utilizzo dei dipendenti. L’esclusione dei dati migliora la precisione dei rapporti escludendo i dati dell’indirizzo IP. Inoltre, puoi rimuovere i dati da denial of service o altri eventi dannosi che possono distorcere i dati dei rapporti. Puoi configurare l’esclusione o utilizzando il firewall. | [Escludi per indirizzo IP](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html?lang=en) |
   | Pubblicazione di widget |  |  |
   | Reporting Activity Manager | Reporting Activity Manager consente di visualizzare la capacità di reporting per ogni suite di rapporti nell’organizzazione. Fornisce visibilità dettagliata sul consumo di reporting e consente di diagnosticare e risolvere facilmente i problemi di capacità durante i periodi in cui si verificano picchi di reporting. | [Reporting Activity Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
   | Etichettatura privacy governance dei dati | Etichettare i dati della suite di rapporti significa assegnare etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una determinata suite di rapporti. | [Etichettare i dati della suite di rapporti](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) |
   | Home Impostazioni società | La pagina Impostazioni società consente di configurare le impostazioni applicabili a tutte le suite di rapporti gestite dall’organizzazione. | [Panoramica delle impostazioni aziendali](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en) |
   | Gestione sicurezza | Security Manager consente di controllare l’accesso ai dati di reporting. Le opzioni includono password sicure, scadenza password, restrizioni di accesso IP e restrizioni del dominio e-mail. | [Sicurezza Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/security-manager.html?lang=en) |
   | Informazioni di supporto | La pagina Informazioni di supporto gestisce le informazioni di supporto visualizzate in Reports &amp; Analytics. Reports &amp; Analytics. <p>A partire dal 31 dicembre 2023, Adobe intende interrompere Reports &amp; Analytics e i relativi rapporti e funzioni. Ulteriori informazioni sull’[Annuncio sulla fine del ciclo di vita](https://www.adobe.com/go/analytics_rnaeol_it) di Reports &amp; Analytics.</p> |  |
   | Servizi Web | Le API dei servizi Web forniscono accesso programmatico ai rapporti di marketing e ad altri servizi della suite che consentono di duplicare e potenziare le funzionalità disponibili tramite l’interfaccia di Analytics. | [Servizi Web](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/web-services-admin.html?lang=en) |
   | Rapporti di Report Builder | Gestire la licenza assegnata agli utenti di Report Builder. | [Report del Report Builder](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/report-builder-reports-admin.html?lang=en) |
   | Servizio Single Sign-on | Il Single sign-on in Adobe Experience Cloud viene implementato tramite Admin Console. | [Analytics in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=it) |
   | Co-branding di Adobe Experience Cloud | La pagina Gestisci immagine co-branding ti consente di visualizzare il logo della tua azienda nei rapporti scaricati di Reports &amp; Analytics e nei dashboard legacy. Il Co-branding non viene utilizzato in Analysis Workspace.<p>A partire dal 31 dicembre 2023, Adobe intende interrompere Reports &amp; Analytics e i relativi rapporti e funzioni. Ulteriori informazioni sull’[Annuncio sulla fine del ciclo di vita](https://www.adobe.com/go/analytics_rnaeol_it) di Reports &amp; Analytics.</p> | [Co-branding](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/co-branding-admin.html?lang=en) |
   | Nascondere le suite di rapporti | Consente di nascondere le suite di rapporti nell’interfaccia utente di Adobe Analytics se non desideri più che una suite di rapporti sia disponibile per te e per i tuoi utenti. | [Nascondere suite di rapporti](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-hide-report-suites.html?lang=en) |  |

   {style="table-layout:auto"}

### Analysis Workspace

Analysis Workspace consente di realizzare rapidamente le analisi per raccogliere informazioni e condividerle con altri utenti. Utilizzando l’interfaccia di trascinamento del browser, puoi creare analisi, aggiungere visualizzazioni per mettere in risalto i dati, curare un set di dati, condividere e pianificare progetti con chiunque desideri.

L’immagine seguente e la tabella allegata illustrano alcune delle aree principali di Analysis Workspace.

Per una panoramica più dettagliata di Analysis Workspace, vedi [Panoramica di Analysis Workspace](/help/analyze/analysis-workspace/home.md).

![Panoramica di Analysis Workspace](assets/analysis-workspace-overvew.png)

| Posizione nell’immagine | Nome e funzione |
|---------|----------|
| A | **Barra all’estrema sinistra:** contiene schede per aggiungere pannelli, visualizzazioni e componenti in Analysis Workspace. Contiene anche l’icona del dizionario dati che viene utilizzata per aprirlo. |
| B | **Barra a sinistra:** a seconda della scheda selezionata nella barra all’estrema sinistra, quest’area contiene singoli pannelli, visualizzazioni o componenti. |
| C | **Area di lavoro:** questa è l’area principale in cui trascini il contenuto dalle barre a sinistra per creare il progetto. Il progetto viene aggiornato dinamicamente quando si aggiungono pannelli, visualizzazioni e componenti all’area di lavoro. |
| D | **Menu a discesa delle suite di rapporti:** per ogni pannello in Analysis Workspace, il menu a discesa della suite di rapporti consente di scegliere la suite di rapporti da utilizzare come origine dati. |

## Introduzione per amministratori, analisti, utenti finali e sviluppatori

In un’organizzazione tipica sono disponibili 3 tipi di utenti Adobe Analytics: amministratori, analisti e utenti finali.

Gli amministratori implementano e configurano Adobe Analytics; gli analisti impostano progetti e creano analisi utilizzando Analysis Workspace; gli utenti finali ottengono informazioni fruibili sui propri clienti, creando analisi proprie o lavorando con gli analisti per crearli.

Espandi le sezioni seguenti per scoprire come ciascuno di questi utenti può iniziare a utilizzare Adobe Analytics.

### Introduzione per gli amministratori

Gli amministratori di Analytics sono responsabili della scelta del metodo di implementazione più appropriato per la propria organizzazione.

Dopo aver implementato Adobe Analytics, gli amministratori devono eseguire varie attività di configurazione per garantire che gli analisti e gli utenti finali ottengano il massimo valore da Adobe Analytics. Gli amministratori devono inoltre monitorare regolarmente il proprio ambiente Analytics per garantire l’efficienza del sistema.

#### Determinare i tipi di dati da raccogliere

Adobe Analytics consente di raccogliere dati da più tipi di canali e di riunirli per fornire informazioni significative e in tempo reale sui clienti.

Di seguito sono riportati alcuni dei canali supportati in cui è possibile raccogliere i dati:

* Telefoni cellulari

* L&#39;Internet degli oggetti

* TV

* Assistenti vocali

* Auto collegate

* E molto altro (i nuovi canali supportati vengono aggiunti regolarmente)

Il [metodo di implementazione](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=it) scegliere determina il tipo di dati che è possibile raccogliere.

#### Implementazione di Adobe Analytics

Sono disponibili diversi metodi di implementazione per l’implementazione di Adobe Analytics sul sito web o sull’app mobile.

Per informazioni su ciascun metodo disponibile, vedi [Implementare Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=it).

| | Metodi di implementazione |
|---------|---------|
| **Siti Web** | <ul><li>Estensione Web SDK (consigliata)</li><li>SDK per web</li><li>Estensione Analytics</li><li>JavaScript legacy</li></ul> |
| **App mobili** | <ul><li>Estensione Mobile SDK (consigliata)</li><li>Estensione Analytics</li></ul> |

{style="table-layout:auto"}

#### Configurare Adobe Analytics

Prima di rendere Adobe Analytics disponibile agli utenti dell’organizzazione, gli amministratori di Analytics devono completare le seguenti attività:

| Attività | Uso previsto | Ulteriori informazioni |
|---------|----------|---------|
| Definire i ruoli di amministratore | Adobe Analytics supporta vari tipi di amministratori | [Ruoli di amministratore in Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=en) |
| Definire le autorizzazioni | Gli amministratori di Analytics devono assegnare i profili di prodotto nell’Admin Console per Adobe Analytics, Strumenti delle suite di rapporti e Strumenti di Analytics. | [Autorizzazioni di Analytics nell’Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=it) |
| Configurare le suite di rapporti e definire le impostazioni per la società | Una suite di rapporti è un silos di dati utilizzati da Adobe Analytics per generare rapporti.<p>Gli amministratori possono anche impostare [suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=it) per segmentare ulteriormente i dati.</p> | <ul><li>[Creare una suite di rapporti](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=en)</li><li>[Panoramica delle impostazioni aziendali](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=en)</li></ul> |
| Importare dati | Le origini dati di Adobe Analytics ti consentono di importare ulteriori dati online o offline a scopo di reporting. | [Panoramica sulle origini dati](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=en) |
| Classificare i dati con le classificazioni | Le classificazioni consentono di classificare i dati per un migliore utilizzo delle variabili, consentendo di includere più contenuto in una singola variabile. | |
| Gestire i componenti | Utilizza il dizionario dati e le aree di gestione per ciascun tipo di componente per definire quali componenti sono disponibili nell’implementazione di Analytics e quali sono approvati per la tua organizzazione.<p>Questa dovrebbe essere un’attività continua per garantire che i componenti vengano utilizzati in modo efficace all’interno della tua organizzazione. </p> | <ul><li>[Panoramica del dizionario dati](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=it)</li><li>[Gestione metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=en)</li><li>[Gestire i segmenti](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=it)</li><li>[Creazione di intervalli di date personalizzati](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=it)</li></ul> |
| Rilevamento delle anomalie | Il rilevamento anomalie fornisce un metodo statistico per determinare il cambiamento di una data metrica in relazione ai dati precedenti. | [Panoramica di Rilevamento delle anomalie](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=it) |
| Analisi contributi | L’analisi dei contributi riconosce pattern nascosti nei dati per spiegare le anomalie statistiche e identificare le correlazioni alla base di azioni inaspettate da parte del cliente, valori fuori dalla norma e improvvisi picchi o ribassi di metriche selezionate su segmenti di pubblico convergenti. | [Panoramica dell&#39;analisi dei contributi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html?lang=it) |
| Segmentazione di Analytics | Consente di creare, gestire, condividere e applicare segmenti di pubblico potenti e mirati ai tuoi rapporti utilizzando le funzionalità di Analytics, Adobe Experience Cloud, Adobe Target e altri prodotti Adobe integrati. | [Segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=it) |
| Pubblicare tipi di pubblico su Audienci Manager | | |
| Integrazioni | È possibile ottenere informazioni da altre applicazioni in Adobe Analytics. <p>Di seguito sono riportate alcune integrazioni comuni:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=en">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=it">Media Analytics</a></li> | |

{style="table-layout:auto"}

#### Monitorare Adobe Analytics

Sono disponibili diverse funzioni per aiutarti a monitorare il tuo ambiente Adobe Analytics.

Gli amministratori di Analytics devono essere a conoscenza delle seguenti funzioni disponibili per monitorare aspetti importanti dell’ambiente Analytics:

| Attività | Uso previsto | Ulteriori informazioni |
|---------|----------|---------|
| Reporting Activity Manager | Reporting Activity Manager consente di visualizzare la capacità di reporting per ogni suite di rapporti nell’organizzazione. Fornisce visibilità dettagliata sul consumo di reporting e consente di diagnosticare e risolvere facilmente i problemi di capacità durante i periodi in cui si verificano picchi di reporting. | [Reporting Activity Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=en) |
| Utilizzo delle chiamate server | Una chiamata al server, nota anche come “hit” o “richiesta di immagine”, è un’istanza in cui i dati vengono inviati ai server di Adobe per essere elaborati. È disponibile un dashboard dell’utilizzo delle chiamate al server che tiene traccia dei dati di consumo delle chiamate al server e li confronta con il limite contrattuale. È possibile impostare avvisi per evitare interruzioni. | [Panoramica sull’utilizzo delle chiamate server](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=en) |
| File di registro | I file di registro sono utili per capire quando gli utenti accedono al sistema e per monitorarne l’accesso e l’utilizzo, le suite di rapporti e le modifiche dell’amministratore. | [Registri](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=it) |

{style="table-layout:auto"}

### Introduzione per gli analisti

Anche se chiunque all’interno di un’organizzazione può utilizzare Adobe Analytics per ottenere informazioni fruibili sul comportamento dei clienti nei vari siti web e app, Adobe Analytics è progettato pensando agli analisti di dati.

Di seguito sono riportate le attività e le funzioni chiave che gli analisti devono conoscere per sfruttare appieno le potenzialità di Adobe Analytics e Analysis Workspace.

| Funzione | Uso previsto | Ulteriori informazioni |
|---------|----------|---------|
| Creare e condividere progetti in Analysis Workspace | Analysis Workspace è uno strumento basato su browser flessibile che consente di creare rapidamente le analisi e condividere i dati rilevati. Tramite un’interfaccia in cui è possibile eseguire semplici operazioni di trascinamento, puoi definire le analisi, aggiungere visualizzazioni per riprodurre i dati in modo facilmente comprensibili, curare un set di dati, condividere e pianificare progetti con chiunque all’interno della tua organizzazione.<p>Gli analisti di dati sono spesso responsabili della creazione di progetti in Analysis Workspace per gli utenti all’interno della loro organizzazione.</p><p>Una volta creati i progetti, gli analisti li condividono con [utenti finali](#end-users)(non analisti) nelle loro organizzazioni che hanno richiesto i dati e li aiutano a capire come interpretarli.</p> | <ul><li>[Creare progetti](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Condividere progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Attribution | Gli analisti possono personalizzare il modo in cui gli elementi dimensionali ottengono credito per gli eventi di successo utilizzando vari modelli di attribuzione e intervalli di lookback in Analysis Workspace.<p>I modelli di attribuzione lineare attribuiscono lo stesso credito a ogni punto di contatto che porta a una conversione, mentre First Touch attribuisce il pieno credito al primo punto di contatto. Sono disponibili molti altri modelli di attribuzione, tra cui il modello algoritmico che utilizza tecniche statistiche per determinare in modo dinamico l’allocazione ottimale del credito. </p> | [Modelli di attribuzione e finestre di lookback](/help/analyze/analysis-workspace/attribution/models.md) |
| Rilevamento delle anomalie | La modellazione statistica in Analysis Workspace trova automaticamente tendenze impreviste nei dati analizzando le metriche e determinando un limite inferiore, un limite superiore e un intervallo di valori previsto. Quando si verifica un picco o una caduta imprevista, il sistema ti avvisa nel rapporto. | [Panoramica di Rilevamento delle anomalie](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) |
| Analisi contributi | Utilizza Analysis Workspace per scoprire pattern nascosti all’interno dei tuoi dati per spiegare le anomalie statistiche e identificare le correlazioni alla base di azioni inaspettate dei clienti, valori fuori dalla norma e improvvisi picchi o ribassi di metriche tra segmenti di pubblico. | [Panoramica dell&#39;analisi dei contributi](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md) |
| Avvisi intelligenti | Crea e gestisci gli avvisi in base alle anomalie nei dati e agli avvisi &quot;impilati&quot; che acquisiscono più metriche in un singolo avviso. | [Panoramica degli avvisi intelligenti](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md) |
| Esportazione dati | I feed di dati e Data Warehouse consentono di esportare dati in varie destinazioni cloud, ad esempio Google Cloud Platform, Azure RBAC, Azure SAS e Amazon S3. | [Guida all’esportazione di Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=it) |
| Activity Map | Activity Map è un’applicazione di Adobe Analytics progettata per classificare l’attività dei collegamenti utilizzando sovrapposizioni visive e fornire una dashboard di analisi in tempo reale per monitorare il coinvolgimento del pubblico nelle pagine web.<p>Activity Map ti permette di configurare varie viste per identificare visivamente l’accelerazione dell’attività dei clienti, quantificare le iniziative di marketing e intervenire sulle esigenze e i comportamenti del tuo pubblico.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=it) |
| Report Builder | Report Builder è un componente aggiuntivo per Microsoft Excel. Il Report Builder ti consente di generare richieste personalizzate a partire da dati di Adobe Analytics inseriti nei tuoi fogli di lavoro Excel. Le richieste possono fare riferimento in maniera dinamica a celle presenti nel tuo foglio di lavoro, inoltre hai la possibilità di aggiornare e personalizzare la presentazione dei dati da parte del Report Builder. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=it) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

### Introduzione per gli utenti finali

Gli utenti finali che non sono analisti professionisti possono lavorare con gli analisti della propria organizzazione per sfruttare appieno le potenzialità di Adobe Analytics e Analysis Workspace, oppure possono imparare le basi di Analysis Workspace per iniziare a ottenere informazioni fruibili sui propri clienti.

#### Lavorare con gli analisti

In genere, gli utenti di un’organizzazione che sono interessati a saperne di più sul comportamento dei clienti nei loro vari siti non sono analisti professionisti.

Idealmente, questi utenti dovrebbero lavorare con [analisti](#analysts) all’interno di un’organizzazione per:

1. Definisci i requisiti per le analisi spiegando all’analista cosa spera di imparare sui clienti.

1. Rivedere le analisi per garantire che soddisfino gli obiettivi.

1. Discutere i dati ottenuti dalle analisi.

1. Modificate le analisi in base alle esigenze nel tempo.

#### Creazione di analisi in Analysis Workspace

Non è necessario essere un analista di dati per ottenere informazioni fruibili da Adobe Analytics.

Alcuni utenti potrebbero ritenere utile lavorare con un analista di dati per configurare un progetto in Analysis Workspace e spiegare come interpretare i dati, come descritto in [Lavorare con gli analisti](#work-with-analysts); altri utenti potrebbero avere familiarità con la creazione del progetto e con l’interpretazione dei dati stessi.

Analysis Workspace consente di realizzare rapidamente le analisi per raccogliere informazioni e condividerle con altri utenti. Utilizzando l’interfaccia di trascinamento del browser, puoi creare analisi, aggiungere visualizzazioni per mettere in risalto i dati, curare un set di dati, condividere e pianificare progetti con chiunque desideri.

Per informazioni su come creare analisi in Analysis Workspace, consulta [Panoramica di Analysis Workspace](/help/analyze/analysis-workspace/home.md).

### Introduzione per sviluppatori

[Le API di Analytics ti consentono di chiamare direttamente i server di Adobe per eseguire quasi tutte le azioni possibili nell’interfaccia utente.](https://developer.adobe.com/analytics-apis/docs/2.0/)

Puoi creare rapporti da esplorare, ottenere informazioni o rispondere a domande importanti sui tuoi dati. Puoi anche gestire i componenti di Adobe Analytics, ad esempio la creazione di segmenti o di metriche calcolate.

## Video introduttivo

Per informazioni sulle nozioni di base di Adobe Analytics, consulta questa *Introduzione ad Adobe Analytics - Webinar Skill Builder* video. Il video illustra le nozioni di base su come acquisire i dati, come inviarli ad Adobe Analytics e quali funzionalità di visualizzazione puoi utilizzare in Adobe Analytics. Il video offre una base per creare, distribuire, raccogliere e interpretare i dati, consentendoti di fornire informazioni fruibili e consigli basati sui dati raccolti.

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Per domande sullo strumento da utilizzare, consulta [Quale strumento Adobe Analytics usare?](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html?lang=it).

## Ulteriori informazioni con il Customer Journey Analytics

Customer Journey Analytics è la soluzione Analytics di nuova generazione di Adobe che consente di sfruttare la potenza di Analysis Workspace con i dati provenienti da Adobe Experience Platform. Tale funzionalità può suddividere, filtrare, eseguire query e visualizzare anni di dati e si abbina alla capacità della Platform di contenere tutti i tipi di schemi e di tipologie di dati.

Di seguito sono riportati alcuni dei vantaggi del Customer Journey Analytics rispetto ad Adobe Analytics:

* **Variabili ed eventi illimitati**: i concetti di eVar, prop ed eventi non esistono più. I dati sono principalmente incentrati su dimensioni e metriche. I set di dati possono disporre di un numero illimitato di dimensioni e metriche univoche.

* **Valori univoci illimitati**: Adobe Experience Platform non è vincolata ad alcun limite univoco.

* **Modifica dei dati storici**: con Adobe Experience Platform è possibile rimuovere o correggere i dati.

* **Dati di più suite di rapporti**: in Platform è possibile combinare le implementazioni esistenti da più set di dati.

Per ulteriori informazioni, consulta [Panoramica del Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it).

