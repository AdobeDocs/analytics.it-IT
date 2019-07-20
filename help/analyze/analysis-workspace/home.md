---
description: Come iniziare a utilizzare Adobe Analytics.
keywords: Analysis Workspace
seo-description: Come iniziare a utilizzare Adobe Analytics.
seo-title: Guida introduttiva
solution: Analytics
title: Guida introduttiva
topic: Reports & Analytics
uuid: 851 feadb -5 e 30-45 ab -9 f 66-02 bdf 844 fa 54
translation-type: tm+mt
source-git-commit: a0158b98089c044091f61796d782604865aa4eba

---


# Analysis Workspace

Analysis Workspace è uno degli strumenti di punta di Adobe per prendere decisioni basate su dati per la tua organizzazione. La visualizzazione più comune, la tabella a forma libera, consente di creare facilmente rapporti personalizzati utilizzando dimensioni, metriche, segmenti e intervalli di date.

## Prerequisiti

[Invia dati ad Adobe Analytics utilizzando Adobe Experience Platform Launch](../../implement/implement-with-launch/validate-publish-prod.md): L'utilizzo di Analysis Workspace richiede un'implementazione funzionante. Assicuratevi che la vostra organizzazione invii dati ad Adobe prima di usare lo strumento. Altre implementazioni, come DTM o implementazioni manuali precedenti, possono funzionare anche.

## Estrarre un rapporto classifica di base in Workspace

Estrai un rapporto di base con Analysis Workspace. Un rapporto classifica mostra una visualizzazione totale aggregata di ciascun valore di dimensione, mostrando prima i valori più grandi. Questi tipi di rapporti sono utili per vedere quali componenti del sito sono più efficaci, ad esempio quali pagine ottengono più traffico o quali prodotti più venduti.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Fai clic sull'icona 9 quadrati in alto a destra, quindi fai clic sul logo di Analytics colorato.
3. Nella barra di navigazione superiore, fate clic su Area di lavoro.
4. Fate clic sul pulsante Crea nuovo progetto.
5. Nella finestra a comparsa modale, accertatevi che «Blank Project» sia selezionato, quindi fate clic su Create (Crea).
6. A sinistra viene visualizzato un elenco di dimensioni, metriche, segmenti e intervalli di date. Individua la dimensione Pagine (colorato arancione) e trascinala sul quadro in cui riporta «Rilascia una dimensione qui».
7. Se la suite di rapporti dispone di dati, è possibile visualizzare un report che mostra le pagine principali di questo mese. Analysis Workspace automatically populated the report with the [Occurrences](../../components/c-variables/c-metrics/metrics-occurrences.md) metric.
8. Locate the Visits metric (colored green), and drag it either **over** or **next to** the Occurrences metric header (avoid placing it above the metric). Se trascini la metrica Visite sopra Occorrenze, la metrica viene sostituita nei rapporti. Se trascini la metrica Visite accanto ad Occorrenze, entrambe le metriche vengono visualizzate affiancate.
9. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## Estrarre un report con tendenze di base in Workspace

Estrai un report con tendenze di base utilizzando Analysis Workspace. Un rapporto con tendenze mostra una visualizzazione temporale delle metriche utilizzando l'intervallo di date selezionato. Questi tipi di report sono utili per identificare le tendenze nel tempo e possono essere utilizzate per misurare il successo o il successo delle decisioni aziendali effettuate. Ad esempio, potete osservare un report di visualizzazione delle pagine con tendenze nel tempo per verificare se una riprogettazione del sito ha contribuito a aumentare o diminuire il traffico.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
2. Fai clic sull'icona 9 quadrati in alto a destra, quindi fai clic sul logo di Analytics colorato.
3. Nella barra di navigazione superiore, fate clic su Area di lavoro.
4. Fate clic sul pulsante Crea nuovo progetto.
5. Nella finestra a comparsa modale, accertatevi che «Blank Project» sia selezionato, quindi fate clic su Create (Crea).
6. A sinistra viene visualizzato un elenco di dimensioni, metriche, segmenti e intervalli di date. Individua la dimensione Visualizzazioni pagina e trascinala nello spazio piccolo sul quadro etichettata «Rilascia una metrica qui». Evitate di rilasciarlo nello spazio riservato alle dimensioni (almeno per questo esercizio).
7. Tieni presente che se la suite di rapporti dispone di dati, dovresti vedere un rapporto di base sulle visualizzazioni delle pagine nel mese in corso. Analysis Workspace è stato portato automaticamente all'intervallo date «Giorno» per visualizzare la tendenza delle visualizzazioni di pagina per il mese corrente.
8. Individua l'intervallo date Settimana (viola colorato) nell'elenco dei componenti intervallo date a sinistra. Fai clic sul titolo dell'intervallo di date per espandere e visualizzare tutti i componenti dell'intervallo di date oppure usa la barra di ricerca.
9. Trascina l'intervallo date Settimana sull'intestazione dell'intervallo giorno giorno per sostituirlo.
10. Tieni presente che il report con tendenze ora viene aggregato per settimana invece che per giorno.
11. If you'd like to save your project, click *[!UICONTROL Project]&gt;[!UICONTROL Save]* in the upper left menu.

## Provare con lo strumento

Analysis Workspace è uno strumento di reporting che non ha alcun impatto sulla raccolta dei dati. Non ci sono conseguenze per trascinare in modo indiscriminato componenti in un progetto per vedere cosa funziona. Per visualizzare le funzionalità disponibili, trascinate diverse combinazioni di dimensioni e metriche nel progetto dell'area di lavoro.

Se trascinate accidentalmente un componente non valido nel progetto dell'area di lavoro o desiderate tornare indietro di un passo, premete Ctrl + Z (Windows) o Comando + Z (Mac) per annullare l'ultima azione effettuata. You can also start with a clean slate by clicking *[!UICONTROL Project]&gt;[!UICONTROL New]* in the upper left menu.

## Risoluzione dei problemi   

**Quando trascino una metrica, viene indicato «Dati non validi».**

I dati non validi indicano che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel report. Ad esempio, due metriche sovrapposte l'una all'altra non possono essere restituite come dati, in quanto non è possibile visualizzare due metriche in tal modo. Posizionate le metriche affiancate.

**Quando trascino una metrica su, non visualizzi dati effettivi, semplicemente zeri.**

Se create un rapporto di workspace con esito positivo ma non vi sono dati, potete controllare quanto segue:

* Controlla la suite di rapporti e verifica che sia composta di dati.
* Se utilizzi un segmento nel rapporto, i criteri del segmento potrebbero non corrispondere ad alcun dato. Prova a rimuovere il segmento o a regolare la definizione del segmento.
* Controllate l'intervallo di date in alto a destra e verificate che sia impostato su un valore previsto.
* Individuare il sito Web e utilizzare il Debugger per convalidare la raccolta dei dati.

## Risorse aggiuntive

* [Note sulla versione di Analysis Workspace](../../analyze/analysis-workspace/new-features-in-analysis-workspace.md): Leggi le funzioni più recenti introdotte nello strumento.
* [Analysis Workspace su YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Scopri come usare la maggior parte delle funzionalità in Analysis Workspace tramite questa sequenza di brani estesa.
* Suggerimenti sui prodotti: Le punte del giorno, insieme ai brevi video, talvolta appaiono nell'angolo inferiore destro di Analysis Workspace. If these tips are dismissed, they can be reached through *[!UICONTROL Help]&gt;[!UICONTROL Tips]* at any time.
* [Community di Analysis Workspace](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): Parla di Analysis Workspace con altri utenti e votate le funzionalità che desiderate visualizzare nello strumento.
* Post blog:
   * [Un’analisi più intelligente per dare più strumenti alle aziende](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Le nuove funzioni di Adobe Analytics rendono ancora più accessibili dati e informazioni](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [5 suggerimenti per massimizzare la produttività con Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Approfondimenti rapidi con Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Perché utilizzare Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Passaggi successivi

Sono disponibili numerose indicazioni per approfondire le conoscenze di Analysis Workspace. Di seguito sono riportati alcuni concetti fondamentali consigliati da Adobe:

### Per gli utenti finali che desiderano ampliare le conoscenze su come utilizzare Analysis Workspace

* [Dettagli sull'interfaccia utente di Workspace](../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md): Ora che hai creato un rapporto di base, acquisisci familiarità con il resto dell'interfaccia.
* [Visualizzazioni in Workspace](visualizations/freeform-analysis-visualizations.md): Le tabelle a forma libera sono semplicemente un tipo di visualizzazione in Analysis Workspace. Scopri come utilizzare altre visualizzazioni, ad esempio grafici a linee, grafici a barre e mappe geografiche.
* [Dimensioni in Workspace](../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Scopri di più sulle dimensioni e su come utilizzarle in più di semplici rapporti.
* [Metriche in Workspace](../../analyze/analysis-workspace/components/apply-create-metrics.md): Scopri di più sulle metriche e su come utilizzarle in altre parti delle tabelle a forma libera.
* [Introduzione alla segmentazione](../../analyze/analysis-workspace/components/t-freeform-project-segment.md): Scopri i segmenti e invoca un rapporto di base con un segmento.
* [Intervalli di date in Workspace](../../analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Informazioni su date relative e continue e utilizzarle nei progetti dell'area di lavoro.
* Condivisione di progetti in Workspace: Mostra al tuo collega il fantastico progetto Workspace che hai creato.
* [(Avanzata) Pannelli in Workspace](c-panels/panels.md): Usa funzioni avanzate in Workspace, ad esempio Attribuzione e Confronto segmenti.

### Per gli analisti e gli amministratori che desiderano migliorare la qualità dell'area di lavoro nella propria organizzazione

* [Autorizzazioni Area di lavoro Analisi](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html): Assegna autorizzazioni agli utenti in Workspace tramite Adobe Admin Console.
* [Creare un documento di progettazione della soluzione](../../implement/prepare/solution-design.md): Inizia a pianificare in che modo l'organizzazione raccoglie dimensioni o metriche aggiuntive specifiche del sito.
* [Modelli in Workspace](../../analyze/analysis-workspace/build-workspace-project/starter-projects.md): Crea modelli in modo che i tuoi colleghi possano iniziare con uno spazio progetto adatto alle loro esigenze.
* [Gestione area di lavoro](curate-share/curate.md): Creare un progetto che limiti i componenti disponibili, rendendo l'area di lavoro più accessibile a chi ha meno esperienza con lo strumento