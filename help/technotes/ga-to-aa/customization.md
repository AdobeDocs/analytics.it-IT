---
title: Personalizzazione dei rapporti in Adobe Analytics
description: Scopri come personalizzare i rapporti in Adobe Analytics
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# Personalizzare i rapporti

Nelle piattaforme di terze parti, come Google Analytics, sono disponibili diverse opzioni di personalizzazione. Queste personalizzazioni consentono a un utente di creare dashboard, rapporti personalizzati, rapporti salvati e avvisi personalizzati. Poiché Analysis Workspace consente agli utenti di creare rapporti da un’area di lavoro vuota, la maggior parte delle personalizzazioni è incorporata direttamente nello strumento.

Questa pagina presuppone che l&#39;utente disponga di una conoscenza di base dell&#39;utilizzo [!UICONTROL Analysis Workspace]. Vedi [Creare un rapporto di base in Analysis Workspace per gli utenti di Google Analytics](reports/create-report.md) se non hai ancora familiarità con lo strumento in Adobe Analytics.

## Dashboard

La [!UICONTROL Analysis Workspace] L’architettura è simile al concetto di widget dashboard. Progetti in [!UICONTROL Analysis Workspace] sono l’equivalente approssimativo delle dashboard nelle Google Analytics. Visualizzazioni in [!UICONTROL Analysis Workspace] sono l&#39;equivalente approssimativo dei widget nelle Google Analytics.

### Aggiunta di contenuto a un progetto

1. Fai clic sul pulsante [!UICONTROL Visualizations] a sinistra e trascina la visualizzazione desiderata nell’area di lavoro.
2. Fai clic sul pulsante [!UICONTROL Components] a sinistra e trascina le dimensioni e le metriche desiderate sulla visualizzazione per inserirle nei dati.
3. Trascina i bordi della visualizzazione per ridimensionarla e trascina il titolo della visualizzazione per spostarla.

Tutti i widget Google Analytics sono disponibili in [!UICONTROL Analysis Workspace]:

* La **Widget della metrica** è approssimativamente uguale a [!UICONTROL Summary Number] visualizzazione.
* La **Widget Timeline** è approssimativamente uguale a [!UICONTROL Line] visualizzazione.
* La **Widget Geomap** è approssimativamente uguale a [!UICONTROL Map] visualizzazione.
* La **Widget tabella** è approssimativamente uguale a [!UICONTROL Freeform Table] visualizzazione.
* La **Widget torta** è approssimativamente uguale a [!UICONTROL Donut] visualizzazione.
* La **Widget a barre** è approssimativamente uguale a [!UICONTROL Bar] visualizzazione.

[!UICONTROL Analysis Workspace] include molte più opzioni di visualizzazione per presentare i dati nel modo più adatto alle tue esigenze di reporting. Vedi [Visualizzazioni in Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) per ulteriori informazioni, consulta la Guida utente di Analyze .

### Condivisione di progetti

Dopo aver aggiunto il contenuto a un progetto, puoi condividerlo.

* Per condividere il progetto con i tuoi colleghi, vai a **[!UICONTROL Share > Share Project]**. I destinatari sono altri utenti della tua organizzazione che dispongono di account Adobe Analytics.
* Per condividere il progetto tramite un collegamento, vai a **[!UICONTROL Share > Get Project Link]**. Tieni presente che questo richiede ancora un accesso ad Adobe Analytics all’interno della tua organizzazione.

### Esportazione di progetti

Oltre a PDF, [!UICONTROL Analysis Workspace] offre un’esportazione CSV.

1. Fai clic su *[!UICONTROL Share]* > *[!UICONTROL Send File Now]*, che apre una finestra modale.
2. Specifica il tipo di file e i destinatari.
3. Fai clic su [!UICONTROL Send Now] (Usa modello di attribuzione non predefinito).

## Rapporti personalizzati

Quando crei un rapporto personalizzato in Google Analytics, i campi richiesti sono simili al flusso di lavoro per la creazione di una visualizzazione in Workspace. Le definizioni di Dimension, metriche e filtri sono simili tra le piattaforme. In Analysis Workspace, invece di selezionare dimensioni e metriche da un elenco, le dimensioni e le metriche vengono trascinate in una tabella a forma libera.

### Metriche calcolate nei rapporti personalizzati

I rapporti personalizzati sono una delle poche aree di Google Analytics che consente l’utilizzo delle metriche calcolate. Poiché Analysis Workspace funziona come un’area di lavoro, le metriche calcolate funzionano retroattivamente e in qualsiasi contesto.

Per creare una metrica calcolata:

1. Fai clic sul pulsante **+** icona vicino all’elenco delle metriche per aprire [!UICONTROL Calculated Metric Builder].
2. Assegna un nome alla metrica calcolata e specifica un formato.
3. Trascina i componenti metrica nell’area di definizione e utilizza gli elenchi a discesa tra ciascun componente per designare un operatore.
4. Una volta che la metrica calcolata contiene la formula desiderata, fai clic su Salva per tornare all’area di lavoro.
5. Trascina la metrica appena definita nell’area di lavoro.

   Ulteriori informazioni [Metriche calcolate](/help/components/c-calcmetrics/cm-overview.md) nella guida utente Componenti .

## Avvisi personalizzati

Gli avvisi sono disponibili su entrambe le piattaforme. In Adobe Analytics, utilizza il menu di navigazione dell’intestazione e vai a *[!UICONTROL Components]* > *[!UICONTROL Alerts]*. Vedi [Avvisi intelligenti](/help/components/c-alerts/intellligent-alerts.md) per ulteriori informazioni, consulta la Guida utente sui componenti .
