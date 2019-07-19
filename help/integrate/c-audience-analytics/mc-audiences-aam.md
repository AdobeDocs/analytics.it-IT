---
description: Adobe Audience Manager (AAM) è una potente piattaforma di gestione dei dati che consente di creare profili di pubblico unici da integrazioni di dati di prime, seconda e terze parti. Per gli inserzionisti, questi profili di pubblico consentono di definire i segmenti più importanti da usare tra i canali digitali.
seo-description: Adobe Audience Manager (AAM) è una potente piattaforma di gestione dei dati che consente di creare profili di pubblico unici da integrazioni di dati di prime, seconda e terze parti. Per gli inserzionisti, questi profili di pubblico consentono di definire i segmenti più importanti da usare tra i canali digitali.
seo-title: Panoramica di Audience Analytics
solution: Marketing Cloud
title: Panoramica di Audience Analytics
uuid: 86 ef 9391-dd 6 a -495 f-a 10 e-e 98 bc 069 dde 4
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Panoramica di Audience Analytics

Adobe Audience Manager (AAM) è una potente piattaforma di gestione dei dati che consente di creare profili di pubblico unici da integrazioni di dati di prime, seconda e terze parti. Per gli inserzionisti, questi profili di pubblico consentono di definire i segmenti più importanti da usare tra i canali digitali.

Con l'integrazione di Audience Analytics, puoi incorporare dati di audience AAM come informazioni demografiche (ad es. genere o livello di entrate), informazioni psicografiche (ad es. interessi e hobby), dati CRM e impressioni dati in qualsiasi flusso di lavoro Analytics.

## Vantaggi chiave {#section_94816D17283349E0BA28521BE55BB868}

L'integrazione di Audience Analytics offre i seguenti vantaggi principali:

* È la prima integrazione produttiva tra una piattaforma di gestione dati (DMP) e un motore di analisi sul mercato.
* I segmenti vengono condivisi da AAM ad Analytics in tempo reale, per informare l'individuazione, la segmentazione e l'ottimizzazione dell'audience.
* Tutti i segmenti AAM sono condivisi per impostazione predefinita, arricchendo i profili cliente in Analytics.
* Gli amministratori della soluzione possono abilitare l'integrazione tramite l'interfaccia utente, con modifiche minime al codice.
* Sono condivisi solo i segmenti che rispettano i controlli di esportazione dei dati di Audience Manager.

## Come funziona {#section_CECDF5A0FEC64264B206EFEF54F19EF2}

![](assets/mc-aud-dataflow.png)

1. Ogni volta che un visitatore arriva alle tue proprietà digitali, gli hit vengono raccolti e inviati ad Analytics.
1. With [server-side forwarding](/help/admin/admin/c-server-side-forwarding/ssf.md), each hit that Analytics receives is automatically sent to AAM in real time.
1. Tramite l'integrazione di Audience Analytics, per ogni hit l'iscrizione al pubblico di un visitatore viene individuata in AAM e un elenco degli ID del segmento viene restituito in Analytics per l'elaborazione in tempo reale.

Poiché i segmenti AAM vengono inseriti sullo stesso hit, puoi assicurarti che qualsiasi dato sia disponibile in AAM su un visitatore non verrà perso e aggiornato per quell'hit. Ciò è superiore a un plug-in AppMeasurement perché un plug-in può rendere tali segmenti disponibili solo sull'hit successiva (e non sulla hit corrente).

Inoltre, classifichiamo automaticamente gli ID del segmento AAM ai loro nomi descrittivi, in modo che non sia necessario osservare ID alfanumerici nei report di Analytics.

## Prerequisiti {#section_A345DC31F7D44EAE9DC1AB53E824C0CC}

Assicurati che vi siano i seguenti prerequisiti:

* Sei cliente di Audience Manager e Adobe Analytics.
* Sei un amministratore di Audience Manager.
* State utilizzando Identity Service v 1.5 o versione successiva.
* AAM and Adobe Analytics report suites are [mapped to the same Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).
* You use [server-side forwarding](/help/admin/admin/c-server-side-forwarding/ssf.md) and have implemented the [Audience Management module](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) (no DIL code) - AppMeasurement 1.5 or later.

These prerequisites are described in the [Audience Analytics Workflow](../../integrate/c-audience-analytics/c-workflow/audiences-workflow.md#concept_A5F067D14C794B759A1D92526DE27F83).
