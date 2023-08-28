---
description: Requisiti di sistema e confronto tra Analysis Workspace, Reports & Analytics, Report Builder, Data Warehouse e Data Workbench
title: Confronto dei prodotti Analytics e requisiti
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 71ebabf7efca70c0cbd2489dc538f7f10cae16cb
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 97%

---

# Confronto dei prodotti Analytics e requisiti

Questa pagina contiene un confronto tra vari prodotti Adobe Analytics: Analysis Workspace, Reports &amp; Analytics, Report Builder, Data Warehouse, Data Workbench, feed di dati e API 2.0 di Analytics.

Per informazioni sul prodotto Adobe Analytics da utilizzare, consulta [Quale strumento Adobe Analytics devo utilizzare?](/help/analyze/get-started/which-analytics-tool.md).

| Nome prodotto e collegamento all’Aiuto | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html?lang=it) | [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md) | [API 2.0 di Analytics](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Metodo di accesso** | [Browser](/help/analyze/get-started/sys-reqs.md) | [Browser](/help/analyze/get-started/sys-reqs.md) | [MS Excel per Windows](/help/analyze/report-builder/setup/system-requirements.md) | Configurazione tramite il browser. [Ulteriori informazioni](/help/analyze/get-started/sys-reqs.md) | [Windows a 64 bit](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html?lang=it) | Configurazione tramite il browser. [Ulteriori informazioni](/help/export/analytics-data-feed/data-feed-overview.md) | Strumenti API RESTful. Accedi con le credenziali Adobe Developer. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Granularità dei dati** | Aggregata | Aggregata | Aggregata | Aggregata | Hit | Hit | Aggregata |
| **Experience Cloud ID (ECID) disponibile** | No | No | No | Sì | Sì | Sì | No |
| **Timestamp disponibile** | No | No | No | No | Sì | Sì | No |
| **Livello di elaborazione** | Elaborazione completa | Elaborazione completa con [rapporto in tempo reale](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) distinto | Elaborazione completa con [rapporto in tempo reale](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) distinto | Elaborazione completa | Elaborazione completa | Elaborazione completa | Elaborazione completa |
| **Dati da filtri bot per amministrazione inclusi** <br> [Ulteriori informazioni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | No | Sì - Rapporto bot distinto | Sì - Rapporto bot distinto | No | No | No | No |
| **Visualizzazione traffico ridotto (valori univoci eccessivi)** <br> [Ulteriori informazioni](/help/technotes/low-traffic.md) | Sì | Sì | Sì | No | No | No | Sì |
| **Limite righe visibili (prima dell’impaginazione)** | 400 | 200 | 50.000 | Senza limiti | Senza limiti | Senza limiti | 50.000 |
| **Più suite di rapporti** | [Sì](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sì, con limitazioni | Sì | No | Sì | No | Sì |
| **Numero di raggruppamenti** | Senza limiti | Fino a 2 | Fino a 2 | Senza limiti | Senza limiti | Senza limiti | Senza limiti, eseguito su più query |
| **Segmentazione** <br> [Ulteriori informazioni](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sì | Sì | Sì | Sì, con [limitazioni](/help/components/segmentation/seg-reference/seg-compatibility.md) | Sì | No | Sì |
| **Metriche calcolate** <br> [Ulteriori informazioni](/help/components/c-calcmetrics/cm-overview.md) | Sì, con [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Sì | Sì | No | Sì | No | Sì, con [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canali marketing** <br> [Ulteriori informazioni](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sì | Sì | Sì | Sì | Sì | Sì - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sì |
| **Analisi per coorte** | [Sì](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | No | No | No | Sì | No | No |
| **Attribuzione** | Sì, con [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Limitato | Limitato | No | Sì | No | Sì, con [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Funzioni di Virtual Analyst** <br> [Ulteriori informazioni](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | Sì | No | No | No | No | No | Sì |
| **Cura** <br> [Ulteriori informazioni](/help/analyze/analysis-workspace/curate-share/curate.md) | Sì - Progetti e suite di rapporti virtuali | No | No | No | No | No | Sì - Solo suite di rapporti virtuali |
| **Condivisione dei progetti** <br> [Ulteriori informazioni](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sì, con ruoli di progetto | Sì | Sì | No | Sì | No | No |
| **Consegna pianificata** | Sì | Sì | Sì | Sì | No | Sì | No |
| **Destinazioni di consegna** | E-mail | E-mail | E-mail, FTP, SFTP, [pubblicazione in Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | E-mail, FTP. Per il supporto di ulteriori destinazioni, incluse SFTP, Azure Blob e Amazon S3, contatta l’Assistenza clienti | - | Piattaforma Amazon S3, Azure RBAC, Azure SAS e Google Cloud | - |
| **Elaborazione al momento del rapporto (suite di rapporti virtuali)** <br> [Ulteriori informazioni](/help/components/vrs/vrs-report-time-processing.md) | Sì | No | No | No | No | No | Sì |
