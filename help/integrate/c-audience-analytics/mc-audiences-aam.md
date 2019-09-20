---
description: Adobe Audience Manager (AAM) è una potente piattaforma di gestione dei dati che consente di creare profili di pubblico unici da integrazioni di dati di prime, seconda e terze parti. Per gli inserzionisti, questi profili di pubblico consentono di definire i segmenti più importanti da usare tra i canali digitali.
seo-description: Adobe Audience Manager (AAM) è una potente piattaforma di gestione dei dati che consente di creare profili di pubblico unici da integrazioni di dati di prime, seconda e terze parti. Per gli inserzionisti, questi profili di pubblico consentono di definire i segmenti più importanti da usare tra i canali digitali.
seo-title: Panoramica di Audience Analytics
solution: Experience Cloud
title: Panoramica di Audience Analytics
uuid: 86ef9391-dd6a-495f-a10e-e98bc069dde4
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Panoramica di Audience Analytics

Adobe Audience Manager (AAM) è una potente piattaforma di gestione dei dati che consente di creare profili di pubblico unici da integrazioni di dati di prime, seconda e terze parti. Per gli inserzionisti, questi profili di pubblico consentono di definire i segmenti più importanti da usare tra i canali digitali.

Con l'integrazione di Audience Analytics, puoi incorporare dati di audience AAM come informazioni demografiche (ad esempio, genere o livello di reddito), informazioni psicografiche (ad esempio, interessi e hobby), dati CRM e dati di impressioni pubblicitarie in qualsiasi flusso di lavoro Analytics.

## Vantaggi chiave {#section_94816D17283349E0BA28521BE55BB868}

L'integrazione di Audience Analytics offre i seguenti vantaggi principali:

* Si tratta della prima integrazione prodotta tra una piattaforma di gestione dati (DMP) e un motore di analisi sul mercato.
* I segmenti vengono condivisi da AAM ad Analytics in tempo reale, per informare l'audience su scoperta, segmentazione e ottimizzazione.
* Tutti i segmenti AAM sono condivisi per impostazione predefinita, arricchendo completamente i profili cliente in Analytics.
* Gli amministratori delle soluzioni possono consentire l'integrazione tramite l'interfaccia utente, con modifiche minime del codice richieste.
* Vengono condivisi solo i segmenti che aderiscono ai controlli di esportazione dei dati di Audience Manager.

## Come funziona {#section_CECDF5A0FEC64264B206EFEF54F19EF2}

![](assets/mc-aud-dataflow.png)

1. Ogni volta che un visitatore accede alle proprietà digitali, gli hit vengono raccolti e inviati ad Analytics.
1. Con l'inoltro [lato](/help/admin/admin/c-server-side-forwarding/ssf.md)server, ogni hit ricevuto da Analytics viene inviato automaticamente ad AAM in tempo reale.
1. Grazie all'integrazione di Audience Analytics, per ogni hit l'iscrizione dell'audience di un visitatore viene cercata in AAM e un elenco degli ID del segmento viene restituito ad Analytics per l'elaborazione in tempo reale.

Poiché i segmenti AAM vengono inseriti in base alla stessa hit, puoi essere sicuro che qualsiasi dato sia disponibile in AAM su un visitatore non verrà perso e sarà aggiornato per quell’hit. Ciò è superiore a un plug-in AppMeasurement perché un plug-in può rendere tali segmenti disponibili solo sull'hit successiva (e non sulla hit corrente).

Inoltre, classifichiamo automaticamente gli ID del segmento AAM in base ai loro nomi descrittivi, in modo da non dover guardare gli ID alfanumerici nei report di Analytics.

## Prerequisiti {#section_A345DC31F7D44EAE9DC1AB53E824C0CC}

Assicurati che vi siano i seguenti prerequisiti:

* Sei cliente di Audience Manager e Adobe Analytics.
* Sei un amministratore di Audience Manager.
* State utilizzando il servizio identità v1.5 o successivo.
* Le suite di rapporti AAM e Adobe Analytics sono [mappate sulla stessa organizzazione](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)Experience Cloud.
* Puoi utilizzare l’inoltro [lato](/help/admin/admin/c-server-side-forwarding/ssf.md) server e hai implementato il modulo [Gestione](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) dell’audience (nessun codice DIL) - AppMeasurement 1.5 o successivo.

Questi prerequisiti sono descritti nel flusso di lavoro di [Audience Analytics](../../integrate/c-audience-analytics/c-workflow/audiences-workflow.md#concept_A5F067D14C794B759A1D92526DE27F83).
