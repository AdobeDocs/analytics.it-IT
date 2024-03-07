---
description: Spiega i preparativi necessari per preparare la migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics.
title: Preparare la migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics
feature: Admin Tools
exl-id: a9ff98dc-6568-428d-a8a8-faca5bc76a29
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 5%

---

# Preparare la migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics

Prima che chiunque nell’organizzazione inizi la migrazione dei progetti come descritto in [Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md), completare le sezioni seguenti.

## Prerequisiti

Prima che i progetti e i relativi componenti siano pronti per la migrazione, devi seguire i passaggi descritti in [Evoluzione da Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=it) nella Guida di Adobe Customer Journey Analytics. Questi passaggi includono:

1. Per acquisire i dati in Adobe Experience Platform per visualizzare i dati della suite di rapporti di Adobe Analytics nel Customer Journey Analytics, utilizza uno dei seguenti metodi:

   >[!NOTE]
   >
   >  Quando utilizzi Web SDK per acquisire i dati, tutti i campi dello schema devono essere mappati manualmente. (Per ulteriori informazioni sul processo di mappatura, vedi [Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md))


   * Per utilizzare il connettore di origine di Adobe Analytics, è necessario:

      1. [Configurare le suite di rapporti per l’acquisizione in Adobe Experience Platform e Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Inserire e utilizzare i dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=it)

   * Per utilizzare Web SDK, è necessario:

      1. [Configurare le suite di rapporti per l’acquisizione in Adobe Experience Platform e Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [Inserire dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html)

1. Creare un [connessione](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html) e [visualizzazione dati](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=it) con i dati acquisiti.

1. Assicurati che gli utenti nel Customer Journey Analytics siano assegnati alle visualizzazioni dati in cui vengono mappati i dati.

   Per ulteriori informazioni, consulta [Autorizzazioni di Customer Journey Analytics nell’Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html#customer-journey-analytics-permissions-in-admin-console) in [Controllo dell’accesso al Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

   La scheda Autorizzazioni fa parte di ciascun profilo di prodotto in Admin Console. Puoi aggiungere utenti a profili di prodotto specifici. Puoi quindi assegnare i diritti a visualizzazioni dati specifiche e specificare quali autorizzazioni hanno gli utenti in un profilo di prodotto.

1. Decidi come mappare i componenti come organizzazione.

   Per ulteriori informazioni, consulta la sezione seguente, [Decidere come organizzazione la mappatura dei componenti](#decide-as-an-organization-how-you-will-map-components).

## Informazioni incluse in una migrazione

Le tabelle seguenti descrivono gli elementi di un progetto e di un componente inclusi in una migrazione:

### Elementi componenti migrati

I Dimension e le metriche vengono migrati come parte del processo di mappatura descritto in [Migrare progetti Adobe Analytics al Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics).

Segmenti, intervalli di date e metriche calcolate che non esistono già nel Customer Journey Analytics vengono ricreati in base alle dimensioni e alle metriche mappate.

|  | Migrato |
|---------|---------|
| **[Proprietario](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | Dimension e metriche: No<p>Segmenti e intervalli di date: ![segno di spunta](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Condivisione](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimension e metriche: No<p>Segmenti e intervalli di date: no</p> |
| **[Descrizione](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimension e metriche: No<p>Segmenti e intervalli di date: ![segno di spunta](assets/Smock_Checkmark_18_N.svg)</p> |
| **[Tag](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimension e metriche: No<p>Segmenti e intervalli di date: no</p> |
| **[Attribuzione (sulle dimensioni)](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimension e metriche: No<p>Segmenti e intervalli di date: no</p> |

{style="table-layout:auto"}

### Elementi del progetto migrati

|  | Migrato |
|---------|----------|
| **[Intervalli di date](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![segno di spunta](assets/Smock_Checkmark_18_N.svg) |
| **[Segmenti](/help/components/segmentation/seg-overview.md)** | ![segno di spunta](assets/Smock_Checkmark_18_N.svg) |
| **[Segmenti rapidi](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![segno di spunta](assets/Smock_Checkmark_18_N.svg) |
| **[Dimensioni](/help/components/dimensions/overview.md)** | ![segno di spunta](assets/Smock_Checkmark_18_N.svg) Mappato automaticamente o manualmente |
| **[Metriche](/help/components/metrics/overview.md)** | ![segno di spunta](assets/Smock_Checkmark_18_N.svg) Mappato automaticamente o manualmente |
| **[Pannelli](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![segno di spunta](assets/Smock_Checkmark_18_N.svg) |
| **[Visualizzazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![segno di spunta](assets/Smock_Checkmark_18_N.svg) |
| **[Proprietario](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![segno di spunta](assets/Smock_Checkmark_18_N.svg) Definito dall’utente che esegue la migrazione |
| **[Cura](/help/analyze/analysis-workspace/curate-share/curate.md)** | No |
| **[Condivisione](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | No |
| **[Annotazioni](/help/analyze/analysis-workspace/components/annotations/overview.md)** | No |
| **[Struttura delle cartelle](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | No |
| **[Descrizione](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![segno di spunta](assets/Smock_Checkmark_18_N.svg) |
| **[Tag](/help/analyze/landing.md)** | No |
| **[Preferiti](/help/analyze/landing.md)** | No |
| **[Schedules](/help/components/scheduled-projects-manager.md)** | No |
| **[Rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)** | ![segno di spunta](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## Comprendere gli elementi non supportati che causano errori

Le visualizzazioni e i pannelli seguenti non sono supportati in Customer Journey Analytics. Quando questi elementi vengono inclusi in un progetto prima della migrazione, possono causare errori o errori dopo la migrazione del progetto.

Rimuovi questi elementi dal progetto Adobe Analytics prima di eseguire la migrazione del progetto al Customer Journey Analytics. Se una migrazione non riesce, rimuovi questi elementi prima di riprovare.

### Visualizzazioni non supportate

* [Mappa](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

### Pannelli non supportati

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [Confronto dei segmenti](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [Pubblico medio per minuto del file multimediale](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [Elemento successivo o precedente](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [Riepilogo pagina](/help/analyze/analysis-workspace/c-panels/page-summary.md)

* [Analisi contributi](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)

## Decidere come organizzazione la mappatura dei componenti

>[!IMPORTANT]
>
>Il processo di migrazione identifica i componenti nel progetto Adobe Analytics che non possono essere mappati automaticamente ai componenti nel Customer Journey Analytics e consente di mapparli manualmente.
>
>**Le mappature effettuate su un progetto si applicano a tutti i progetti futuri nell’intera organizzazione IMS, indipendentemente dall’utente che esegue la migrazione. Queste mappature possono essere modificate o annullate solo contattando l’Assistenza clienti.**
>
>Per questo motivo, è importante che la tua organizzazione decida come verranno mappate dimensioni e metriche prima della migrazione di qualsiasi progetto. In questo modo i singoli amministratori non possono prendere decisioni all’interno di un silo se si considera un solo progetto.
>
>Di seguito è riportato un elenco di dimensioni e metriche da mappare manualmente, se presenti nel progetto. È consigliabile rivedere questo elenco prima della migrazione. Se nel progetto è presente uno di questi componenti, decidi ora a quali componenti di Customer Journey Analytics mapparli.


### Dimension che devono essere mappati manualmente

* averagepagetime
* pagetimeseconds
* singlepagevisits
* visitnumber
* timeprior
* tempo trascorso
* categoria
* connectiontype
* fedeltà del cliente
* customlink
* download
* exitlink
* profondità dell&#39;hit
* tipo di battuta
* pathlength
* daysbeforefirstpurchase
* dayssincelastpurchase
* dayssincelastvisit
* identationstate
* optoutreason
* persistentcookie
* frequenza di ritorno
* searchenginenatural
* searchenginenaturalkeyword
* portalomobili
* monitorresolution
* base di sondaggio
* mcaudiences
* tntbase
* targetraw


### Metriche che devono essere mappate manualmente

* timespentvisit
* timespentvisitor
* ricaricamenti
* mancati recapiti
* rimbalzo
* pageevents
* pageviewspervisit
* orderspervisit
* averagepagedepth
* averagetimespentonsite
* exitlinkinstances
* customlinkinstances
* downloadlinkinstances
* darkvisitors
* singlepagevisits
* singlevaluevisits
* visitorhomepage
* visitorsmcvisid
* pagesnotfound
* nuovi impegni
* time_granularity
* concurrent_viewers_visitors
* concurrent_viewers_occurrrences
* dispositivi
* persone stimate
* tempo_di_riproduzione trascorso_secondi
* playback_time_espor_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* targetconversion
* targetimpression
