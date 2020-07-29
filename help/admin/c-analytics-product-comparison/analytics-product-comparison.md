---
description: Requisiti di sistema e confronto tra Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder, Data Warehouse e Data Workbench
title: Requisiti e confronto dei prodotti Analytics
translation-type: tm+mt
source-git-commit: 0885a42ccf79565d2ad55cf84e346926f2328f77
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 50%

---


# Analytics Requisiti e confronto dei prodotti 

Questa pagina contiene un confronto tra vari prodotti  Adobe Analytics:  Analysis Workspace, Reporting e  Analytics, Report Builder, Data warehouse, Data Workbench, feed di dati e  Analytics API 2.0.

Per informazioni sul prodotto Adobe Analytics da utilizzare, consulta [questo articolo](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nome prodotto e collegamento all’Aiuto | [Analysis Workspace](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/it-IT/analytics/analyze/reports-analytics/getting-started.html) | [Report Builder](https://docs.adobe.com/content/help/it-IT/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/it-IT/analytics/export/data-warehouse/data-warehouse.translate.html) | [Data Workbench](https://docs.adobe.com/content/help/it-IT/data-workbench/using/home.html) | [Feed dati](https://docs.adobe.com/content/help/it-IT/analytics/export/analytics-data-feed/data-feed-overview.html) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Metodo Access** | [Browser](https://docs.adobe.com/content/help/it-IT/analytics/admin/sys-reqs.html) | [Browser](https://docs.adobe.com/content/help/it-IT/analytics/admin/sys-reqs.html) | [MS Excel per Windows](https://docs.adobe.com/content/help/it-IT/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | Configurazione tramite browser. Le destinazioni supportate includono l&#39;FTP. Rivolgiti all&#39;Assistenza clienti per ricevere ulteriore assistenza sulla destinazione. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/admin/sys-reqs.html) | [Windows a 64 bit](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html) | Configurazione tramite il browser. Le destinazioni supportate includono FTP, SFTP, Azure Blob, S3. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/export/analytics-data-feed/data-feed-overview.html) | Strumenti RESTful API. Effettuate l&#39;accesso con  credenziali di I/O Adobe. [Ulteriori informazioni](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Formato dati (granularità)** | Aggregata | Aggregata | Aggregata | ECID | Timestamp + ECID | Timestamp + ECID | Aggregata |
| **Livello di elaborazione** | Completamente elaborato | Elaborazione completa, con report in tempo [reale separati](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | Elaborazione completa, con report in tempo [reale separati](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | Completamente elaborato | Completamente elaborato | Completamente elaborato | Completamente elaborato |
| **Dati filtro bot amministratore inclusi** <br>[Per saperne di più](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html) | No | Sì - Rapporto bot separato | Sì - Rapporto bot separato | No | No | No | No |
| **Viene visualizzato** il traffico limitato (Superato il numero di errori) <br>[Ulteriori informazioni](https://docs.adobe.com/content/help/en/analytics/technotes/low-traffic.html) | Sì | Sì | Sì | No | No | No | Sì |
| **Limite righe visibili (prima dell’impaginazione)** | 400 | 200 | 50000 | Senza limiti | Senza limiti | Senza limiti | 50000 |
| **Più suite di rapporti** | [Sì](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) | Sì, con limitazioni | Sì | No | Sì | No | Sì |
| **Numero di analisi approfondite** | Senza limiti | Fino a 2 | Fino a 2 | Senza limiti | Senza limiti | Senza limiti | Senza limiti, eseguite tra più query |
| **Segmentazione** <br>[Ulteriori informazioni](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) | Sì | Sì | Sì | Sì, con [limitazioni](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-compatibility.html) | Sì | No | Sì |
| **Metriche** calcolate <br>[Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/cm-overview.html) | Sì, con [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | Sì | Sì | No | Sì | No | Sì, con [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Canali** di marketing <br>[Per saperne di più](https://docs.adobe.com/content/help/it-IT/analytics/components/marketing-channels/c-getting-started-mchannel.html) | Sì | Sì | Sì | Sì | Sì | Sì - [va_finder, va_closer](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html) | Sì |
| **Analisi per coorte** | [Sì](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | No | No | No | Sì | No | No |
| **Attribution** | Sì, con [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | Limitato | Limitato | No | Sì | No | Sì, con [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Funzionalità** Analista virtuale <br>[Per saperne di più](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/overview.html) | Sì | No | No | No | No | No | Sì |
| **Cura** <br>[Per saperne di più](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/curate-share/curate.html) | Sì - Progetto e VRS | No | No | No | No | No | Sì, solo VRS |
| **Condivisione** dei progetti <br>[Per saperne di più](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Sì, con i ruoli del progetto | Sì | Sì | No | Sì | No | No |
| **Spedizione pianificata** | Sì | Sì | Sì | Sì | Sì | Sì | No |
| **Elaborazione** del tempo del rapporto VRS <br>[Per saperne di più](https://docs.adobe.com/content/help/it-IT/analytics/components/virtual-report-suites/vrs-report-time-processing.html) | Sì | No | No | No | No | No | Sì |
