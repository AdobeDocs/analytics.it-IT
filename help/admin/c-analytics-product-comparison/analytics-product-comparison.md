---
description: Requisiti di sistema e confronto tra Analysis Workspace, Reports & Analytics, Report Builder, Data Warehouse e Data Workbench
title: Requisiti e confronto dei prodotti Analytics
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 54%

---


# Analytics Requisiti e confronto dei prodotti

Questa pagina contiene un confronto tra vari prodotti  Adobe Analytics:  Analysis Workspace, Reporting e analisi, Report Builder, Data Warehouse, Data Workbench, feed di dati e API di Analytics 2.0.

Per informazioni sul prodotto Adobe Analytics da utilizzare, consulta [questo articolo](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nome prodotto e collegamento all’Aiuto | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://docs.adobe.com/content/help/it-IT/data-workbench/using/home.html) | [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md) | [API di Analytics 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Metodo Access** | [Browser](/help/admin/sys-reqs.md) | [Browser](/help/admin/sys-reqs.md) | [MS Excel per Windows](/help/analyze/report-builder/setup/system-requirements.md) | Configurazione tramite il browser. [Ulteriori informazioni](/help/admin/sys-reqs.md) | [Windows a 64 bit](https://docs.adobe.com/content/help/it-IT/data-workbench/using/install/c-data-workbench-client-install.html) | Configurazione tramite il browser. [Ulteriori informazioni](/help/export/analytics-data-feed/data-feed-overview.md) | Strumenti RESTful API. Effettuate l&#39;accesso con  credenziali di Adobe I/O. [Ulteriori informazioni](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Granularità dei dati** | Aggregata | Aggregata | Aggregata | Aggregata | Hit | Hit | Aggregata |
| **ID Experience Cloud (ECID) disponibile** | No | No | No | Sì | Sì | Sì | No |
| **Marca temporale disponibile** | No | No | No | No | Sì | Sì | No |
| **Livello di elaborazione** | Completamente elaborato | Elaborazione completa, con report in tempo reale [separato](/help/components/c-real-time-reporting/realtime.md) | Elaborazione completa, con report in tempo reale [separato](/help/components/c-real-time-reporting/realtime.md) | Completamente elaborato | Completamente elaborato | Completamente elaborato | Completamente elaborato |
| **Dati filtro bot amministratore inclusi** <br> [Ulteriori informazioni](/help/admin/admin/bot-removal/bot-removal.md) | No | Sì - Rapporto bot separato | Sì - Rapporto bot separato | No | No | No | No |
| **Viene visualizzato traffico basso (Superato il limite di lunghezza)** <br> [Ulteriori informazioni](/help/technotes/low-traffic.md) | Sì | Sì | Sì | No | No | No | Sì |
| **Limite righe visibili (prima dell’impaginazione)** | 400 | 200 | 50000 | Senza limiti | Senza limiti | Senza limiti | 50000 |
| **Suite di rapporti multiple** | [Sì](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sì, con limitazioni | Sì | No | Sì | No | Sì |
| **Numero di analisi approfondite** | Senza limiti | Fino a 2 | Fino a 2 | Senza limiti | Senza limiti | Senza limiti | Senza limiti, eseguite tra più query |
| **Segmentazione** <br> [Ulteriori informazioni](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sì | Sì | Sì | Sì, con [limitazioni](/help/components/segmentation/seg-reference/seg-compatibility.md) | Sì | No | Sì |
| **Metriche calcolate** <br> [Ulteriori informazioni](/help/components/c-calcmetrics/cm-overview.md) | Sì, con [ Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Sì | Sì | No | Sì | No | Sì, con [ Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canali marketing** <br> [Ulteriori informazioni](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sì | Sì | Sì | Sì | Sì | Sì - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sì |
| **Analisi per coorte** | [Sì](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | No | No | No | Sì | No | No |
| **Attribution** | Sì, con [ Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Limitato | Limitato | No | Sì | No | Sì, con [ Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Funzioni di analisi virtuale** <br> [Ulteriori informazioni](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | Sì | No | No | No | No | No | Sì |
| **Cura** <br> [Ulteriori informazioni](/help/analyze/analysis-workspace/curate-share/curate.md) | Sì - Progetto e VRS | No | No | No | No | No | Sì, solo VRS |
| **Condivisione dei progetti** <br> [Ulteriori informazioni](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sì, con i ruoli del progetto | Sì | Sì | No | Sì | No | No |
| **Spedizione pianificata** | Sì | Sì | Sì | Sì | No | Sì | No |
| **Destinazioni di consegna** | E-mail | E-mail | E-mail, FTP, SFTP, [pubblicazione in Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | E-mail, FTP. Rivolgiti all&#39;Assistenza clienti per ottenere ulteriore supporto per le destinazioni, inclusi SFTP, Azure Blob,  Amazon S3 | - | FTP, SFTP, Azure Blob,  Amazon S3 | - |
| **Elaborazione tempo report VRS** <br> [Ulteriori informazioni](/help/components/vrs/vrs-report-time-processing.md) | Sì | No | No | No | No | No | Sì |
