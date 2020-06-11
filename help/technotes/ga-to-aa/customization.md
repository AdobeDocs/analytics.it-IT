---
title: Personalizzazione dei report in Adobe Analytics
description: Scopri come personalizzare i rapporti in Adobe Analytics
translation-type: tm+mt
source-git-commit: 6fc8145d9a94427ec942d55776b6029f7dd6f79c
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 1%

---


# Personalizzare i rapporti

Nelle piattaforme di terze parti, come Google Analytics, sono disponibili diverse opzioni di personalizzazione. Queste personalizzazioni consentono a un utente di creare dashboard, rapporti personalizzati, rapporti salvati e avvisi personalizzati. Poiché Analysis Workspace consente agli utenti di creare rapporti da un quadro vuoto, la maggior parte delle personalizzazioni sono integrate direttamente nello strumento.

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo [!UICONTROL Analysis Workspace]. Consultate [Creare un rapporto di base in Analysis Workspace per gli utenti](reports/create-report.md) di Google Analytics se non avete ancora familiarità con lo strumento in Adobe Analytics.

## Dashboard

L&#39; [!UICONTROL Analysis Workspace] architettura è simile al concetto di widget dashboard. I progetti in [!UICONTROL Analysis Workspace] sono l&#39;equivalente approssimativo delle dashboard in Google Analytics. Le visualizzazioni in [!UICONTROL Analysis Workspace] sono l&#39;equivalente approssimativo dei widget in Google Analytics.

### Aggiunta di contenuto a un progetto

1. Fate clic sull’ [!UICONTROL Visualizations] icona a sinistra e trascinate la visualizzazione desiderata nell’area di lavoro.
2. Fai clic sull’ [!UICONTROL Components] icona a sinistra e trascina le dimensioni e le metriche desiderate sulla visualizzazione per compilarla con i dati.
3. Trascina i bordi della visualizzazione per ridimensionarla, quindi trascina il titolo della visualizzazione per spostarla.

Tutti i widget Google Analytics sono disponibili in [!UICONTROL Analysis Workspace]:

* Il widget **** Metrica è approssimativamente uguale alla [!UICONTROL Summary Number] visualizzazione.
* Il widget **** Timeline è approssimativamente uguale alla [!UICONTROL Line] visualizzazione.
* Il widget **Geomap** è approssimativamente uguale alla [!UICONTROL Map] visualizzazione.
* Il widget **** Tabella è approssimativamente uguale alla [!UICONTROL Freeform Table] visualizzazione.
* Il widget **Torta** è approssimativamente uguale alla [!UICONTROL Donut] visualizzazione.
* Il widget **** Barra è approssimativamente uguale alla [!UICONTROL Bar] visualizzazione.

[!UICONTROL Analysis Workspace] include molte più opzioni di visualizzazione per presentare i dati nel modo più adatto alle esigenze di reporting. Per ulteriori informazioni, consulta [Visualizzazioni in Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) nella Guida utente di analisi.

### Condivisione di progetti

Dopo aver aggiunto il contenuto a un progetto, potete condividerlo.

* Per condividere il progetto con i tuoi colleghi, vai a **[!UICONTROL Share > Share Project]**. I destinatari sono altri utenti dell&#39;organizzazione che dispongono di account Adobe Analytics.
* Per condividere il progetto tramite un collegamento, vai a **[!UICONTROL Share > Get Project Link]**. Tieni presente che questo richiede ancora un accesso ad Adobe Analytics all&#39;interno dell&#39;organizzazione.

### Esportazione di progetti

Oltre al PDF, [!UICONTROL Analysis Workspace] offre un’esportazione CSV.

1. Fate clic su *[!UICONTROL Share]* > *[!UICONTROL Send File Now]*, per aprire una finestra modale.
2. Specificate il tipo di file e i destinatari.
3. Fai clic su [!UICONTROL Send Now].

## Report personalizzati

Quando si crea un rapporto personalizzato in Google Analytics, i campi richiesti sono simili al flusso di lavoro per la creazione di una visualizzazione nell&#39;area di lavoro. Le definizioni di dimensioni, metriche e filtri sono simili tra le piattaforme. In Analysis Workspace, invece di selezionare dimensioni e metriche da un elenco, dimensioni e metriche vengono trascinate in una tabella a forma libera.

### Metriche calcolate nei report personalizzati

I report personalizzati sono una delle poche aree di Google Analytics che consente l&#39;utilizzo delle metriche calcolate. Poiché Analysis Workspace funziona come un quadro, le metriche calcolate funzionano in modo retroattivo e in qualsiasi contesto.

Per creare una metrica calcolata:

1. Fai clic sull’icona **+** accanto all’elenco delle metriche per aprire il [!UICONTROL Calculated Metric Builder].
2. Assegna un nome alla metrica calcolata e specifica un formato.
3. Trascina i componenti della metrica nell’area di definizione e usa i menu a discesa tra ciascun componente per designare un operatore.
4. Una volta che la metrica calcolata contiene la formula desiderata, fate clic su Salva per tornare alla vostra area di lavoro.
5. Trascina nell’area di lavoro la metrica calcolata appena definita.

   Per ulteriori informazioni sulle metriche [calcolate](/help/components/c-calcmetrics/cm-overview.md) , consulta la Guida utente ai componenti.

## Avvisi personalizzati

Gli avvisi sono disponibili su entrambe le piattaforme. In Adobe Analytics, utilizzate il menu di navigazione dell&#39;intestazione e andate a *[!UICONTROL Components]* > *[!UICONTROL Alerts]*. Per ulteriori informazioni, consulta [Avvisi](/help/components/c-alerts/intellligent-alerts.md) intelligenti nella Guida utente dei componenti.
