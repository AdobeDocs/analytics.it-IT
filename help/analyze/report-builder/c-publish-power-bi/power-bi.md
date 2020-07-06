---
description: 'null'
title: 'Pubblicare su Power BI: panoramica'
uuid: ad688817-6e3c-45da-983d-48c123465309
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 13%

---


# Pubblicare su Power BI: panoramica

Microsoft Power BI è una suite di dashboard di analisi business per l’analisi dei dati e la condivisione di approfondimenti. L’integrazione di Adobe Analytics con Power BI consente di visualizzare i dati del Report Builder di Analytics all’interno di Microsoft Power BI e di condividerli facilmente in tutta l’organizzazione.

Precedentemente l’analista pianificava la diffusione delle cartelle di lavoro del Report Builder tramite e-mail (o ftp). Ora è possibile consentire agli utenti aziendali interessati di accedere (dall’interno dei loro account Power BI) a dati precisi e aggiornati in un ambiente basato sul web accessibile su più piattaforme e dispositivi.

La combinazione della capacità di generazione rapporti di Report Builder e delle funzionalità di visualizzazione di Power BI rende le informazioni più accessibili per tutti coloro che fanno parte dell’organizzazione. Con Power BI, puoi anche integrare Adobe  Analytics con altre origini dati (ad es. punto vendita, CRM) per scoprire approfondimenti, associazioni e opportunità esclusive per i clienti.

![](assets/aaplusbi.png)

L&#39;integrazione con Report Builder Adobe consente di

* [Pubblicare cartelle di lavoro del Generatore di report programmati su Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [Pubblicare tutte le tabelle formattate nella cartella di lavoro come tabelle DataSet Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [Pubblica tutte le richieste del Generatore di report come tabelle DataSet Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)

## Requisiti di sistema {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 [installato](/help/analyze/report-builder/setup/t-install-arb.md)
* Account Microsoft attivo che consente di accedere a Power BI

## Pubblica cartella di lavoro in Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

Le cartelle di lavoro pianificate sono fogli di calcolo Excel formattati con dati di Adobe  Analytics e inviati su base regolare.

**Pubblica cartella di lavoro nel Generatore di report**

1. In Generatore di report, genera e salva una cartella di lavoro.
1. Nella barra degli strumenti del Generatore di report, fai clic su **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Nella Pianificazione guidata di base, selezionare la casella accanto a **[!UICONTROL Publish Workbook to Microsoft Power BI]**.

   ![](assets/simple-schedule-wizard.png)

1. Specificate l’e-mail e inviate immediatamente o specificate la frequenza di programmazione (ogni ora, giorno, ecc.).
1. Fate clic **[!UICONTROL OK]** per pubblicare.
1. Ora ti verrà chiesto di accedere al tuo account Microsoft. Immettete le vostre credenziali.
1. La cartella di lavoro del Generatore di report viene pianificata e pubblicata in Power BI.

   Per ogni istanza pianificata e dopo che il processo di pianificazione del Generatore di report ha aggiornato la cartella di lavoro con  dati Analytics aggiornati, la cartella di lavoro verrà pubblicata in Microsoft Power BI.

**Visualizzare i dati della cartella di lavoro del Generatore di report in Power BI**

1. In Power BI, fare doppio clic sulla cartella di lavoro nel [!UICONTROL Workbooks] menu.

   ![](assets/workbooks-power-bi.png)

1. È ora possibile visualizzare i dati del dashboard della cartella di lavoro.  ![](assets/view-data-pbi.png)

1. È quindi possibile fissare un&#39;area della cartella di lavoro per includerla in qualsiasi dashboard di Power BI.

## Publish all formatted tables in the workbook as Power BI dataset tables {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE]
>
>Se la cartella di lavoro contiene una macro, l&#39;opzione &quot;Pubblica tutte le tabelle formattate nella cartella di lavoro come tabelle DataSet Power BI&quot; verrà disattivata.

Anziché importare l&#39;intera cartella di lavoro, è possibile importare solo il contenuto di tutte le tabelle formattate all&#39;interno della cartella di lavoro.

**Caso** di utilizzo: È disponibile una cartella di lavoro Excel che raccoglie dati da più richieste del Generatore di report e crea una tabella di riepilogo con molte formule. È possibile importare solo la tabella di riepilogo in Power BI e creare una visualizzazione per tale tabella.

**Pubblicare una tabella formattata nel Generatore di report**

1. Nel Generatore di report, genera una tabella di dati che include una riga di intestazione seguita da una riga di dati.
1. Selezionare la tabella e **[!UICONTROL Format as Table]** dal [!UICONTROL Home] menu. La tabella viene denominata per impostazione predefinita (Tabella 1, Tabella 2, ecc.), ma è possibile modificare il nome nel [!UICONTROL Design]menu.

1. Nella barra degli strumenti del Generatore di report, fai clic su **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Nella Pianificazione guidata di base, fare clic su **[!UICONTROL Advanced Scheduling Options]**.
1. Nella [!UICONTROL Scheduling Wizard - Advanced]scheda, **[!UICONTROL Publishing Options]** selezionare la casella accanto a **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**.

   ![](assets/advanced-schedule-wizard2.png)

1. (Facoltativo) È possibile personalizzare il nome della risorsa pubblicata in Power BI. Questo può essere utile se utilizzate il controllo delle versioni come parte del nome della cartella di lavoro (ad esempio, myfolder_v1.1.xlsx) e non desiderate che il numero di versione venga visualizzato nel nome della risorsa Power BI pubblicata. Inoltre, se cambia il numero di versione, la risorsa pubblicata non subirà modifiche. (Vedi [le specifiche](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md) qui.)

**Visualizzazione dei dati della tabella in Power BI**

1. In Power BI, passare al menu **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** .

   ![](assets/datasets-menu.png)

1. Selezionate il set di dati pubblicato e fate clic sull’ [!UICONTROL Create report] icona accanto ad esso. Le tabelle verranno visualizzate come Campi.

   ![](assets/formatted-tables.png)

1. Selezionare una tabella e le relative colonne associate.

   ![](assets/view-table-dataset.png)

1. Dal [!UICONTROL Visualizations] menu è possibile selezionare la modalità di visualizzazione di una tabella in Power BI. Ad esempio, puoi scegliere di presentare i dati come grafico a linee:

   ![](assets/bi-line-graph.png)

1. Da qui, puoi creare visualizzazioni da questa tabella di dati.

## Publish all Report Builder requests as Power BI Dataset tables {#section_0C26057C7DBB4068A643FDD688F6E463}

Puoi trasformare tutte le tue richieste in tabelle di set di dati e creare visualizzazioni su di esse.

>[!IMPORTANT]
>
>Se la cartella di lavoro contiene più di 100 richieste, solo le prime 100 richieste verranno pubblicate in Power BI. Inoltre, per ogni richiesta pubblicata in Power BI, verranno pubblicate solo le prime 10.000 righe di dati. Quindi, mentre queste richieste verranno distribuite correttamente tramite la pianificazione, l&#39;ambito di pubblicazione in Power BI è limitato.

1. In Generatore di report, aprire o creare una cartella di lavoro con richieste Generatore di report.
1. Nella barra degli strumenti del Generatore di report, fai clic su **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. Nella Pianificazione guidata di base, fare clic su **[!UICONTROL Advanced Scheduling Options]**.
1. Nella [!UICONTROL Scheduling Wizard - Advanced], nella **[!UICONTROL Publishing Options]** scheda, selezionare la casella accanto a **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]** ![](assets/advanced-schedule-wizard2.png)

1. Fai clic su **[!UICONTROL OK]**.

**Visualizzare i dati della richiesta in Power BI**

Ogni richiesta Generatore di report pianificata verrà pubblicata come tabella nel dataset. Ogni tabella di richieste ha un nome in base alla dimensione primaria nella richiesta e ha una [!UICONTROL Report Suite] e una [!UICONTROL Segments] colonna.

1. In Power BI, passare al menu **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** .

1. Selezionate la richiesta pubblicata e fate clic sull’ [!UICONTROL Create report] icona accanto.

   Le richieste vengono visualizzate come tabelle nel [!UICONTROL Fields] menu.

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >Indipendentemente dalla configurazione della richiesta del Generatore di report da inserire nel foglio di lavoro (layout pivot, layout personalizzato, alcune colonne invisibili), il Generatore di report pubblicherà sempre la richiesta nello stesso formato bidimensionale di riga singola dell&#39;intestazione: Data, Dimensioni, Metriche, Suite di rapporti, Segmenti.

1. È inoltre disponibile una tabella aggiuntiva denominata **[!UICONTROL Legend]**. Se si toglie una richiesta dal contesto del Generatore di report, potrebbe essere difficile ricordare per cosa si intende ogni richiesta. Lo scopo della tabella Legenda è, ad esempio, quello di mostrarvi il nome di ogni richiesta in ID tabella. Potete inoltre aggiungere le altre colonne Legenda per ottenere una visualizzazione completa della richiesta.

   ![](assets/legend-table.png)

