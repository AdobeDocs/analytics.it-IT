---
description: Requisiti di sistema e confronto tra Analysis Workspace, Report Builder; Data Warehouse e Data Workbench
title: Confronto dei prodotti Analytics e requisiti
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 100%

---

# Confronto dei prodotti Analytics e requisiti

Questa pagina contiene un confronto tra vari prodotti di Adobe Analytics: Analysis Workspace, Report Builder, Data Warehouse, Data Workbench, feed di dati e API 2.0 di Analytics.

Per informazioni sul prodotto Adobe Analytics da utilizzare, consulta [Quale strumento Adobe Analytics devo utilizzare?](/help/analyze/get-started/which-analytics-tool.md).

| Nome prodotto e collegamento all’Aiuto | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md) | [API 2.0 di Analytics](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **Metodo di accesso** | [Browser](/help/analyze/get-started/sys-reqs.md) | [MS Excel per Windows](/help/analyze/legacy-report-builder/setup/system-requirements.md) | Configurazione tramite il browser. [Ulteriori informazioni](/help/analyze/get-started/sys-reqs.md) | Configurazione tramite il browser. [Ulteriori informazioni](/help/export/analytics-data-feed/data-feed-overview.md) | Strumenti API RESTful. Accedi con le credenziali Adobe Developer. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Granularità dei dati** | Aggregata | Aggregata | Aggregata | Hit | Aggregata |
| **Experience Cloud ID (ECID) disponibile** | No | No | Sì | Sì | No |
| **Timestamp disponibile** | No | No | No | Sì | No |
| **Livello di elaborazione** | Elaborazione completa | Elaborazione completa con [rapporto in tempo reale](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) distinto | Elaborazione completa | Elaborazione completa | Elaborazione completa |
| **Dati da filtri bot per amministrazione inclusi** <br> [Ulteriori informazioni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | No | Sì - Rapporto bot distinto | No | No | No |
| **Visualizzazione traffico ridotto (valori univoci eccessivi)** <br> [Ulteriori informazioni](/help/technotes/low-traffic.md) | Sì | Sì | No | No | Sì |
| **Limite righe visibili (prima dell’impaginazione)** | 400 | 50.000 | Senza limiti | Senza limiti | 50.000 |
| **Più suite di rapporti** | [Sì](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sì | No | Sì | No | Sì |
| **Numero di raggruppamenti** | Senza limiti | Fino a 2 | Senza limiti | Senza limiti | Senza limiti, eseguito su più query |
| **Segmentazione** <br> [Ulteriori informazioni](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sì | Sì | Sì, con [limitazioni](/help/components/segmentation/seg-reference/seg-compatibility.md) | No | Sì |
| **Metriche calcolate** <br> [Ulteriori informazioni](/help/components/c-calcmetrics/cm-overview.md) | Sì, con [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Sì, con attribuzione | Sì | No | Sì, con [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canali marketing** <br> [Ulteriori informazioni](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sì | Sì | Sì | Sì - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sì |
| **Analisi per coorte** | [Sì](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Sì | No | No | No |
| **Attribuzione** | Sì, con [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Limitato | No | No | Sì, con [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | No |
| **Cura** <br> [Ulteriori informazioni](/help/analyze/analysis-workspace/curate-share/curate.md) | Sì: progetti e suite di rapporti virtuali | No | No | No | Sì: solo suite di rapporti virtuali |
| **Condivisione dei progetti** <br> [Ulteriori informazioni](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sì, con ruoli di progetto | Sì | No | No | No |
| **Consegna pianificata** | Sì | Sì | Sì | Sì | No |
| **Destinazioni di consegna** | E-mail | E-mail, FTP, SFTP, [pubblicazione in Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC e E-mail | Amazon S3, Azure RBAC, Azure SAS e Google Cloud Platform | - |
| **Elaborazione dei tempi di reporting della suite di rapporti virtuale** <br> [Ulteriori informazioni](/help/components/vrs/vrs-report-time-processing.md) | Sì | No | No | No | Sì |
