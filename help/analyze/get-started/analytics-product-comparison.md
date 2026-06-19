---
description: Requisiti di sistema e confronto tra Analysis Workspace, Report Builder; Data Warehouse e Data Workbench
title: Confronto dei prodotti Analytics e requisiti
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
TQID: https://experienceleague.adobe.com/VQgK6DUSlz-UA3zk-Q18-QOAI5M6xfK7KqBYwW56j6w
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: a421fb65-2c82-457a-921c-28c46b697a39id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8id: af53ada8-1b7d-4929-ac91-ac971dd20ec7id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: dcae653e-62c6-4cc8-84e6-ee110b848296id: e9cb007b-c8b7-4975-bc81-11a788c535faid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 67%

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
| **Livello di elaborazione** | Elaborazione completa | Elaborazione completa con [rapporto in tempo reale](/help/admin/tools/manage-rs/edit-settings/realtime/realtime.md) distinto | Elaborazione completa | Elaborazione completa | Elaborazione completa |
| **Dati da filtri bot per amministrazione inclusi** <br> [Ulteriori informazioni](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) | No | Sì - Rapporto bot distinto | No | No | No |
| **Visualizzazione traffico ridotto (valori univoci eccessivi)** <br> [Ulteriori informazioni](/help/technotes/low-traffic.md) | Sì | Sì | No | No | Sì |
| **Limite righe visibili (prima dell’impaginazione)** | 400 | 50.000 | Senza limiti | Senza limiti | 50.000 |
| **Più suite di rapporti** | [Sì](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sì | No | Sì | No |
| **Numero di raggruppamenti** | Senza limiti | Fino a 2 | Senza limiti | Senza limiti | Senza limiti, eseguito su più query |
| **Segmentazione** <br> [Ulteriori informazioni](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sì | Sì | Sì, con [limitazioni](/help/export/data-warehouse/segment-compatibility.md) | No | Sì |
| **Metriche calcolate** <br> [Ulteriori informazioni](/help/components/calculated-metrics/cm-overview.md) | Sì, con [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Sì, con attribuzione | Sì | No | Sì, con [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canali marketing** <br> [Ulteriori informazioni](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sì | Sì | Sì | Sì - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sì |
| **Analisi per coorte** | [Sì](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Sì | No | No | No |
| **Attribuzione** | Sì, con [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Limitato | No | No | Sì, con [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Cura** <br> [Ulteriori informazioni](/help/analyze/analysis-workspace/curate-share/curate.md) | Sì: progetti e suite di rapporti virtuali | No | No | No | Sì: solo suite di rapporti virtuali |
| **Condivisione dei progetti** <br> [Ulteriori informazioni](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sì, con ruoli di progetto | Sì | No | No | No |
| **Consegna pianificata** | Sì | Sì | Sì | Sì | No |
| **Destinazioni di consegna** | E-mail | E-mail, FTP, SFTP, [pubblicazione in Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC e E-mail | Amazon S3, Azure RBAC, Azure SAS e Google Cloud Platform | - |
| **Elaborazione dei tempi di reporting della suite di rapporti virtuale** <br> [Ulteriori informazioni](/help/components/vrs/vrs-report-time-processing.md) | Sì | No | No | No | Sì |
| **Rapporti geografici e tecnologici** | Sì <p>Utilizza valori medi anziché campi di post. La logica di prima visita si basa su `post_cust_hit_time_gmt` invece di `visit_page_num=1`. I risultati possono differire da altri strumenti se l’IP cambia a metà visita, gli hit arrivano fuori ordine o le visite attraversano i limiti mensili.</p> | Sì <p>Utilizza valori medi anziché campi di post. La logica di prima visita si basa su `post_cust_hit_time_gmt` invece di `visit_page_num=1`. I risultati possono differire da altri strumenti se l’IP cambia a metà visita, gli hit arrivano fuori ordine o le visite attraversano i limiti mensili.</p> | Sì <p>Utilizza i valori post e `visit_page_num=1` per determinare il primo hit della visita. Applica il valore del primo hit a tutti gli hit nella visita per queste dimensioni.</p> | Sì <p>Utilizza i valori post e `visit_page_num=1` per determinare il primo hit della visita. Applica il valore del primo hit a tutti gli hit nella visita per queste dimensioni.</p> | Sì <p>Utilizza valori medi anziché campi di post. La logica di prima visita si basa su `post_cust_hit_time_gmt` invece di `visit_page_num=1`. I risultati possono differire da altri strumenti se l’IP cambia a metà visita, gli hit arrivano fuori ordine o le visite attraversano i limiti mensili.</p> |
