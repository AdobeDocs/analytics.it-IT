---
description: Requisiti di sistema e confronto tra Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder, Data Warehouse e Data Workbench
title: Requisiti e confronto dei prodotti Analytics
translation-type: tm+mt
source-git-commit: 9265fb410b20a764ecc86c56b453b045122fcd05
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 76%

---


# Analytics Requisiti e confronto dei prodotti 

Requisiti di sistema e confronto tra Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis, Report Builder, Data Warehouse e Data Workbench.

Per informazioni sul prodotto Adobe Analytics da utilizzare, consulta [questo articolo](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nome prodotto e collegamento all’Aiuto | [Analysis Workspace](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/reports-analytics/getting-started.html) | [Ad Hoc Analysis](https://docs.adobe.com/content/help/it-IT/analytics/analyze/ad-hoc-analysis/adhoc-home.html) | [Report Builder](https://docs.adobe.com/content/help/it-IT/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/it-IT/analytics/export/data-warehouse/data-warehouse.translate.html) | [Data Workbench](https://docs.adobe.com/content/help/it-IT/data-workbench/using/home.html) |
|---|---|---|---|---|---|---|
| **Metodo di accesso** | Soluzione browser per la creazione di solidi progetti di analisi personalizzata e la democratizzazione delle informazioni. | Soluzione browser per l’analisi digitale. | Strumento basato su Java per l’analisi digitale avanzata. | Componente aggiuntivo per Excel che consente di creare richieste personalizzate a partire da dati di R&amp;A e di visualizzarle con Microsoft Excel. | Soluzione browser per la generazione di rapporti in formato  .csv . Può generare file in formato Tableau. | Strumento per l’analisi multicanale avanzata, ad esempio modellazione di attribuzione personalizzata, analisi predittive e analisi cliente a 360°. |
| **Suddivisioni dei rapporti** | Senza limiti | Fino a 2 correlazioni | Senza limiti | Fino a 2 correlazioni | Suddivisioni approfondite e illimitate, per segmento. | Senza limiti |
| **Confronti tra segmenti** | Senza limiti | Fino a 2 segmenti | Senza limiti | Senza limiti (stack di richieste di dati) | 1 segmento. Supporta più segmenti (in stack). | Senza limiti |
| **Limite di righe di output** | 400 | 200 | 50.000 | 50.000 | Senza limiti | Personalizzabile |
| **** Limiti di valori univoci (nei rapporti eVar/prop) | 500.000 - 2 milioni | 500.000 - 2 milioni | 500.000 - 2 milioni | 500.000 - 2 milioni | Senza limiti | Personalizzabile |
| **Funnel/Percorsi** | Sì: [Abbandono](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)/[Flusso](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/flow/flow.html) | [Sì](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/reports.html) | [Sì](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-reports-paths.html) | Sì | No | Sì |
| **Analisi avanzata del percorso del cliente** | Yes: [Customer Journey Analytics](https://docs.adobe.com/content/help/it-IT/analytics-platform/using/cja-landing.html) | No | Sì | No | No | Sì |
| **Analisi per coorte** | [Sì](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | No | No | No | No | Sì |
| **Attribuzione avanzata** | [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution-iq.html) | Limitata - Primo/Ultimo/Lineare | Limitata - Primo/Ultimo/Lineare | Limitata - Primo/Ultimo/Lineare | Limitata - Primo/Ultimo/Lineare | Sì |
| **Opzioni di visualizzazione ottimizzate** | [Sì](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) | No | Sì | Sì | No | Sì |
| **Layout personalizzabile** | [Sì](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html) | Sì - [ Dashboard](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/dashboard.html) | No | [Sì](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/configure-the-custom-layout.html) | Ordinare i risultati per suddivisione o metrica. | Sì |
| **** Cura dei progetti (semplificazione dei rapporti per non utenti non analisti) | [Sì](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/curate-share/curate.html) | No | No | Sì | No | Sì |
| **Condivisione dei progetti** | [Sì: all/any users](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/curate-share/curate.html) | [Sì: all/any users](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html) | Solo con utenti di Ad Hoc Analysis | Sì: all/any users | No | Sì |
| **Distribuzione del report** pianificata | [Sì](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/schedule-projects.html) | [Sì](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html) | [Sì](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-schedule.html) | [Sì](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/t-schedule-a-data-request.html) | Sì | Sì |
| **Requisiti di sistema** | Browser<br>[Altro...](https://docs.adobe.com/content/help/it-IT/analytics/admin/sys-reqs.html) | <br>[BrowserAltro...](https://docs.adobe.com/content/help/it-IT/analytics/admin/sys-reqs.html) | <br>[JavaMore...](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-getting-started.html) | Windows, MS<br>[ExcelAltro...](https://docs.adobe.com/content/help/it-IT/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | Browser e programma per aprire file  .csv , come MS Excel. Può generare file in formato Tableau. | Windows 64 bit, good graphics adapter for OpenGL 3.2 [More...](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html) |
| **Compatibilità con Virtual Report Suite (elaborazione report)** | Sì | Sì | Sì | Sì | No | Sì? |
| **Più suite di rapporti** | Sì | No | No | No | No | Sì? |
| **Metriche calcolate** | Sì | Sì | Sì | Sì | Sì | Sì |
| **Compatibilità canale di marketing** | Sì | Sì | Sì | Sì | ? | ? |
| **Livello di granularità** |  |  |  |  |  |  |
| **Rilevamento delle anomalie** | Sì | No |  |  |  |  |
| **Analisi contributi** | Sì | No | No | No | No | Sì |
| **Tipi di segmenti** |  |  |  |  |  |  |