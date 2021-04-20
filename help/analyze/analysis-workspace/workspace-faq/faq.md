---
description: Domande frequenti su Workspace
title: Domande frequenti e risoluzione dei problemi di Workspace
feature: Workspace Basics
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 100%

---


# Domande frequenti

| Domanda | Risposta |
|--- |--- |
| Quali sono i prerequisiti per utilizzare Analysis Workspace? | [Invia dati ad Adobe Analytics tramite Adobe Experience Platform Launch](/help/implement/launch/validate-publish-prod.md): l’utilizzo di Analysis Workspace richiede un’implementazione funzionante. Prima di utilizzare lo strumento, è necessario assicurarsi che l’organizzazione invii dati ad Adobe. Possono funzionare anche altre implementazioni, come DTM o implementazioni manuali precedenti. |
| Quali sono i requisiti di amministrazione e di accesso per Analysis Workspace? | Consulta  [Requisiti di amministrazione](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| L’utilizzo di Analysis Workspace influisce sulla raccolta dei dati? | Poiché Analysis Workspace è uno strumento di reporting, non ha alcun impatto sulla raccolta dei dati. Non ci saranno ripercussioni in seguito al trascinamento di componenti all’interno di un progetto per scoprire come funziona lo strumento. Trascina nel progetto Workspace diverse combinazioni di dimensioni e metriche per scoprire quali sono le opzioni disponibili. Se trascini accidentalmente un componente non valido nel progetto Workspace o desideri tornare indietro di un passo, premi Ctrl+Z (Windows) o Comando+Z (Mac) per annullare l’ultima azione eseguita. È anche possibile iniziare con un’area di lavoro pulita facendo clic su *[!UICONTROL Project] > [!UICONTROL New]* nel menu in alto a sinistra. |
| Quante suite di rapporti è possibile visualizzare in un progetto di Analysis Workspace? | Ora puoi creare progetti in Analysis Workspace con dati provenienti da più [suite di rapporti multiple](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html). |
| Come si implementa Analysis Workspace? | Non è richiesta alcuna implementazione particolare. Analysis Workspace è disponibile per tutte le società che dispongono di Analytics Standard o Premium. Tuttavia, si applicano le autorizzazioni standard per i contenuti (come suite di rapporti e componenti dei progetti) e per la cura e la condivisione di progetti. Consulta [Amministrazione e requisiti di accesso](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Analysis Workspace modifica i rapporti pre-configurati in Adobe Analytics? | No. Poiché si tratta di un ambiente separato, non verrà modificato alcun rapporto esistente o pre-configurato in Adobe Analytics. Potrai sempre utilizzare lo strumento standard di Reports &amp; Analytics e i rapporti del Report Builder tramite Analysis Workspace. |
| Posso utilizzare Analysis Workspace per il Data Warehouse? | Analysis Workspace non è consigliato per l’esportazione di dati in massa. Si tratta di un’area di lavoro di visualizzazione per la creazione di progetti di analisi con layout simile a una dashboard. |
| Come si ottimizzano le prestazioni di Analysis Workspace? | Vedi [Ottimizzazione delle prestazioni](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Risoluzione dei problemi

**Quando trascino una metrica, visualizzo un messaggio indicante che i dati non sono validi.**

Il messaggio indicante che i dati non sono validi significa che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel report. Ad esempio, due metriche posizionate una sopra all’altra non possono essere restituite come dati, in quanto non è possibile visualizzare due metriche in questo modo. Posiziona invece le metriche una accanto all’altra.

**Quando trascino una metrica, non visualizzo dati effettivi, ma solo zeri.**

Se crei correttamente un report Workspace, ma non sono presenti dati, puoi controllare alcuni elementi:

* Controlla la suite di rapporti e assicurati che includa dati.
* Se hai applicato un segmento nel report, i criteri del segmento potrebbero non corrispondere ad alcun dato. Prova a rimuovere il segmento o a regolare la definizione del segmento.
* Controlla l’intervallo di date in alto a destra e accertati che sia impostato sul valore desiderato.
* Vai al tuo sito web e utilizza il [Debugger](https://docs.adobe.com/content/help/it-IT/debugger/using/experience-cloud-debugger.html) per convalidare i dati raccolti.