---
title: Personalizzazione dei rapporti in Adobe Analytics
description: Scopri come personalizzare i rapporti in Adobe Analytics
feature: Third-party Integration
exl-id: 8ea6ec3a-cfc6-4c14-966b-d245949451c7
TQID: https://experienceleague.adobe.com/vvVKR7JKV12zgIic0rso4OihH5kyAoZBV983R3VmOic
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e3e906cf-5493-4e0a-9a33-bf0ac37393d6
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 567
ht-degree: 0%

---

# Personalizzare i rapporti

Nelle piattaforme di terze parti, come Google Analytics, sono disponibili diverse opzioni di personalizzazione. Queste personalizzazioni consentono a un utente di creare dashboard, rapporti personalizzati, rapporti salvati e avvisi personalizzati. Poiché Analysis Workspace consente agli utenti di creare rapporti da un’area di lavoro vuota, la maggior parte delle personalizzazioni viene incorporata direttamente nello strumento.

Questa pagina presuppone che l&#39;utente abbia una conoscenza di base dell&#39;utilizzo di [!UICONTROL Analysis Workspace]. Se non conosci ancora lo strumento in Analysis Workspace, consulta [Creare un report di base in Adobe Analytics per gli utenti di Google Analytics](reports/create-report.md).

## Dashboard

L&#39;architettura [!UICONTROL Analysis Workspace] è stata creata in modo simile al concetto di widget del dashboard. I progetti in [!UICONTROL Analysis Workspace] equivalgono approssimativamente alle dashboard in Google Analytics. Le visualizzazioni in [!UICONTROL Analysis Workspace] sono l&#39;equivalente approssimativo dei widget in Google Analytics.

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

Durante la creazione di un rapporto personalizzato in Google Analytics, i campi richiesti sono simili al flusso di lavoro per la creazione di una visualizzazione in Workspace. Le definizioni di dimensioni, metriche e filtri sono simili tra le piattaforme. In Analysis Workspace, invece di selezionare dimensioni e metriche da un elenco, dimensioni e metriche vengono trascinate in una tabella a forma libera.

### Metriche calcolate nei rapporti personalizzati

I rapporti personalizzati sono una delle poche aree di Google Analytics che consentono l’utilizzo di metriche calcolate. Poiché Analysis Workspace funziona come un’area di lavoro, le metriche calcolate funzionano retroattivamente e in qualsiasi contesto.

Per creare una metrica calcolata:

1. Fai clic sull&#39;icona **+** accanto all&#39;elenco delle metriche per aprire [!UICONTROL Calculated Metric Builder].
2. Assegna un nome alla metrica calcolata e specifica un formato.
3. Trascina i componenti della metrica in nell’area di definizione e utilizza gli elenchi a discesa tra ciascun componente per designare un operatore.
4. Una volta che la metrica calcolata contiene la formula desiderata, fai clic su Salva per tornare al tuo workspace.
5. Trascina la metrica calcolata appena definita nell’area di lavoro.

   Ulteriori informazioni su [Metriche calcolate](/help/components/calculated-metrics/cm-overview.md) nella guida utente Componenti.

## Avvisi personalizzati

Gli avvisi sono disponibili su entrambe le piattaforme. In Adobe Analytics, usa il menu di navigazione dell&#39;intestazione e vai a *[!UICONTROL Components]* > *[!UICONTROL Alerts]*. Per ulteriori informazioni, vedere [Panoramica degli avvisi](/help/components/alerts/alerts-overview.md) nella Guida utente dei componenti.
