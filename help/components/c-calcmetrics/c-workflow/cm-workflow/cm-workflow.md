---
description: Scopri come creare metriche calcolate.
title: Flusso di lavoro per le metriche calcolate
feature: Calculated Metrics
exl-id: b3380d6b-53b5-40af-8e23-34772d79ae26
source-git-commit: 183f6e39fb1d14b7b29817e76da0302ba23cd5d6
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 13%

---

# Creare metriche calcolate

Per impostazione predefinita, solo gli amministratori possono creare metriche calcolate. Gli utenti dispongono delle autorizzazioni per visualizzare le metriche calcolate, in modo analogo a come visualizzano altri componenti (come segmenti, annotazioni e altro ancora).

Puoi creare una metrica calcolata nei seguenti modi:

![Modalità di creazione di una metrica](assets/create-metric.png)

* **A**. Nell’interfaccia principale, seleziona **[!UICONTROL Components]** e quindi **[!UICONTROL Calculated metrics]**. Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] dal gestore [[!UICONTROL Calculated metrics]](cm-manager.md).
* **B**. In un progetto Workspace, dal pannello a sinistra Componenti, seleziona ![Aggiungi](/help/assets/icons/Add.svg) in ![Evento](/help/assets/icons/Event.svg) **Metriche**.
* **C**. In un progetto Workspace, dal menu di scelta rapida nell&#39;intestazione di colonna delle metriche, selezionare **[!UICONTROL Create metric from selection]**. Dal sottomenu, è possibile selezionare una funzione o selezionare **[!UICONTROL Open in calculated metric builder]**. <br/>Se selezioni una funzione, la metrica calcolata viene definita come metrica solo progetto. Quando successivamente modifichi questa metrica, tramite il popup [Informazioni componente](/help/analyze/analysis-workspace/components/use-components-in-workspace.md), viene visualizzata una notifica nel [Generatore di metriche calcolate](c-build-metrics/cm-build-metrics.md).
* **D**. In un progetto Workspace, seleziona **[!UICONTROL Components]** dal menu e quindi **[!UICONTROL Create metric]**.
* **E**. In un progetto Workspace, utilizzare il collegamento **[!UICONTROL shift+cmd+c]** (macOS) o **[!UICONTROL shift+ctrl+c]** (Windows).

Per definire la nuova metrica calcolata, utilizzare il generatore di metriche calcolate [&#128279;](c-build-metrics/cm-build-metrics.md).


## Flusso di lavoro

Prima di creare le metriche calcolate, considera attentamente il seguente flusso di lavoro:

| Attività flusso di lavoro | Descrizione |
| --- | --- |
| Pianificare le metriche calcolate | Soprattutto per le metriche che verranno ufficialmente &quot;approvate&quot;, ha senso delineare quali metriche calcolate saranno ampiamente utilizzate e come saranno definite. |
| [Genera](c-build-metrics/cm-build-metrics.md) metriche calcolate | Genera e modifica metriche calcolate e calcolate avanzate da utilizzare nei componenti [!DNL Analytics].  Consulta [esempi](c-build-metrics/cm-build-metrics.md) su come generare metriche calcolate. |
| [Tag](cm-tagging.md) metriche calcolate | Assegna tag alle metriche calcolate per semplificarne l’organizzazione e la condivisione. Scopri come pianificare e assegnare tag per ricerche e organizzazioni semplici e avanzate. |
| [Approva](cm-approving.md) metriche calcolate | Approva le metriche calcolate per renderle canoniche. |
| Utilizzare le metriche calcolate | Utilizza le metriche calcolate nei progetti. |
| [Condividi](cm-sharing.md) metriche calcolate | Condividere le metriche calcolate con altri individui, gruppi o organizzazioni. |
| [Filtro](cm-filter.md) metriche calcolate | Filtrare le metriche calcolate per tag, proprietari e altri filtri (Mostra tutto, Personali, Condivisi con me, Preferiti e Approvati). |
| Contrassegna metriche calcolate come [preferiti](cm-finding.md) | Contrassegnare le metriche come preferite è un altro modo per organizzarle in modo semplice e intuitivo. |
