---
title: Personalizzazione dei rapporti in Adobe Analytics
description: Scopri come personalizzare i rapporti in Adobe Analytics
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
source-git-commit: 815e50e30fa6a0bce1bf78f33843070f96f52de8
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Personalizzare i rapporti

Nelle piattaforme di terze parti, come ad esempio Google Analytics, sono disponibili diverse opzioni di personalizzazione. Queste personalizzazioni consentono a un utente di creare dashboard, rapporti personalizzati, rapporti salvati e avvisi personalizzati. Poiché Analysis Workspace consente agli utenti di creare rapporti da un’area di lavoro vuota, la maggior parte delle personalizzazioni viene incorporata direttamente nello strumento.

Questa pagina presuppone che l&#39;utente abbia una conoscenza di base dell&#39;utilizzo di [!UICONTROL Analysis Workspace]. Se non conosci ancora lo strumento in Analysis Workspace, consulta [Creare un report di base in Adobe Analytics per gli utenti Google Analytics](reports/create-report.md).

## Dashboard

L&#39;architettura [!UICONTROL Analysis Workspace] è stata creata in modo simile al concetto di widget del dashboard. I progetti in [!UICONTROL Analysis Workspace] equivalgono approssimativamente ai dashboard nelle Google Analytics. Le visualizzazioni in [!UICONTROL Analysis Workspace] sono l&#39;equivalente approssimativo dei widget nelle Google Analytics.

### Aggiunta di contenuto a un progetto

1. Fai clic sull&#39;icona [!UICONTROL Visualizations] a sinistra e trascina la visualizzazione desiderata nell&#39;area di lavoro.
2. Fai clic sull&#39;icona [!UICONTROL Components] a sinistra e trascina le dimensioni e le metriche desiderate nella visualizzazione per compilarla con i dati.
3. Trascina i bordi della visualizzazione per ridimensionarla e trascina il titolo della visualizzazione per spostarla.

Tutti i widget Google Analytics sono disponibili in [!UICONTROL Analysis Workspace]:

* Il widget **Metrica** è approssimativamente uguale alla visualizzazione [!UICONTROL Summary Number].
* Il widget **Timeline** è approssimativamente uguale alla visualizzazione [!UICONTROL Line].
* Il widget **Geomap** è approssimativamente uguale alla visualizzazione [!UICONTROL Map].
* Il widget **Tabella** è approssimativamente uguale alla visualizzazione [!UICONTROL Freeform Table].
* Il widget **Torta** è approssimativamente uguale alla visualizzazione [!UICONTROL Donut].
* Il widget **Barre** è approssimativamente uguale alla visualizzazione [!UICONTROL Bar].

[!UICONTROL Analysis Workspace] include molte altre opzioni di visualizzazione per presentare i dati nel modo migliore per le tue esigenze di reporting. Per ulteriori informazioni, consulta [Visualizzazioni in Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) nella Guida utente di Analyze.

### Condivisione di progetti

Dopo aver aggiunto il contenuto a un progetto, puoi condividerlo.

* Per condividere il progetto con i tuoi colleghi, vai a **[!UICONTROL Share > Share Project]**. I destinatari sono altri utenti dell’organizzazione che dispongono di account Adobe Analytics.
* Per condividere il progetto tramite un collegamento, vai a **[!UICONTROL Share > Get Project Link]**. Tieni presente che questo richiede ancora un accesso ad Adobe Analytics all’interno della tua organizzazione.

### Esportazione di progetti

Oltre a PDF, [!UICONTROL Analysis Workspace] offre un&#39;esportazione CSV.

1. Fare clic su *[!UICONTROL Share]* > *[!UICONTROL Send File Now]* per aprire una finestra modale.
2. Specifica il tipo di file e i destinatari.
3. Fai clic su [!UICONTROL Send Now].

## Rapporti personalizzati

Quando crei un rapporto personalizzato nelle Google Analytics, i campi richiesti sono simili al flusso di lavoro per la creazione di una visualizzazione nell’area di lavoro. Le definizioni di Dimension, metriche e filtri sono simili tra le piattaforme. In Analysis Workspace, invece di selezionare dimensioni e metriche da un elenco, dimensioni e metriche vengono trascinate in una tabella a forma libera.

### Metriche calcolate nei rapporti personalizzati

I rapporti personalizzati sono una delle poche aree nelle Google Analytics che consentono l’utilizzo di metriche calcolate. Poiché Analysis Workspace funziona come un’area di lavoro, le metriche calcolate funzionano retroattivamente e in qualsiasi contesto.

Per creare una metrica calcolata:

1. Fai clic sull&#39;icona **+** accanto all&#39;elenco delle metriche per aprire [!UICONTROL Calculated Metric Builder].
2. Assegna un nome alla metrica calcolata e specifica un formato.
3. Trascina i componenti della metrica in nell’area di definizione e utilizza gli elenchi a discesa tra ciascun componente per designare un operatore.
4. Una volta che la metrica calcolata contiene la formula desiderata, fai clic su Salva per tornare al tuo workspace.
5. Trascina la metrica calcolata appena definita nell’area di lavoro.

   Ulteriori informazioni su [Metriche calcolate](/help/components/c-calcmetrics/cm-overview.md) nella guida utente Componenti.

## Avvisi personalizzati

Gli avvisi sono disponibili su entrambe le piattaforme. In Adobe Analytics, usa il menu di navigazione dell&#39;intestazione e vai a *[!UICONTROL Components]* > *[!UICONTROL Alerts]*. Per ulteriori informazioni, vedere [Panoramica degli avvisi](/help/components/c-alerts/intellligent-alerts.md) nella Guida utente dei componenti.
