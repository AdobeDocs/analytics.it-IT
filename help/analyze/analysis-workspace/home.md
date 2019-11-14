---
description: Come iniziare a utilizzare Adobe Analytics.
keywords: Analysis Workspace
solution: Analytics
title: Guida introduttiva
topic: Reports and analytics
uuid: 851feadb-5e30-45ab-9f66-02bdf844fa54
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analysis Workspace

Analysis Workspace è uno degli strumenti di punta di Adobe per adottare decisioni basate sui dati utilizzabili a livello aziendale. La visualizzazione più comune, la tabella a forma libera, consente di creare facilmente rapporti personalizzati utilizzando dimensioni, metriche, segmenti e intervalli di date.

## Prerequisiti

[Invia dati ad Adobe Analytics tramite Adobe Experience Platform Launch](/help/implement/implement-with-launch/validate-publish-prod.md): L’utilizzo di Analysis Workspace richiede un’implementazione efficace. Prima di utilizzare lo strumento, assicurarsi che l'organizzazione invii dati ad Adobe. Possono funzionare anche altre implementazioni, come DTM o implementazioni manuali precedenti.

## Ottenere un report classifica di base in Workspace

Richiama un report classifica di base utilizzando Analysis Workspace. Un rapporto con classifica mostra una visualizzazione totale aggregata di ciascun valore di dimensione, con i valori più grandi. Questi tipi di rapporti sono utili per vedere quali componenti del sito sono più efficaci, ad esempio quali pagine ottengono il maggior traffico o quali prodotti vendono di più.

1. Accedete a [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali ID Adobe.
2. Fate clic sull'icona di 9 quadrati in alto a destra, quindi fate clic sul logo Analytics colorato.
3. Nella barra di navigazione superiore, fate clic su Area di lavoro.
4. Fate clic sul pulsante "Crea nuovo progetto".
5. Nella finestra a comparsa modale, assicurarsi che sia selezionato "Progetto vuoto", quindi fare clic su Crea.
6. A sinistra è visualizzato un elenco di dimensioni, metriche, segmenti e intervalli di date. Individuate la dimensione Pagine (arancione colorata) e trascinatela sull’area di lavoro dove è indicato "Rilascia qui una dimensione".
7. Se la suite di rapporti contiene dei dati, è possibile visualizzare un rapporto che mostra le pagine principali per questo mese. Analysis Workspace popolava automaticamente il rapporto con la metrica [Occorrenze](/help/components/c-variables/c-metrics/metrics-occurrences.md) .
8. Individuate la metrica Visite (verde colorato) e trascinatela **sopra** o **accanto all** ’intestazione della metrica Occorrenze (evitate di posizionarla sopra la metrica). Se trascinate la metrica Visite sopra a Occorrenze, la metrica viene sostituita nel reporting. Se trascinate la metrica Visite accanto a Occorrenze, entrambe le metriche vengono visualizzate affiancate.
9. Per salvare il progetto, fate clic su *[!UICONTROL Project]&gt;[!UICONTROL Save]* in alto a sinistra.

## Estrazione di un rapporto con tendenze di base in Workspace

Richiama un report con tendenze di base tramite Analysis Workspace. Un rapporto con tendenze mostra una visualizzazione temporale delle metriche utilizzando l'intervallo di date selezionato. Questi tipi di report sono utili per identificare le tendenze nel tempo e possono essere utilizzati per misurare il successo o il fallimento delle decisioni aziendali prese. Ad esempio, potete esaminare un rapporto sulle visualizzazioni di pagina con tendenze nel tempo per verificare se una riprogettazione del sito ha contribuito ad aumentare o ridurre il traffico.

1. Accedete a [ExperienceCloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali ID Adobe.
2. Fate clic sull'icona di 9 quadrati in alto a destra, quindi fate clic sul logo Analytics colorato.
3. Nella barra di navigazione superiore, fate clic su Area di lavoro.
4. Fate clic sul pulsante "Crea nuovo progetto".
5. Nella finestra a comparsa modale, assicurarsi che sia selezionato "Progetto vuoto", quindi fare clic su Crea.
6. A sinistra è visualizzato un elenco di dimensioni, metriche, segmenti e intervalli di date. Individuate la dimensione Visualizzazioni pagina e trascinatela nello spazio piccolo sul quadro con l’etichetta "Rilasciate qui una metrica". Evitare di rilasciarlo nello spazio riservato alle dimensioni (almeno per questo esercizio).
7. Nota: se la suite di rapporti contiene dati, dovresti visualizzare un rapporto di visualizzazione della pagina di base con tendenze nel mese corrente. Analysis Workspace ha introdotto automaticamente l’intervallo di date "Giorno" per visualizzare la tendenza delle visualizzazioni di pagina per il mese corrente.
8. Posiziona l’intervallo di date Settimana (viola colorato) nell’elenco dei componenti dell’intervallo di date a sinistra. Fai clic sul titolo dell’intervallo di date per espandere e visualizzare tutti i componenti dell’intervallo di date oppure utilizza la barra di ricerca.
9. Trascina l’intervallo di date Settimana sopra l’intestazione dell’intervallo di date Giorno nell’area di lavoro per sostituirlo.
10. Il report con tendenze ora è aggregato per settimana invece che per giorno.
11. Per salvare il progetto, fate clic su *[!UICONTROL Project]&gt;[!UICONTROL Save]* in alto a sinistra.

## Sperimentare con lo strumento

Poiché Analysis Workspace è uno strumento di reporting, non ha alcun impatto sulla raccolta dei dati. Non ci sono ripercussioni sul trascinamento indiscriminato di componenti in un progetto per vedere cosa funziona. Trascina nel progetto dell’area di lavoro diverse combinazioni di dimensioni e metriche per vedere quali sono le opzioni disponibili.

Se accidentalmente trascinate un componente non valido nel progetto dell’area di lavoro o desiderate tornare indietro di un passo, premete Ctrl+Z (Windows) o Comando+Z (Mac) per annullare l’ultima azione eseguita. Potete anche iniziare con una lavagna pulita facendo clic su *[!UICONTROL Project]&gt;[!UICONTROL New]* in alto a sinistra.

## Risoluzione dei problemi

**Quando trascino una metrica su di essa, viene indicato "Dati non validi".**

Dati non validi indicano che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel rapporto. Ad esempio, due metriche sovrapposte tra loro non possono essere restituite come dati, in quanto non è possibile visualizzare in questo modo due metriche. Posiziona invece le metriche affiancate.

**Quando trascino una metrica su di essa, non vedo dati effettivi, ma solo zeri.**

Se create correttamente un rapporto dell’area di lavoro ma non sono presenti dati, potete controllare alcuni elementi:

* Controlla due volte la suite di rapporti e assicurati che sia compilata con i dati.
* Se utilizzi un segmento nel report, i criteri del segmento potrebbero non corrispondere ad alcun dato. Provate a rimuovere il segmento o a regolare la definizione del segmento.
* Controlla l'intervallo di date in alto a destra e accertati che sia impostato su un valore previsto.
* Andate al sito Web e utilizzate il debugger per convalidare i dati raccolti.

## Risorse aggiuntive

* [Note](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md)sulla versione di Analysis Workspace: Leggi le funzioni più recenti introdotte nello strumento.
* [Analysis Workspace su YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): Scopri come utilizzare la maggior parte delle funzioni di Analysis Workspace tramite questa ampia playlist.
* Suggerimenti per i prodotti: I suggerimenti della giornata, insieme a brevi video, vengono visualizzati occasionalmente nell’angolo inferiore destro di Analysis Workspace. Se questi suggerimenti vengono scartati, possono essere raggiunti attraverso *[!UICONTROL Help]&gt;[!UICONTROL Tips]* in qualsiasi momento.
* [Community](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace)di Analysis Workspace: Discuti di Analysis Workspace con altri utenti e vota le funzioni che vorresti vedere nello strumento.
* Post del blog:
   * [Un’analisi più intelligente per dare più strumenti alle aziende](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [Le nuove funzioni di Adobe Analytics rendono ancora più accessibili dati e informazioni](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/)
   * [5 suggerimenti per massimizzare la produttività con Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/)
   * [Approfondimenti rapidi con Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/)
   * [Perché utilizzare Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)

## Passaggi successivi

Ci sono molte indicazioni per approfondire la conoscenza di Analysis Workspace. Di seguito sono riportate alcune informazioni di base che Adobe consiglia di:

### Per gli utenti finali che desiderano ampliare le conoscenze su come utilizzare Analysis Workspace

* [Dettagli sull’interfaccia](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)Workspace: Ora che hai creato un rapporto di base, acquisisci maggiore familiarità con il resto dell'interfaccia.
* [Visualizzazioni in Workspace](visualizations/freeform-analysis-visualizations.md): Le tabelle a forma libera sono solo un tipo di visualizzazione disponibile in Analysis Workspace. Scopri come utilizzare altre visualizzazioni, come grafici a linee, grafici a barre e mappe geografiche.
* [Dimensioni in Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): Scopri di più sulle dimensioni e come utilizzarle in report più che semplici classifica.
* [Metriche in Workspace](/help/analyze/analysis-workspace/components/apply-create-metrics.md): Ulteriori informazioni sulle metriche e su come utilizzarle in altre parti delle tabelle a forma libera.
* [Introduzione alla segmentazione](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): Scopri i segmenti e crea un rapporto di base utilizzando un segmento.
* [Intervalli di date in Workspace](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): Scopri le date relative e mobili e utilizzali nei progetti dell'area di lavoro.
* Condivisione di progetti in Workspace: Mostra al tuo collega il fantastico progetto Workspace che hai creato.
* [(Avanzate) Pannelli in Workspace](c-panels/panels.md): Utilizzare funzioni avanzate in Workspace, ad esempio Attribuzione e Confronto segmenti.

### Per analisti e amministratori che desiderano migliorare la qualità dell’area di lavoro nella propria organizzazione

* [Autorizzazioni](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)di Analysis Workspace: Assegnare agli utenti le autorizzazioni per Workspace tramite Adobe Admin Console.
* [Crea un documento](/help/implement/prepare/solution-design.md)di progettazione della soluzione: Inizia a pianificare in che modo l'organizzazione raccoglie dimensioni o metriche aggiuntive specifiche per il tuo sito.
* [Modelli in Workspace](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): Potete creare dei modelli in modo che i vostri colleghi possano iniziare con uno spazio di progetto adatto alle loro esigenze.
* [Gestione](curate-share/curate.md)area di lavoro: Creare un progetto che limiti i componenti disponibili, rendendo l'area di lavoro più accessibile a chi ha meno familiarità con lo strumento
