---
description: Adobe Audience Manager (Adobe Audience Manager) è una potente piattaforma di gestione dei dati che consente di creare profili di pubblico univoci da integrazioni di dati di prime parti, seconde parti/partner e terze parti. Per gli inserzionisti, questi profili di pubblico aiutano a definire i segmenti più importanti da utilizzare su qualsiasi canale digitale.
solution: Experience Cloud
title: Panoramica di Audience Analytics
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
TQID: https://experienceleague.adobe.com/WPB1fEJx1MaWpUNRCZ48ghAVyKyc5IwoGOdgQQ-tPhI
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: df401a2a-327d-468c-a5e4-b7b7ccd071a0id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 522
ht-degree: 4%

---

# Panoramica di Audience Analytics

Adobe Audience Manager (Adobe Audience Manager) è una potente piattaforma di gestione dei dati che consente di creare profili di pubblico univoci da integrazioni di dati di prime parti, seconde parti/partner e terze parti. Per gli inserzionisti, questi profili di pubblico aiutano a definire i segmenti più importanti da utilizzare su qualsiasi canale digitale.

Con l’integrazione di Audience Analytics, puoi incorporare in qualsiasi flusso di lavoro di Adobe Audience Manager dati sul pubblico, come informazioni demografiche (ad esempio, genere o fascia di reddito), informazioni psicografiche (ad esempio, interessi e hobby), dati CRM e dati di impressioni di annunci.


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/audience-manager/audience-analytics-integrate-aam-segments-into-analytics){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


## Vantaggi chiave {#benefits}

L’integrazione di Audience Analytics offre i seguenti vantaggi chiave:

* È la prima integrazione prodotta tra una piattaforma di gestione dati (DMP) e un motore di analisi sul mercato.
* I segmenti vengono condivisi da Adobe Audience Manager ad Analytics in tempo reale, per informare l’individuazione, la segmentazione e l’ottimizzazione del pubblico.
* Tutti i segmenti di Adobe Audience Manager sono condivisi per impostazione predefinita, arricchendo completamente i profili dei clienti in Analytics.
* Gli amministratori della soluzione possono abilitare l’integrazione tramite l’interfaccia utente, con la minima richiesta di modifiche al codice.
* Vengono condivisi solo i segmenti che aderiscono ai controlli di esportazione dei dati di Audience Manager.

## Come funziona Audience Analytics {#works}

![](assets/mc-aud-dataflow.png)

1. Ogni volta che un visitatore accede alle tue proprietà digitali, gli hit vengono raccolti e inviati ad Analytics.
1. Con [inoltro lato server](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md), ogni hit ricevuto da Analytics viene inviato automaticamente a Adobe Audience Manager in tempo reale.
1. Attraverso l’integrazione di Audience Analytics, per ogni hit, l’iscrizione del pubblico di un visitatore viene cercata in Adobe Audience Manager e un elenco di ID segmento viene restituito ad Analytics per l’elaborazione in tempo reale.

Poiché i segmenti di Adobe Audience Manager vengono inseriti con lo stesso hit, puoi essere sicuro che tutti i dati disponibili in Adobe Audience Manager relativi a un visitatore non verranno persi e saranno aggiornati per tale hit. Si tratta di un valore superiore a quello di un plug-in di AppMeasurement, poiché un plug-in può rendere questi segmenti disponibili solo all’hit successivo (anziché all’hit corrente).

Inoltre, classifichiamo automaticamente gli ID del segmento Adobe Audience Manager in base al loro nome descrittivo, in modo da non dover esaminare gli ID alfanumerici nei rapporti di Analytics.

## Prerequisiti {#prerequisites}

Verifica che siano presenti i seguenti prerequisiti:

* Sei un cliente sia di Audience Manager che di Adobe Analytics.
* Sei un amministratore di Audience Manager.
* Stai utilizzando il servizio Identity v1.5 o versione successiva.
* Le suite di rapporti di Adobe Audience Manager e Adobe Analytics sono mappate sulla stessa organizzazione Experience Cloud.
* Hai utilizzato [inoltro lato server](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md) e hai implementato il [modulo Gestione dell&#39;audience](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=it) (nessun codice DIL) - AppMeasurement 1.5 o versione successiva.

Questi prerequisiti sono descritti nel [flusso di lavoro Audience Analytics](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md).
