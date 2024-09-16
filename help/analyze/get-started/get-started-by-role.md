---
description: Informazioni generali di panoramica su Adobe Analytics, tra cui informazioni sull’interfaccia di Analytics e informazioni introduttive per amministratori, analisti, utenti e sviluppatori.
title: Introduzione per amministratori, analisti, utenti finali e sviluppatori
feature: Analytics Basics
exl-id: 11800de5-224a-4bd2-8cb1-a6318925db71
source-git-commit: 2b8688da1400857b7f5093197d06c04681cd87ff
workflow-type: tm+mt
source-wordcount: '1694'
ht-degree: 100%

---

# Introduzione per amministratori, analisti, utenti finali e sviluppatori

In un’organizzazione tipica sono disponibili 4 tipi di utenti Adobe Analytics:

* **Amministratori:** implementano e configurano Adobe Analytics.

* **Analisti:** impostano i progetti e creano le analisi con Analysis Workspace.

* **Utenti finali:** ottengono informazioni actionable sui propri clienti, creando le proprie analisi o collaborando con gli analisti per crearle.

* **Sviluppatori:** utilizzano le API 2.0 di Adobe Analytics per chiamare direttamente i server di Adobe ed eseguire quasi tutte le azioni passibili di esecuzione nell’interfaccia utente, ad esempio la creazione di rapporti da esplorare, il recupero di informazioni o la risposta a domande importanti sui dati.

Le informazioni riportate di seguito illustrano come ciascuno di questi utenti può iniziare a utilizzare Adobe Analytics.

## Introduzione per amministratori

Gli amministratori di Analytics sono responsabili della scelta del metodo di implementazione più appropriato per la propria organizzazione.

Dopo aver implementato Adobe Analytics, gli amministratori devono eseguire varie attività di configurazione per garantire che gli analisti e gli utenti finali possano valorizzare al massimo Adobe Analytics. Gli amministratori devono inoltre monitorare regolarmente il proprio ambiente Analytics, per garantire l’efficienza del sistema.

### Determinare i tipi di dati da raccogliere

Adobe Analytics consente di raccogliere dati da più tipi di canali e di riunirli per fornire approfondimenti significativi e in tempo reale sulla clientela.

Di seguito sono riportati alcuni dei canali supportati in cui è possibile raccogliere i dati:

* Telefoni cellulari

* L’Internet of Things

* TV

* Assistenti vocali

* Veicoli connessi

* E molto altro (i nuovi canali supportati vengono aggiunti regolarmente)

Il [metodo di implementazione](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=it) che scegli determina il tipo di dati che è possibile raccogliere.

### Implementare Adobe Analytics

Per implementare Adobe Analytics sul sito web o sull’app mobile sono disponibili diversi metodi.

Per informazioni su ciascun metodo disponibile, consulta [Implementare Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=it).

| | Metodi di implementazione |
|---------|---------|
| **Siti Web** | <ul><li>Estensione Web SDK (consigliata)</li><li>Web SDK</li><li>Estensione Analytics</li><li>JavaScript legacy</li></ul> |
| **App mobili** | <ul><li>Estensione Mobile SDK (consigliata)</li><li>Estensione Analytics</li></ul> |

{style="table-layout:auto"}

### Configurare Adobe Analytics

Prima di rendere Adobe Analytics disponibile agli utenti dell’organizzazione, gli amministratori di Analytics devono completare le seguenti attività:

| Attività | Uso previsto | Ulteriori informazioni |
|---------|----------|---------|
| Definire i ruoli di amministratore | Adobe Analytics supporta vari tipi di amministratori | [Ruoli di amministratore in Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/admin-roles-in-analytics.html?lang=it) |
| Definire le autorizzazioni | Gli amministratori di Analytics devono assegnare i profili di prodotto in Admin Console per Adobe Analytics, Strumenti delle suite di rapporti e Strumenti di Analytics. | [Autorizzazioni Analytics in Admin Console](/help/admin/admin-console/permissions/analytics-tools.md) |
| Configurare le suite di rapporti e definire le impostazioni per la propria azienda | Una suite di rapporti è un silos di dati utilizzati da Adobe Analytics per generare i rapporti.<p>Gli amministratori possono anche configurare [suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=it) per segmentare ulteriormente i dati.</p> | <ul><li>[Creare una suite di rapporti](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/c-new-report-suite/t-create-a-report-suite.html?lang=it)</li><li>[Panoramica delle impostazioni aziendali](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/company-settings/c-company-settings.html?lang=it)</li></ul> |
| Importare dati | Le origini dati Adobe Analytics ti consentono di importare manualmente altri dati online e offline per il reporting. | [Panoramica sulle origini dati](https://experienceleague.adobe.com/docs/analytics/import/data-sources/overview.html?lang=it) |
| Classificare i dati con le classificazioni | Le classificazioni consentono di classificare i dati per un migliore utilizzo delle variabili, permettendo di includere più contenuto in una singola variabile. | [Panoramica delle classificazioni](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=it) |
| Gestire i componenti | Utilizza il dizionario dati e le aree di gestione per ciascun tipo di componente per definire quali di essi sono disponibili nell’implementazione di Analytics e quali sono approvati per la tua organizzazione.<p>Questa dovrebbe essere un’attività continua per garantire che i componenti vengano utilizzati in modo efficace all’interno della tua organizzazione. </p> | <ul><li>[Panoramica del dizionario dati](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.html?lang=it)</li><li>[Gestione metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=it)</li><li>[Gestire i segmenti](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=it)</li><li>[Creare di intervalli di date personalizzati](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html?lang=it)</li></ul> |
| Rilevamento delle anomalie | Il rilevamento anomalie fornisce un metodo statistico per determinare come una particolare metrica è cambiata in relazione ai dati precedenti. | [Panoramica del rilevamento anomalie](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=it) |
| Analisi dei contributi | L’analisi dei contributi riconosce pattern nascosti nei dati per spiegare le anomalie statistiche e identificare le correlazioni alla base di azioni inaspettate da parte della clientela, valori fuori dalla norma e improvvisi picchi o ribassi di metriche selezionate su segmenti di pubblico convergenti. | [Panoramica dell’analisi dei contributi](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) |
| Segmentazione di Analytics | Ti consente di creare, gestire, condividere e applicare segmenti di pubblico efficaci e mirati ai tuoi rapporti utilizzando le funzionalità di Analytics, Adobe Experience Cloud, Adobe Target e altri prodotti Adobe integrati. | [Segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=it) |
| Pubblicare tipi di pubblico su Audience Manager | Adobe Audience Manager è una potente piattaforma di gestione dei dati che consente di creare profili di pubblico univoci da integrazioni di dati di prime, seconde e terze parti (partner). | [Panoramica di Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=it) |
| Integrazioni | È possibile far emergere le informazioni da altre applicazioni in Adobe Analytics. <p>Di seguito sono riportate alcune integrazioni comuni:</p><ul><li><a href="https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=it">Analytics for Target</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=it">Componente aggiuntivo Streaming Media Collection</a></li> | [Integrazione di Analytics](https://experienceleague.adobe.com/docs/analytics/integration/home.html?lang=it) |

{style="table-layout:auto"}

### Monitoraggio di Adobe Analytics

Sono disponibili diverse funzioni per aiutarti a monitorare l’ambiente Adobe Analytics.

Gli amministratori di Analytics devono essere a conoscenza delle seguenti funzioni disponibili per monitorare aspetti importanti dell’ambiente Analytics:

| Attività | Uso previsto | Ulteriori informazioni |
|---------|----------|---------|
| Reporting Activity Manager | Il Reporting Activity Manager ti consente di visualizzare la capacità di reporting per ogni suite di rapporti della tua organizzazione. Offre una visibilità dettagliata sul consumo di reporting e ti aiuta a diagnosticare e risolvere facilmente i problemi di capacità durante i periodi in cui si verificano picchi di reporting. | [Reporting Activity Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/reporting-activity.html?lang=it) |
| Utilizzo chiamate al server | Una chiamata al server, nota anche come “hit” o “richiesta di immagine”, è un’istanza in cui i dati vengono inviati ai server di Adobe per essere elaborati. È disponibile una dashboard dell’utilizzo delle chiamate al server che tiene traccia dei dati di consumo delle chiamate al server e li confronta con il limite contrattuale. È possibile impostare avvisi per evitare le eccedenze. | [Panoramica sull’utilizzo delle chiamate al server](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-call-usage/overage-overview.html?lang=it) |
| File di registro | I file di registro sono utili per capire quando gli utenti accedono al sistema e per monitorarne l’accesso e l’utilizzo, le suite di rapporti e le modifiche dell’amministratore. | [Registri](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=it) |

{style="table-layout:auto"}

## Introduzione per gli analisti

Anche se chiunque all’interno di un’organizzazione può utilizzare Adobe Analytics per ottenere approfondimenti fruibili sul comportamento della clientela nei vari siti web e app, Adobe Analytics è progettato pensando agli analisti di dati.

Di seguito sono riportate le attività e le funzioni chiave che gli analisti devono conoscere per sfruttare appieno le potenzialità di Adobe Analytics e Analysis Workspace.

| Funzionalità | Uso previsto | Ulteriori informazioni |
|---------|----------|---------|
| Creare e condividere progetti in Analysis Workspace | Analysis Workspace è uno strumento basato su browser flessibile che consente di creare rapidamente le analisi e condividere i dati rilevati. Tramite un’interfaccia in cui è possibile eseguire semplici operazioni di trascinamento, puoi definire le analisi, aggiungere visualizzazioni per riprodurre i dati in modo facilmente comprensibili, curare un set di dati, condividere e pianificare progetti con chiunque all’interno della tua organizzazione.<p>Gli analisti di dati sono spesso responsabili della creazione di progetti in Analysis Workspace per gli utenti all’interno della loro organizzazione.</p><p>Una volta creati i progetti, gli analisti li condividono con gli [utenti finali](#end-users) (non analisti) nelle loro organizzazioni che hanno richiesto i dati e li aiutano a capire come interpretarli.</p> | <ul><li>[Creare progetti](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[Condividere progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| Attribuzione | Gli analisti possono personalizzare il modo in cui agli elementi dimensionali deve essere attribuito il merito per gli eventi di successo utilizzando vari modelli di attribuzione e intervalli di lookback in Analysis Workspace.<p>I modelli di attribuzione lineare attribuiscono lo stesso credito a ogni punto di contatto che porta a una conversione, mentre quelli di primo contatto attribuiscono tutto il merito al primo punto di contatto. Sono disponibili molti altri modelli di attribuzione, tra cui il modello algoritmico che utilizza tecniche statistiche per determinare in modo dinamico l’allocazione ottimale del credito. </p> | [Modelli di attribuzione e intervalli di lookback](/help/analyze/analysis-workspace/attribution/models.md) |
| Rilevamento delle anomalie | La modellazione statistica in Analysis Workspace trova automaticamente tendenze impreviste nei dati analizzando le metriche e determinando un limite inferiore, un limite superiore e un intervallo di valori previsto. Quando si verifica un picco o un calo imprevisto, il sistema ti avvisa nel rapporto. | [Panoramica del rilevamento anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| Analisi dei contributi | Utilizza Anaysis Workspace per scoprire pattern nascosti nei dati, spiegare anomalie statistiche e individuare correlazioni alla base di azioni inaspettate da parte della clientela, valori fuori dalla norma e improvvisi picchi o cali delle metriche sui segmenti di pubblico. | [Analisi contributi](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) in [Panoramica del rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| Avvisi intelligenti | Crea e gestisci gli avvisi in base ad anomalie nei dati e ad avvisi “impilati” che raccolgono più metriche in un singolo avviso. | [Panoramica degli avvisi intelligenti](/help/components/c-alerts/intellligent-alerts.md) |
| Esportazione dei dati | Le funzioni Feed di dati e Data warehouse consentono di esportare dati in varie destinazioni cloud, ad esempio Google Cloud Platform, Azure RBAC, Azure SAS e Amazon S3. | [Guida all’esportazione di Analytics](https://experienceleague.adobe.com/docs/analytics/export/home.html?lang=it) |
| Activity Map | Activity Map è un’applicazione di Adobe Analytics progettata per classificare l’attività dei collegamenti utilizzando sovrapposizioni visive e fornire una dashboard di analisi in tempo reale per monitorare il coinvolgimento del pubblico nelle pagine web.<p>Activity Map ti permette di configurare varie viste per identificare visivamente l’accelerazione dell’attività dei clienti, quantificare le iniziative di marketing e intervenire sulle esigenze e i comportamenti del tuo pubblico.</p> | [Activity Map](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/activity-map.html?lang=it) |
| Report Builder | Report Builder è un componente aggiuntivo per Microsoft Excel. Il Report Builder ti consente di generare richieste personalizzate a partire da dati di Adobe Analytics inseriti nei tuoi fogli di lavoro Excel. Le richieste possono fare riferimento in maniera dinamica a celle presenti nel tuo foglio di lavoro, inoltre hai la possibilità di aggiornare e personalizzare la presentazione dei dati da parte del Report Builder. | [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=it) |

{style="table-layout:auto"}

<!-- * Realtime reporting? -->

## Introduzione per gli utenti finali

Gli utenti finali che non sono analisti professionisti possono lavorare con gli analisti della propria organizzazione per sfruttare appieno le potenzialità di Adobe Analytics e Analysis Workspace, oppure possono imparare le basi di Analysis Workspace per iniziare a ottenere informazioni approfondite fruibili sulla propria clientela.

### Lavorare con gli analisti

In genere, gli utenti di un’organizzazione che sono interessati a saperne di più sul comportamento dei clienti sui vari siti non sono analisti professionisti.

Idealmente, tali utenti dovrebbero lavorare con gli [analisti](#analysts) all’interno della propria organizzazione per:

1. Definire i requisiti delle analisi spiegando all’analista cosa si desidera sapere sui clienti.

1. Rivedere le analisi per garantire che soddisfino gli obiettivi.

1. Discutere i dati ottenuti dalle analisi.

1. Modificare le analisi in base alle esigenze nel tempo.

### Creare analisi in Analysis Workspace

Non è necessario essere analista di dati per ottenere informazioni approfondite fruibili da Adobe Analytics.

Per alcuni utenti potrebbe essere utile lavorare con un analista di dati per configurare un progetto in Analysis Workspace e spiegare come interpretare i dati, come descritto in [Lavorare con gli analisti](#work-with-analysts); altri utenti potrebbero essere in grado di occuparsi direttamente della creazione di un progetto e dell’interpretazione dei dati.

Analysis Workspace consente di realizzare rapidamente le analisi per raccogliere informazioni e condividerle con altri utenti. Utilizzando l’interfaccia di trascinamento del browser, puoi creare analisi, aggiungere visualizzazioni per mettere in risalto i dati, curare un set di dati, condividere e pianificare progetti con chiunque desideri.

Per informazioni su come creare analisi in Analysis Workspace, consulta [Panoramica di Analysis Workspace](/help/analyze/analysis-workspace/home.md).

## Introduzione per gli sviluppatori

[Le API di Analytics consentono di chiamare direttamente i server di Adobe per eseguire quasi tutte le azioni possibili nell’interfaccia utente.](https://developer.adobe.com/analytics-apis/docs/2.0/)

Puoi creare rapporti da esplorare, ottenere informazioni o rispondere a domande importanti sui tuoi dati. Puoi anche gestire i componenti di Adobe Analytics, ad esempio la creazione di segmenti o di metriche calcolate.
