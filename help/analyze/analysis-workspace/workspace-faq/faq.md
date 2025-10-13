---
description: Ottieni risposte alle domande più frequenti su Analysis Workspace.
title: Domande frequenti
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 81%

---

# Domande frequenti

+++Quali sono i prerequisiti per utilizzare Analysis Workspace?
[Invia dati ad Adobe Analytics tramite l’estensione Adobe Experience](/help/implement/launch/validate-publish-prod.md): l’utilizzo di Analysis Workspace richiede un’implementazione funzionante. Prima di utilizzare lo strumento, assicurati che la tua organizzazione invii dati ad Adobe. Possono funzionare anche altre implementazioni, come le implementazioni manuali precedenti.
+++

+++Quali sono i requisiti di amministrazione e di accesso per Analysis Workspace?
Consulta [Requisiti di amministrazione](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++L’utilizzo di Analysis Workspace influisce sulla raccolta dei dati?
Poiché Analysis Workspace è uno strumento di reporting, non ha alcun impatto sulla raccolta dei dati. Non ci saranno ripercussioni in seguito al trascinamento di componenti all’interno di un progetto per scoprire come funziona lo strumento. Trascina nel progetto Workspace diverse combinazioni di dimensioni e metriche per scoprire quali sono le opzioni disponibili. Se trascini accidentalmente un componente non valido nel progetto Workspace o desideri tornare indietro di un passo, premi Ctrl + Z (Windows) o Comando + Z (Mac) per annullare l’ultima azione eseguita. È anche possibile iniziare con un’area di lavoro pulita facendo clic su **[!UICONTROL Project]** > **[!UICONTROL New]** nel menu in alto a sinistra.
+++

+++Quante suite di rapporti è possibile visualizzare in un progetto di Analysis Workspace?
Ora puoi creare progetti in Analysis Workspace con dati provenienti da più [suite di rapporti multiple](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md).
+++

+++Come si implementa Analysis Workspace?
Non è richiesta alcuna implementazione particolare. Analysis Workspace è disponibile per tutte le società che dispongono di Analytics Standard o Premium. Tuttavia, si applicano le autorizzazioni standard per i contenuti (come suite di rapporti e componenti dei progetti) e per la cura e la condivisione di progetti. Consulta [Amministrazione e requisiti di accesso](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++Posso utilizzare Analysis Workspace per il Data Warehouse?
Analysis Workspace non è consigliato per l’esportazione di dati in massa. Si tratta di un’area di lavoro di visualizzazione per la creazione di progetti di analisi con layout simile a una dashboard.
+++

+++Come si ottimizzano le prestazioni di Analysis Workspace?

Vedi [Ottimizzazione delle prestazioni](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).

+++

+++Come entrano i dati nel progetto Analysis Workspace?

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dati in Analysis Workspace](https://video.tv.adobe.com/v/35894?quality=12&learn=on&captions=ita){target="_blank"} per un video dimostrativo.

+++

+++Come si tiene traccia dell’utilizzo di Workspace?

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Tracciamento del registro](https://video.tv.adobe.com/v/29768?quality=12&learn=on){target="_blank"}.

+++

+++Quando trascino una metrica, visualizzo un messaggio indicante che i dati non sono validi. Come posso risolvere questo problema?

Il messaggio indicante che i dati non sono validi significa che Adobe non può restituire dati utilizzando la combinazione di dimensioni e metriche utilizzate nel report. Ad esempio, due metriche posizionate una sopra all’altra non possono essere restituite come dati, in quanto non è possibile visualizzare due metriche in questo modo. Posiziona invece le metriche una accanto all’altra.

+++

+++Quando trascino una metrica, non visualizzo dati effettivi, ma solo zeri. Come posso risolvere questo problema?

Se crei correttamente un report Workspace, ma non sono presenti dati, puoi controllare alcuni elementi:

* Controlla la suite di rapporti e assicurati che includa dati.
* Se hai applicato un segmento nel report, i criteri del segmento potrebbero non corrispondere ad alcun dato. Prova a rimuovere il segmento o a regolare la definizione del segmento.
* Controlla l’intervallo di date in alto a destra e accertati che sia impostato sul valore desiderato.
* Vai al tuo sito web e utilizza il [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it) per convalidare i dati raccolti.


+++

+++In qualità di utente di sola lettura, quali azioni posso eseguire in Analysis Workspace?
Quando un progetto viene condiviso in sola lettura, tutte le funzioni e le caratteristiche di modifica vengono completamente disabilitate e i destinatari possono solo modificare il menu a discesa per applicare un filtro al pannello in modo predefinito.
+++
