---
description: Utilizza Report Builder con Microsoft Power BI.
title: 'Pubblicare su Power BI: panoramica'
feature: Report Builder
role: User, Admin
exl-id: 3464c153-2db5-41af-9e83-da081ec64ad3
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 13%

---

# Pubblicare su Power BI: panoramica

Microsoft Power BI è una suite di dashboard di analisi business per l’analisi dei dati e la condivisione di approfondimenti. L’integrazione di Adobe Analytics con Power BI consente di visualizzare i dati del Report Builder di Analytics all’interno di Microsoft Power BI e di condividerli facilmente in tutta l’organizzazione.

Precedentemente l’analista pianificava la diffusione delle cartelle di lavoro del Report Builder tramite e-mail (o ftp). Ora è possibile consentire agli utenti aziendali interessati di accedere (dall’interno dei loro account Power BI) a dati precisi e aggiornati in un ambiente basato sul web accessibile su più piattaforme e dispositivi.

La combinazione della capacità di generazione rapporti di Report Builder e delle funzionalità di visualizzazione di Power BI rende le informazioni più accessibili per tutti coloro che fanno parte dell’organizzazione. Con Power BI, puoi anche integrare Adobe Analytics con altre origini dati (ad esempio punto vendita, CRM) per scoprire approfondimenti specifici sui clienti, associazioni e opportunità.

![](assets/aaplusbi.png)

## Requisiti di sistema {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 [installato](/help/analyze/report-builder/setup/t-install-arb.md)
* Account Microsoft attivo che consente di accedere a Power BI

## Pubblica cartella di lavoro su Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

Le cartelle di lavoro pianificate sono fogli di calcolo Excel formattati con dati provenienti da Adobe Analytics e inviati regolarmente secondo la pianificazione.

**Pubblica cartella di lavoro nel Report Builder**

1. In Report Builder, generare e salvare una cartella di lavoro.
1. Sulla barra degli strumenti del Report Builder fare clic su **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Nella Pianificazione guidata di base, seleziona la casella accanto a **[!UICONTROL Publish Workbook to Microsoft Power BI]**.

   ![](assets/simple-schedule-wizard.png)

1. Specifica l’e-mail e l’invio immediato oppure la frequenza di pianificazione (oraria, giornaliera, ecc.).
1. Clic **[!UICONTROL OK]** per la pubblicazione.
1. Ora ti verrà chiesto di accedere al tuo account Microsoft. Immetti le tue credenziali.
1. La cartella di lavoro del Report Builder viene pianificata e pubblicata in Power BI.

   Con ogni istanza pianificata e dopo che il processo di pianificazione di Report Builder ha aggiornato la cartella di lavoro con i dati di Analytics aggiornati, la cartella di lavoro verrà pubblicata in Microsoft Power BI.

**Visualizza dati cartella di lavoro di Report Builder in Power BI**

1. In Power BI, fare doppio clic sulla cartella di lavoro sotto [!UICONTROL Workbooks] menu.

   ![](assets/workbooks-power-bi.png)

1. È ora possibile visualizzare i dati del dashboard della cartella di lavoro.  ![](assets/view-data-pbi.png)

1. È quindi possibile fissare un&#39;area della cartella di lavoro per includerla in una delle dashboard di Power BI.

## Pubblica tutte le tabelle formattate nella cartella di lavoro come tabelle di set di dati Power BI {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE]
>
>Se la cartella di lavoro contiene una macro, l&#39;opzione &quot;Pubblica tutte le tabelle formattate nella cartella di lavoro come tabelle di set di dati di Power BI&quot; verrà disattivata.

Anziché importare l&#39;intera cartella di lavoro, è possibile importare solo il contenuto di tutte le tabelle formattate all&#39;interno della cartella di lavoro.

**Caso d’uso**: una cartella di lavoro di Excel consente di estrarre dati da più richieste di Report Builder e di creare una tabella di riepilogo con numerose formule. Puoi importare solo la tabella di riepilogo in Power BI e crearne una visualizzazione.

**Pubblicare una tabella formattata nel Report Builder**

1. In Report Builder, genera una tabella di dati che includa una riga di intestazione, seguita da una riga di dati.
1. Seleziona la tabella e seleziona. **[!UICONTROL Format as Table]** dal [!UICONTROL Home] menu. La tabella viene denominata per impostazione predefinita (Tabella 1, Tabella 2, ecc.), ma è possibile modificarne il nome in [!UICONTROL Design]menu.

1. Sulla barra degli strumenti del Report Builder fare clic su **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Nella Pianificazione guidata di base, fare clic su **[!UICONTROL Advanced Scheduling Options]**.
1. In [!UICONTROL Scheduling Wizard - Advanced], sulla **[!UICONTROL Publishing Options]** , seleziona la casella accanto a **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**.

   ![](assets/advanced-schedule-wizard2.png)

1. (Facoltativo) Puoi personalizzare in Power BI il nome della risorsa pubblicata. Ciò può essere utile se si utilizza il controllo delle versioni come parte del nome della cartella di lavoro (ad esempio, myfolder_v1.1.xlsx) e non si desidera che il numero di versione venga visualizzato nel nome della risorsa Power BI pubblicata. Offre il vantaggio aggiunto che la risorsa pubblicata non cambierà se cambia il numero di versione. (Visualizza [specifiche](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md) qui.)

**Visualizzare i dati della tabella in Power BI**

1. In Power BI, vai al **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** menu.

   ![](assets/datasets-menu.png)

1. Seleziona il set di dati pubblicato e fai clic su [!UICONTROL Create report] accanto. Le tabelle verranno visualizzate come Campi.

   ![](assets/formatted-tables.png)

1. Selezionare una tabella e le colonne associate.

   ![](assets/view-table-dataset.png)

1. Dalla sezione [!UICONTROL Visualizations] puoi selezionare la modalità di visualizzazione di una tabella in Power BI. Ad esempio, puoi scegliere di presentare i dati come un grafico a linee:

   ![](assets/bi-line-graph.png)

1. Da qui puoi creare visualizzazioni da questa tabella di set di dati.

## Pubblica tutte le richieste di Report Builder come tabelle di set di dati di Power BI {#section_0C26057C7DBB4068A643FDD688F6E463}

Puoi trasformare tutte le richieste in tabelle di set di dati e aggiungere visualizzazioni.

>[!IMPORTANT]
>
>Se la cartella di lavoro contiene più di 100 richieste, solo le prime 100 richieste verranno pubblicate in Power BI. Inoltre, per ogni richiesta pubblicata in Power BI, verranno pubblicate solo le prime 10.000 righe di dati. Pertanto, anche se queste richieste verranno consegnate correttamente tramite la pianificazione, l’ambito di pubblicazione in Power BI è limitato.

1. In Report Builder aprire o creare una cartella di lavoro con richieste di Report Builder.
1. Sulla barra degli strumenti del Report Builder fare clic su **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Nella Pianificazione guidata di base, fare clic su **[!UICONTROL Advanced Scheduling Options]**.
1. In [!UICONTROL Scheduling Wizard - Advanced], sulla **[!UICONTROL Publishing Options]** , seleziona la casella accanto a **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]** ![](assets/advanced-schedule-wizard2.png)

1. Fai clic su **[!UICONTROL OK]** (Usa modello di attribuzione non predefinito).

**Visualizzare i dati della richiesta in Power BI**

Ogni richiesta di Report Builder pianificata verrà pubblicata come tabella nel set di dati. Ogni tabella di richiesta è denominata in base alla dimensione primaria nella richiesta e presenta una [!UICONTROL Report Suite] e un [!UICONTROL Segments] colonna.

1. In Power BI, vai al **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** menu.

1. Seleziona la richiesta pubblicata e fai clic su [!UICONTROL Create report] accanto.

   Le richieste vengono visualizzate come tabelle nella sezione [!UICONTROL Fields] menu.

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >Indipendentemente dal modo in cui hai configurato la richiesta di Report Builder per essere impostata sul foglio di lavoro (layout pivot, layout personalizzato, alcune colonne invisibili), il Report Builder pubblicherà sempre la richiesta nello stesso formato bidimensionale di riga a intestazione singola: Data, Dimension, Metriche, Suite di rapporti, Segmenti.

1. Inoltre, è disponibile una tabella aggiuntiva denominata **[!UICONTROL Legend]**. Se elimini una richiesta dal contesto del Report Builder, potrebbe essere difficile ricordare per cosa sta una richiesta. Lo scopo della tabella Legenda è, ad esempio, quello di mostrare il nome di ogni richiesta in ID tabella. Puoi anche aggiungere le altre colonne della legenda per ottenere una visualizzazione completa della richiesta.

   ![](assets/legend-table.png)
