---
title: Personalizzazione dei rapporti in Adobe Analytics
description: Scopri come personalizzare i rapporti in Adobe Analytics
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 1%

---

# Personalizzare i rapporti

Nelle piattaforme di terze parti, come ad esempio Google Analytics, sono disponibili diverse opzioni di personalizzazione. Queste personalizzazioni consentono a un utente di creare dashboard, rapporti personalizzati, rapporti salvati e avvisi personalizzati. Poiché Analysis Workspace consente agli utenti di creare rapporti da un’area di lavoro vuota, la maggior parte delle personalizzazioni viene incorporata direttamente nello strumento.

Questa pagina presuppone che l’utente abbia una conoscenza di base dell’utilizzo di [!UICONTROL Analysis Workspace]. Consulta [Creazione di un rapporto di base in Analysis Workspace per gli utenti Google Analytics](reports/create-report.md) se non hai ancora familiarità con lo strumento in Adobe Analytics.

## Dashboard

Il [!UICONTROL Analysis Workspace] L&#39;architettura è simile al concetto di widget del dashboard. Progetti in [!UICONTROL Analysis Workspace] sono approssimativamente equivalenti alle dashboard nelle Google Analytics. Visualizzazioni in [!UICONTROL Analysis Workspace] sono l’equivalente approssimativo dei widget nelle Google Analytics.

### Aggiunta di contenuto a un progetto

1. Fai clic su [!UICONTROL Visualizations] a sinistra e trascinare la visualizzazione desiderata sul workspace.
2. Fai clic su [!UICONTROL Components] a sinistra e trascina le dimensioni e le metriche desiderate nella visualizzazione per compilarla con i dati.
3. Trascina i bordi della visualizzazione per ridimensionarla e trascina il titolo della visualizzazione per spostarla.

Tutti i widget Google Analytics sono disponibili in [!UICONTROL Analysis Workspace]:

* Il **Widget metrica** è approssimativamente uguale al valore [!UICONTROL Summary Number] visualizzazione.
* Il **Widget sequenza temporale** è approssimativamente uguale al valore [!UICONTROL Line] visualizzazione.
* Il **Widget Geomap** è approssimativamente uguale al valore [!UICONTROL Map] visualizzazione.
* Il **Widget tabella** è approssimativamente uguale al valore [!UICONTROL Freeform Table] visualizzazione.
* Il **Widget a torta** è approssimativamente uguale al valore [!UICONTROL Donut] visualizzazione.
* Il **Widget barra** è approssimativamente uguale al valore [!UICONTROL Bar] visualizzazione.

[!UICONTROL Analysis Workspace] include molte più opzioni di visualizzazione per presentare i dati nel modo migliore per le tue esigenze di reporting. Consulta [Visualizzazioni in Analysis Workspace](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) nella Guida utente di Analyze per ulteriori informazioni.

### Condivisione di progetti

Dopo aver aggiunto il contenuto a un progetto, puoi condividerlo.

* Per condividere il progetto con i colleghi, vai a **[!UICONTROL Share > Share Project]**. I destinatari sono altri utenti dell’organizzazione che dispongono di account Adobe Analytics.
* Per condividere il progetto tramite un collegamento, vai a **[!UICONTROL Share > Get Project Link]**. Tieni presente che questo richiede ancora un accesso ad Adobe Analytics all’interno della tua organizzazione.

### Esportazione di progetti

Oltre a PDF, [!UICONTROL Analysis Workspace] offre un’esportazione CSV.

1. Clic *[!UICONTROL Share]* > *[!UICONTROL Send File Now]*, che apre una finestra modale.
2. Specifica il tipo di file e i destinatari.
3. Fai clic su [!UICONTROL Send Now] (Usa modello di attribuzione non predefinito).

## Rapporti personalizzati

Quando crei un rapporto personalizzato nelle Google Analytics, i campi richiesti sono simili al flusso di lavoro per la creazione di una visualizzazione nell’area di lavoro. Le definizioni di Dimension, metriche e filtri sono simili tra le piattaforme. In Analysis Workspace, invece di selezionare dimensioni e metriche da un elenco, dimensioni e metriche vengono trascinate in una tabella a forma libera.

### Metriche calcolate nei rapporti personalizzati

I rapporti personalizzati sono una delle poche aree nelle Google Analytics che consentono l’utilizzo di metriche calcolate. Poiché Analysis Workspace funziona come un’area di lavoro, le metriche calcolate funzionano retroattivamente e in qualsiasi contesto.

Per creare una metrica calcolata:

1. Fai clic su **+** vicino all’elenco delle metriche per aprire [!UICONTROL Calculated Metric Builder].
2. Assegna un nome alla metrica calcolata e specifica un formato.
3. Trascina i componenti della metrica in nell’area di definizione e utilizza i menu a discesa tra ciascun componente per designare un operatore.
4. Una volta che la metrica calcolata contiene la formula desiderata, fai clic su Salva per tornare al tuo workspace.
5. Trascina la metrica calcolata appena definita nell’area di lavoro.

   Ulteriori informazioni su [Metriche calcolate](/help/components/c-calcmetrics/cm-overview.md) nella guida utente Componenti.

## Avvisi personalizzati

Gli avvisi sono disponibili su entrambe le piattaforme. In Adobe Analytics, utilizza il menu di navigazione dell’intestazione e vai a *[!UICONTROL Components]* > *[!UICONTROL Alerts]*. Consulta [Avvisi intelligenti](/help/components/c-alerts/intellligent-alerts.md) nella Guida utente dei componenti per ulteriori informazioni.
