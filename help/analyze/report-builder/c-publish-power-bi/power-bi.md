---
description: nulle
seo-description: nulle
seo-title: Pubblica su Power BI - Panoramica
title: Pubblica su Power BI - Panoramica
uuid: ad 688817-6 e 3 c -45 da -983 d -48 c 123465309
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Pubblica su Power BI - Panoramica

Microsoft Power BI è una suite di dashboard di analisi business per l'analisi dei dati e la condivisione di approfondimenti. L'integrazione di Adobe Analytics con Power BI consente di visualizzare i dati di Analytics di Report Builder in Microsoft Power BI e di condividerli facilmente all'interno dell'organizzazione.

In precedenza, in qualità di Analista, le cartelle di lavoro del Generatore di report pianificavano la diffusione tramite e-mail (o ftp). Ora puoi offrire ai tuoi utenti interessati l'accesso (dall'interno dei loro account Power BI) a dati precisi e aggiornati in un ambiente basato sul Web accessibile su piattaforme e dispositivi diversi.

Combinando la funzionalità di generazione dei report di Generatore di report con le funzionalità di visualizzazione di Power BI, le informazioni sono più accessibili a tutti gli utenti dell'organizzazione. Con Power BI, puoi anche integrare Adobe Analytics con altre sorgenti dati (ad es. punto di vendita, CRM) per scoprire approfondimenti, associazioni e opportunità univoche sui clienti.

![](assets/aaplusbi.png)

L'integrazione con Generatore di report Adobe consente di

* [Pubblicare cartelle di lavoro pianificate per Generatore di report su Power BI](../../../analyze/report-builder/whats-new-arb.md#section_21CA66229EC240D49594A9A7D3FBA687)
* [Pubblica tutte le tabelle formattate nella cartella di lavoro come tabelle Dataset Power BI](../../../analyze/report-builder/whats-new-arb.md#section_7C54A54E75184DD6BAEF4ACCE241239A)
* [Pubblicare tutte le richieste di Generatore di report come tabelle Dataset Power BI](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463)

## System requirements {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 [installed](../../../analyze/report-builder/setup/t-install-arb.md#task_0CA66703882F469EB6DBD9298975D6C3)
* Account Microsoft attivo che consente di accedere a Power BI

## Publish workbook to Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

I documenti di lavoro pianificati sono fogli di calcolo Excel formattati compilati con dati provenienti da Adobe Analytics e inviati regolarmente.

**Pubblicare la cartella di lavoro in Generatore di report**

1. In Generatore di report, generate e salvate una cartella di lavoro.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** &gt; **[!UICONTROL New]**.

1. In the Basic Scheduling Wizard, check the box next to **[!UICONTROL Publish Workbook to Microsoft Power BI]**.

   ![](assets/simple-schedule-wizard.png)

1. Specificate l'e-mail e invia immediatamente o specificate la frequenza di pianificazione (oraria, giornaliera, ecc.).
1. Click **[!UICONTROL OK]** to publish.
1. Ti verrà ora chiesto di accedere al tuo account Microsoft. Fornite le vostre credenziali.
1. La cartella di lavoro Generatore di report viene pianificata e pubblicata su Power BI.

   Con ciascuna istanza pianificata e dopo che il processo di pianificazione di Generatore di report ha aggiornato la cartella di lavoro con i dati aggiornati di Analytics, la cartella di lavoro verrà pubblicata su Microsoft Power BI.

**Visualizzare i dati del cartella di lavoro di Generatore di report in Power BI**

1. In Power BI, double click the workbook under the [!UICONTROL Workbooks] menu.

   ![](assets/workbooks-power-bi.png)

1. You can now view the workbook dashboard data.  ![](assets/view-data-pbi.png)

1. Potete quindi fissare un'area della cartella di lavoro per includerla in una delle dashboard Power BI.

## Publish all formatted tables in the workbook as Power BI dataset tables {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE]
>
>Se la cartella di lavoro contiene una macro, l'opzione «Pubblica tutte le tabelle formattate nella cartella di lavoro come tabelle Dataset Power BI» verrà disattivata.

Invece di importare l'intera cartella di lavoro, potete importare solo il contenuto di tutte le tabelle formattate nella cartella di lavoro.

**Caso d'uso**: Disponete di una cartella di lavoro Excel che estrae i dati da più richieste di Generatore di report e crea una tabella di riepilogo con numerose formule. È possibile importare solo la tabella di riepilogo in Power BI e creare una visualizzazione.

**Pubblicare una tabella formattata in Generatore di report**

1. In Generatore di report, genera una tabella di dati che include una riga di intestazione, seguita da una riga di dati.
1. Select the table and select **[!UICONTROL Format as Table]** from the [!UICONTROL Home] menu. The table gets named by default (Table 1, Table 2, etc.), but you can change the name on the [!UICONTROL Design]menu.

1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** &gt; **[!UICONTROL New]**.

1. In the Basic Scheduling Wizard, click **[!UICONTROL Advanced Scheduling Options]**.
1. In the [!UICONTROL Scheduling Wizard - Advanced], on the **[!UICONTROL Publishing Options]**tab, check the box next to **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**.

   ![](assets/advanced-schedule-wizard2.png)

1. (Facoltativo) Potete personalizzare il nome della risorsa pubblicata in Power BI. Questo può risultare utile se utilizzate la funzione di gestione delle versioni come parte del nome della cartella di lavoro (ad esempio, myworkbook_v1.1.xlsx) e non desiderate che il numero di versione venga visualizzato nel nome della risorsa Power BI pubblicata. Offre un vantaggio aggiuntivo che la risorsa pubblicata non subirà modifiche se il numero di versione cambia. (View [specifications](../../../analyze/report-builder/c-publish-power-bi/specifications-limits.md#concept_1B6522B4D7A9482680198F125D94EEFD) here.)

**Visualizzare i dati della tabella in Power BI**

1. In Power BI, go to the **[!UICONTROL Workspaces]** &gt; **[!UICONTROL Datasets]** menu.

   ![](assets/datasets-menu.png)

1. Select the dataset that you published and click the [!UICONTROL Create report] icon next to it. Le tabelle vengono visualizzate come Campi.

   ![](assets/formatted-tables.png)

1. Selezionare una tabella e le relative colonne associate.

   ![](assets/view-table-dataset.png)

1. From the [!UICONTROL Visualizations] menu, you can select how to visualize a table in Power BI. Ad esempio, potete scegliere di presentare i dati come grafico a linee:

   ![](assets/bi-line-graph.png)

1. Da qui potete creare visualizzazioni da questa tabella di set di dati.

## Publish all Report Builder requests as Power BI Dataset tables {#section_0C26057C7DBB4068A643FDD688F6E463}

Puoi trasformare tutte le tue richieste in tabelle di set di dati e creare visualizzazioni su di esse.

>[!IMPORTANT]
>
>Se la cartella di lavoro contiene più di 100 richieste, solo le prime 100 richieste verranno pubblicate su Power BI. Inoltre, per ogni richiesta pubblicata su Power BI, verranno pubblicate solo le prime 10,000 righe di dati. Pertanto, quando queste richieste verranno distribuite correttamente tramite la pianificazione, l'ambito della pubblicazione su Power BI è limitato.

1. In Generatore di report, aprite o create una cartella di lavoro con le richieste Generatore di report.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** &gt; **[!UICONTROL New]**.

1. In the Basic Scheduling Wizard, click **[!UICONTROL Advanced Scheduling Options]**.
1. In the [!UICONTROL Scheduling Wizard - Advanced], on the **[!UICONTROL Publishing Options]**tab, check the box next to **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]** ![](assets/advanced-schedule-wizard2.png)

1. Fai clic su **[!UICONTROL OK]**.

**Visualizzare i dati della richiesta in Power BI**

Ogni richiesta di Generatore di report pianificata verrà pubblicata come tabella nel dataset di dati. Each request table is named after the primary dimension in the request and it has a [!UICONTROL Report Suite] and a [!UICONTROL Segments] column.

1. In Power BI, go to the **[!UICONTROL Workspaces]** &gt; **[!UICONTROL Datasets]** menu.

1. Select the request that you published and click the [!UICONTROL Create report] icon next to it.

   Notice that the requests appear as tables in the [!UICONTROL Fields] menu.

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >Indipendentemente dalla modalità in cui hai configurato la richiesta di Generatore di report per essere disposto sul foglio di lavoro (layout pivot, layout personalizzato, alcune colonne invisibile), Generatore di report pubblicherà sempre la tua richiesta nello stesso formato bidimensionale, riga di intestazione: Data, Dimensioni, Metriche, Suite di rapporti, Segmenti.

1. Also notice that there is an additional table called **[!UICONTROL Legend]**. Se si scatta una richiesta dal contesto di Generatore di report, potrebbe essere difficile ricordare quali sono le implicazioni di ogni richiesta. Lo scopo della tabella Legenda è, ad esempio, di mostrare il nome di ogni richiesta in Tabella ID. Potete anche aggiungere le altre colonne Legenda per ottenere una visualizzazione completa della richiesta.

   ![](assets/legend-table.png)

