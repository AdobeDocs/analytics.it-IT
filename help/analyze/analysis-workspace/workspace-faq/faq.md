---
description: Ottieni risposte alle domande più frequenti su Analysis Workspace.
title: Domande frequenti
feature: Workspace Basics
role: User, Admin
exl-id: cf7a9a73-bcbe-4bf5-b5dc-913199ab229c
TQID: https://experienceleague.adobe.com/Cp7KvN1Y7Mxr4iGWNF08TYBzJWqhVWVSHApX0989lZ4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c069c44e-5426-4c1a-accc-8028662f2fdeid: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 596
ht-degree: 68%

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
Non è richiesta alcuna implementazione particolare. Analysis Workspace è disponibile per tutte le aziende con Analytics Standard o Premium. Tuttavia, si applicano le autorizzazioni standard per i contenuti (come suite di rapporti e componenti di progetto) e per la cura e la condivisione di progetti. Consulta [Amministrazione e requisiti di accesso](/help/analyze/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).
+++

+++Posso utilizzare Analysis Workspace per Data Warehouse?
Analysis Workspace non è consigliato per l’esportazione di dati in blocco. È un’area di lavoro di visualizzazione che crea progetti di analisi simili a dashboard.
+++

+++Come si ottimizzano le prestazioni di Analysis Workspace?

Vedi [Ottimizzazione delle prestazioni](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).

+++

+++Come entrano i dati nel progetto Analysis Workspace?

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dati in Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/understanding-how-data-gets-into-your-analysis-workspace-project){target="_blank"} per un video dimostrativo.

+++

+++Come si tiene traccia dell’utilizzo di Workspace?

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Tracciamento del registro](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/administration/logs/usage-log-tracking-for-analysis-workspace){target="_blank"}.

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
