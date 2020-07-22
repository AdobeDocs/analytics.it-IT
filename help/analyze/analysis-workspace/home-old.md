---
description: Introduzione ad Adobe Analytics.
keywords: Analysis Workspace
title: Guida introduttiva
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1329'
ht-degree: 98%

---


# Analysis Workspace

Analysis Workspace è uno degli strumenti principali di Adobe che consente di prendere decisioni basate sui dati utilizzabili a livello aziendale. La visualizzazione più comune, ovvero la tabella a forma libera, consente di creare facilmente rapporti personalizzati utilizzando dimensioni, metriche, segmenti e intervalli di date.

## Prerequisiti

[Invia dati ad Adobe Analytics tramite Adobe Experience Platform Launch](/help/implement/launch/validate-publish-prod.md): l’utilizzo di Analysis Workspace richiede un’implementazione funzionante. Prima di utilizzare lo strumento, è necessario assicurarsi che l’organizzazione invii dati ad Adobe. Possono funzionare anche altre implementazioni, come DTM o implementazioni manuali precedenti.

## Recuperare un report classifica di base in Workspace

Recupera un report classifica di base utilizzando Analysis Workspace. Un rapporto classifica mostra una visualizzazione totale aggregata di ciascun elemento dimensione, mostrando per primo i valori più grandi. Questi tipi di report sono utili per identificare i componenti del sito più efficaci, ad esempio le pagine che ottengono il maggior traffico o quelle che generano più vendite.

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
2. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
3. Nella barra di navigazione superiore, fai clic su Workspace.
4. Fai clic sul pulsante “Crea nuovo progetto”.
5. Nella finestra a comparsa modale, assicurati che sia selezionato “Progetto vuoto”, quindi fai clic su Crea.
6. A sinistra appare un elenco di dimensioni, metriche, segmenti e intervalli di date. Individua la dimensione Pages (Pagine) (di colore arancione) e trascinala sull’area di lavoro dove è indicato “Drop a Dimension Here” (Rilascia qui una dimensione).
7. Se la suite di rapporti contiene dati, è possibile visualizzare un report che mostra le pagine principali del mese in corso. Analysis Workspace ha popolato automaticamente il report con la metrica [Occorrenze](/help/components/metrics/occurrences.md).
8. Individua la metrica Visite (di colore verde) e trascinala **sopra** o **accanto** all’intestazione della metrica Occorrenze (evita di posizionarla al di sopra della metrica). Se trascini la metrica Visite al di sopra di Occorrenze, la metrica viene sostituita durante la generazione del report. Se trascini la metrica Visite accanto a Occorrenze, entrambe le metriche vengono visualizzate una accanto all’altra.
9. Per salvare il progetto, fai clic su *[!UICONTROL Project] > [!UICONTROL Save]* nel menu in alto a sinistra.

## Recuperare un report con tendenze di base in Workspace

Recupera un report con tendenze di base utilizzando Analysis Workspace. Un report con tendenze mostra una visualizzazione temporale delle metriche utilizzando l’intervallo di date selezionato. Questi tipi di report sono utili per identificare le tendenze nel tempo e possono essere utilizzati per misurare il successo o il fallimento delle decisioni aziendali attuate. Ad esempio, è possibile esaminare un report sulle visualizzazioni di pagina con tendenze nel tempo per verificare se una riprogettazione del sito ha contribuito ad aumentare o ridurre il traffico.

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
2. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
3. Nella barra di navigazione superiore, fai clic su Workspace.
4. Fai clic sul pulsante “Crea nuovo progetto”.
5. Nella finestra a comparsa modale, assicurati che sia selezionato “Progetto vuoto”, quindi fai clic su Crea.
6. A sinistra appare un elenco di dimensioni, metriche, segmenti e intervalli di date. Individua la dimensione Page Views (Visualizzazioni di pagina) e trascinala nel piccolo spazio sull’area di lavoro denominata “Drop a Metric Here” (Rilascia qui una metrica). Evita di rilasciarla nello spazio riservato alle dimensioni (almeno per questo esercizio).
7. Nota: se la suite di rapporti contiene dati, dovrebbe apparire un report di base sulle visualizzazioni di pagina indicante le tendenze nel corso del mese corrente. Analysis Workspace ha introdotto automaticamente l’intervallo di date “Day” (Giorno) per visualizzare la tendenza delle visualizzazioni di pagina nel corso del mese corrente.
8. Individua l’intervallo di data “Week” (Settimana) (di colore viola) nell’elenco dei componenti dell’intervallo di date a sinistra. Fai clic sul titolo dell’intervallo di date per espandere e visualizzare tutti i componenti dell’intervallo di date, oppure utilizza la barra di ricerca.
9. Trascina l’intervallo di date “Week” (Settimana) sopra l’intestazione dell’intervallo di date “Day” (Giorno) nell’area di lavoro per sostituirlo.
10. Il report con tendenze ora è aggregato per settimana anziché per giorno.
11. Per salvare il progetto, fai clic su *[!UICONTROL Project] > [!UICONTROL Save]* nel menu in alto a sinistra.

## Esercitarsi con lo strumento

Poiché Analysis Workspace è uno strumento di reporting, non ha alcun impatto sulla raccolta dei dati. Non ci saranno ripercussioni in seguito al trascinamento di componenti all’interno di un progetto per scoprire come funziona lo strumento. Trascina nel progetto Workspace diverse combinazioni di dimensioni e metriche per scoprire quali sono le opzioni disponibili.

Se trascini accidentalmente un componente non valido nel progetto Workspace o desideri tornare indietro di un passo, premi Ctrl+Z (Windows) o Comando+Z (Mac) per annullare l’ultima azione eseguita. È anche possibile iniziare con un’area di lavoro pulita facendo clic su *[!UICONTROL Project] > [!UICONTROL New]* nel menu in alto a sinistra.

## Risoluzione dei problemi

**Quando trascino una metrica, visualizzo un messaggio indicante che i dati non sono validi.**

Il messaggio indicante che i dati non sono validi significa che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel report. Ad esempio, due metriche posizionate una sopra all’altra non possono essere restituite come dati, in quanto non è possibile visualizzare due metriche in questo modo. Piuttosto, posiziona le metriche una accanto all’altra.

**Quando trascino una metrica, non visualizzo dati effettivi, ma solo zeri.**

Se crei correttamente un report Workspace ma non sono presenti dati, puoi controllare alcuni elementi:

* Controlla la suite di rapporti e assicurati che includa dati.
* Se utilizzi un segmento nel report, i criteri del segmento potrebbero non corrispondere ad alcun dato. Prova a rimuovere il segmento o a regolare la definizione del segmento.
* Controlla l’intervallo di date in alto a destra e accertati che sia impostato sul valore desiderato.
* Vai al tuo sito web e utilizza Debugger per convalidare i dati raccolti.

## Risorse aggiuntive

* [Note sulla versione di Analysis Workspace](/help/analyze/analysis-workspace/new-features-in-analysis-workspace.md): leggi le funzioni più recenti introdotte nello strumento.
* [Analysis Workspace su YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS): scopri come utilizzare la maggior parte delle funzioni di Analysis Workspace tramite questa ampia playlist.
* Suggerimenti interni ai prodotti: i suggerimenti della giornata, oltre a brevi video, vengono visualizzati occasionalmente nell’angolo inferiore destro di Analysis Workspace. Se questi suggerimenti vengono chiusi, possono essere recuperati in qualsiasi momento andando su *[!UICONTROL Help] > [!UICONTROL Tips]*.
* [Community di Analysis Workspace](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/analysis-workspace): discuti di Analysis Workspace con altri utenti e vota le funzioni che vorresti vedere nello strumento.
* Post sul blog:
   * [Empowering Organizations with Smarter Analysis](https://blogs.adobe.com/digitalmarketing/analytics/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/) (Un’analisi più intelligente per dare più strumenti alle aziende)
   * [New Adobe Analytics Capabilities Make Powerful Insights More Accessible](https://blogs.adobe.com/digitalmarketing/analytics/new-adobe-analytics-capabilities-make-powerful-insights-accessible/) (Le nuove funzioni di Adobe Analytics rendono ancora più accessibili dati e informazioni)
   * [5 Tips to Maximize Your Productivity with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/5-tips-maximize-productivity-analysis-workspace/) (5 suggerimenti per massimizzare la produttività con Analysis Workspace)
   * [Faster Insights with Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/faster-insights-with-the-analysis-workspace/) (Approfondimenti rapidi con Analysis Workspace)
   * [Why You Should Be Using Analysis Workspace](https://blogs.adobe.com/digitalmarketing/analytics/why-you-should-be-using-analysis-workspace-in-adobe-analytics/) (Perché utilizzare Analysis Workspace)

## Passaggi successivi

Esistono altre risorse per approfondire le tue conoscenze di Analysis Workspace. Di seguito sono riportate alcune informazioni di base consigliate da Adobe:

### Per gli utenti finali che desiderano ampliare le conoscenze sull’utilizzo di Analysis Workspace

* [Dettagli sull’interfaccia Workspace](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md): ora che hai creato un report di base, acquisisci maggiore familiarità con il resto dell’interfaccia.
* [Visualizzazioni in Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md): le tabelle a forma libera è solo uno dei tipi di visualizzazione disponibili in Analysis Workspace. Scopri come utilizzare altre visualizzazioni quali grafici a linee, grafici a barre e mappe geografiche.
* [Dimensioni in Workspace](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md): scopri di più sulle dimensioni e come utilizzarle in report classifica più elaborati.
* [Metriche in Workspace](/help/analyze/analysis-workspace/components/apply-create-metrics.md): ulteriori informazioni sulle metriche e su come utilizzarle in altre sezioni delle tabelle a forma libera.
* [Introduzione alla segmentazione](/help/analyze/analysis-workspace/components/t-freeform-project-segment.md): scopri cosa sono i segmenti e crea un report di base utilizzando un segmento.
* [Intervalli di date in Workspace](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md): scopri le date relative e continue e utilizzale nei progetti Workspace.
* Condivisione di progetti in Workspace: mostra ai tuoi colleghi il fantastico progetto Workspace che hai creato.
* [(Avanzato) Pannelli in Workspace](/help/analyze/analysis-workspace/c-panels/panels.md): utilizzare funzioni avanzate in Workspace, ad esempio Attribuzione e Confronto segmenti.

### Per analisti e amministratori che desiderano migliorare la qualità di Workspace nella propria organizzazione

* [Autorizzazioni di Analysis Workspace](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html): assegna agli utenti le autorizzazioni d’utilizzo di Workspace tramite Adobe Admin Console.
* [Modelli in Workspace](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md): puoi creare dei modelli in modo che i tuoi colleghi possano iniziare con uno spazio di progetto adatto alle loro esigenze.
* [Gestione di Workspace](/help/analyze/analysis-workspace/curate-share/curate.md): crea un progetto che limiti i componenti disponibili, rendendo Workspace più accessibile a chi ha meno familiarità con lo strumento.
