---
title: Personalizzazione dei report in Adobe Analytics
description: Scopri come personalizzare i rapporti in Adobe Analytics
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Personalizzare i rapporti

Nelle piattaforme di terze parti come Google Analytics, sono disponibili diverse opzioni di personalizzazione. Queste personalizzazioni consentono a un utente di creare dashboard, rapporti personalizzati, rapporti salvati e avvisi personalizzati. Poiché Analysis Workspace consente agli utenti di generare rapporti da un quadro vuoto, la maggior parte delle personalizzazioni sono integrate direttamente nello strumento.

Questa pagina presuppone che l'utente abbia una conoscenza di base sull'utilizzo di Analysis Workspace. See [Create a basic report in Analysis Workspace for Google Analytics users](reports/create-report.md) if you are not yet familiar with the tool in Adobe Analytics.

## Dashboard

L'architettura di Analysis Workspace è simile al concetto di widget dashboard. I progetti in Analysis Workspace rappresentano l'equivalente approssimativo delle dashboard in Google Analytics. Le visualizzazioni in Analysis Workspace rappresentano l'equivalente approssimativo dei widget in Google Analytics.

### Aggiunta di contenuti a un progetto

1. Fai clic sull'icona Visualizzazioni a sinistra e trascina la visualizzazione desiderata sull'area di lavoro.
2. Fai clic sull'icona Componenti a sinistra e trascina le dimensioni e le metriche desiderate sulla visualizzazione per compilarle con i dati.
3. Trascinate i bordi della visualizzazione per ridimensionarla e trascinate il titolo della visualizzazione per spostarla.

Tutti i widget Google Analytics sono disponibili in Analysis Workspace:

* The **Metric widget** is approximately equal to the Summary Number visualization.
* The **Timeline widget** is approximately equal to the Line visualization.
* The **Geomap widget** is approximately equal to the Map visualization.
* The **Table widget** is approximately equal to the Freeform Table visualization.
* The **Pie widget** is approximately equal to the Donut visualization.
* The **Bar widget** is approximately equal to the Bar visualization.

Analysis Workspace include numerose opzioni di visualizzazione per presentare i dati in modo ottimale per le esigenze di reporting. See [Visualizations in Analysis Workspace](../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) in the Analyze User Guide for more information.

### Condivisione di progetti

Dopo aver aggiunto il contenuto a un progetto, potete condividerlo.

* Per condividere il progetto con i colleghi, vai a Condividi &gt; Condividi progetto. I destinatari sono altri utenti della vostra organizzazione che dispongono di account Adobe Analytics.
* Per condividere il progetto tramite un collegamento, vai a Condividi &gt; Ottieni collegamento progetto. Tenete presente che questo richiede ancora un accesso ad Adobe Analytics all'interno della vostra organizzazione.

### Esportazione di progetti

Oltre a PDF, Analysis Workspace offre un'esportazione CSV.

1. Click *[!UICONTROL Share]* &gt; *[!UICONTROL Send File Now]*, which opens a modal window.
2. Specifica il tipo di file e i destinatari.
3. Clic [!UICONTROL Send Now].

## Report personalizzati

Quando create un rapporto personalizzato in Google Analytics, i campi necessari sono simili al flusso di lavoro durante la creazione di una visualizzazione nell'area di lavoro. Le definizioni di dimensioni, metriche e filtri sono simili alle piattaforme. In Analysis Workspace, invece di selezionare dimensioni e metriche da un elenco, dimensioni e metriche vengono trascinate in una tabella a forma libera.

### Metriche calcolate nei rapporti personalizzati

I rapporti personalizzati sono una delle poche aree di Google Analytics che consentono l'utilizzo di metriche calcolate. Poiché Analysis Workspace funziona come un quadro, le metriche calcolate funzionano in modo retroattivo e in qualsiasi contesto.

Per creare una metrica calcolata:

1. Click the **+** icon near the metric list to open the Calculated Metric Builder.
2. Assegna un nome alla metrica calcolata e specifica un formato.
3. Trascinate i componenti della metrica nell'area di definizione e utilizzate gli elenchi a discesa tra ciascun componente per designare un operatore.
4. Una volta che la metrica calcolata contiene la formula desiderata, fai clic su Salva per tornare alla tua area di lavoro.
5. Trascinate la metrica calcolata appena definita nell'area di lavoro.

   Learn more about [Calculated Metrics](../../components/c-variables/c-metrics/calculated-metric.md) in the Components user guide.

## Avvisi personalizzati

Gli avvisi sono disponibili su entrambe le piattaforme. In Adobe Analytics, use the header navigation menu and go to *[!UICONTROL Components]* &gt; *[!UICONTROL Alerts]*. See [Intelligent Alerts](../../components/c-alerts/intellligent-alerts.md) in the Components User Guide for more information.
