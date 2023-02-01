---
title: Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile
description: Utilizzare l’estensione Mobile SDK in Adobe Experience Platform Data Collection per inviare dati ad Adobe Analytics.
source-git-commit: 5adc3fe1eab0a358573ebdc12e51c6753e85b14c
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 20%

---

# Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile

L’Adobe Experience Platform Mobile SDK aiuta ad alimentare soluzioni e servizi di Adobe Experience Cloud nelle app mobile. È disponibile per Android™, iOS e vari framework di sviluppo multipiattaforma. La configurazione viene gestita tramite Raccolta dati di Adobe Experience Platform.
>[!IMPORTANT]
>
>Un’estensione Adobe Analytics è disponibile anche in Raccolta dati di Adobe Experience Platform. Se installi questa estensione, non sfrutti XDM o la rete Edge.

## SDK per Adobe Experience Platform

Panoramica di alto livello delle attività di implementazione:

![Adobe Analytics tramite il flusso di lavoro dell’estensione Analytics](../../assets/mobilesdk-annotated.png)

| | Attività | Ulteriori informazioni | |-| —|—| | 1 | Assicurati di avere **definizione di una suite di rapporti**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configurare schemi e set di dati**. Per standardizzare la raccolta di dati da utilizzare nelle applicazioni che sfruttano Adobe Experience Platform, Adobe ha creato lo standard aperto e documentato pubblicamente, Experience Data Model (XDM). | [Configurare schemi e set di dati](https://developer.adobe.com/client-sdks/documentation/getting-started/set-up-schemas-and-datasets/) | | 3 | **Configurare un datastream**. Un datastream rappresenta la configurazione lato server durante l&#39;implementazione dell&#39;SDK per web Adobe Experience Platform. | [Configurare un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 4 | **Aggiungere un servizio Adobe Analytics** al tuo datastream. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics. | [Aggiungere il servizio Adobe Analytics a un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 5 | **Creare una proprietà mobile**. Una proprietà è un contenitore che si riempie con estensioni, regole, elementi dati e librerie. | [Impostare una proprietà mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 6 | **Installare l’estensione Adobe Experience Platform Edge Network** nella proprietà tag mobile e configura il datastream nell’estensione . | [Adobe Experience Platform Edge Network](https://developer.adobe.com/client-sdks/documentation/edge-network/) | | 7 | **Usa il codice nella tua app** per registrare le estensioni necessarie e caricare la configurazione del tag. | [Imposta la configurazione](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 8 | **Implementazione e funzionalità di test** utilizzando una combinazione di elementi dati, regole, estensioni aggiuntive e chiamate API SDK nella tua app. Inspect, convalida ed esegui il debug della raccolta dati e delle esperienze per la tua app mobile. | [Utilizzare l&#39;applicazione di esempio](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 9 | **Estendere e convalidare l’implementazione dell’app mobile** prima di spingerlo verso la produzione. | |


## Estensione Adobe Analytics.

Panoramica di alto livello delle attività di implementazione:

![Adobe Analytics tramite il flusso di lavoro dell’estensione Analytics](../../assets/mobilesdk-analytics-annotated.png)

| | Attività | Ulteriori informazioni | |-| —|—| | 1 | Assicurati di avere **definizione di una suite di rapporti**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Creare una proprietà mobile**. Una proprietà è un contenitore che si riempie con estensioni, regole, elementi dati e librerie. | [Impostare una proprietà mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/) | | 3 | **Installare l’estensione Adobe Analytics** nella proprietà tag mobile e configura l’estensione in modo che punti alla suite di rapporti. | [Estensione Adobe Analytics per la proprietà mobile](https://developer.adobe.com/client-sdks/documentation/adobe-analytics/) | | 4 | **Usa il codice nella tua app** per registrare le estensioni necessarie e caricare la configurazione del tag. | [Imposta la configurazione](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration) | | 5 | **Implementazione e funzionalità di test** utilizzando una combinazione di elementi dati, regole, estensioni aggiuntive e chiamate API SDK nella tua app. Inspect, convalida ed esegui il debug della raccolta dati e delle esperienze per la tua app mobile. | [Utilizzare l&#39;applicazione di esempio](https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application) | | 6 | **Estendere e convalidare l’implementazione dell’app mobile** prima di spingerlo verso la produzione. | |

## Risorse aggiuntive

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it#)

- [Documentazione di Mobile SDK](https://developer.adobe.com/client-sdks/documentation/)



