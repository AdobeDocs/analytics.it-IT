---
title: Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK
description: Utilizza l’estensione Web SDK in Adobe Experience Platform Data Collection per inviare dati ad Adobe Analytics.
source-git-commit: 472faef9c6ef99d4e58f2f5a9a71ca8d058f0ee2
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 17%

---

# Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK

Puoi utilizzare [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) per inviare dati ad Adobe Analytics. Questo metodo di implementazione funziona traducendo il [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) in un formato utilizzato da Analytics.

Puoi inviare dati a Experience Edge direttamente utilizzando l’SDK per web o tramite l’estensione SDK per web in Tag.

## SDK per web

Panoramica di alto livello delle attività di implementazione:

![Implementazione del flusso di lavoro Adobe Analytics tramite SDK per web](../../assets/websdk-annotated.png)

| | Attività | Ulteriori informazioni | |-| —|—| | 1 | Assicurati di avere **definizione di una suite di rapporti**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configurazione di schemi e set di dati**. Per standardizzare la raccolta di dati da utilizzare nelle applicazioni che sfruttano Adobe Experience Platform, Adobe ha creato lo standard aperto e documentato pubblicamente, Experience Data Model (XDM). | [Panoramica dell’interfaccia utente degli schemi](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=it) e [Panoramica dell’interfaccia utente dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it) | | 3 | **Creare un livello di dati** per gestire il tracciamento dei dati sul sito web. | [Creare un livello di dati](../../prepare/data-layer.md) | | 4 | **Installare la versione standalone predefinita**. Puoi fare riferimento alla libreria (`alloy.js`) sulla rete CDN direttamente sulla tua pagina o scaricala e ospitala sulla tua infrastruttura. In alternativa, è possibile utilizzare il pacchetto NPM. | [Installazione della versione autonoma predefinita](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version) e [Utilizzo del pacchetto NPM](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package)| | 5 | **Configurare un datastream**. Un datastream rappresenta la configurazione lato server durante l&#39;implementazione dell&#39;SDK per web Adobe Experience Platform. | [Configurare un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 6 | **Aggiungere un servizio Adobe Analytics** al tuo datastream. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics. | [Aggiungere il servizio Adobe Analytics a un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 7 | **Configurare l’SDK per web**. Assicurati che la libreria installata nel passaggio 4 sia configurata correttamente con l&#39;ID del datastream (precedentemente noto come id di configurazione perimetrale (`edgeConfigId`), id organizzazione (`orgId`) e altre opzioni disponibili. | [Configurare l’SDK per web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) | | 8 | **Esegui comandi** e/o **eventi di tracciamento**. Una volta implementato il codice di base sulla pagina web, puoi iniziare a eseguire comandi ed eventi di tracciamento con l&#39;SDK. | [Esegui comandi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en) e [Tracciare gli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en) | | 9 | **Estendi e convalida l’implementazione** prima di spingerlo verso la produzione. | |



## Estensione SDK per web

Panoramica di alto livello delle attività di implementazione:

![Implementare Adobe Analytics tramite il flusso di lavoro dell&#39;estensione dell&#39;SDK per web](../../assets/websdk-extension-annotated.png)

| | Attività | Ulteriori informazioni | |-| —|—| | 1 | Assicurati di avere **definizione di una suite di rapporti**. | [Report Suite Manager](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Configurazione di schemi e set di dati**. Per standardizzare la raccolta di dati da utilizzare nelle applicazioni che sfruttano Adobe Experience Platform, Adobe ha creato lo standard aperto e documentato pubblicamente, Experience Data Model (XDM). | [Panoramica dell’interfaccia utente degli schemi](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=it) e [Panoramica dell’interfaccia utente dei set di dati](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it) | | 3 | **Creare un livello di dati** per gestire il tracciamento dei dati sul sito web. | [Creare un livello di dati](../../prepare/data-layer.md) | | 4 | **Configurare un datastream**. Un datastream rappresenta la configurazione lato server durante l&#39;implementazione dell&#39;SDK per web Adobe Experience Platform. | [Configurare un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 5 | **Aggiungere un servizio Adobe Analytics** al tuo datastream. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics. | [Aggiungere il servizio Adobe Analytics a un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 6 | **Creare una proprietà tag**. Le proprietà sono contenitori sovrapposti utilizzati per fare riferimento ai dati di gestione dei tag.| [Creare o configurare una proprietà tag per il Web](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web) | | 7 | **Installare e configurare l’estensione SDK per web** nella proprietà tag. Configura l&#39;estensione Web SDK per inviare dati al datastream configurato nel passaggio 4. | [Panoramica dell&#39;estensione Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en) | | 8 | **Itera, convalida e pubblica** alla produzione. Aggiungi la proprietà tag al sito Web. Quindi utilizza elementi dati, regole e così via per personalizzare la tua implementazione. | [Panoramica sulla pubblicazione](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en) |



## Risorse aggiuntive

I tag possono essere altamente personalizzati. Ulteriori informazioni su come ottenere il massimo da Adobe Analytics includendo i dati giusti nella tua implementazione.

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it#): Scopri come funziona l’interfaccia e quali estensioni sono disponibili.

- [Documentazione di Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=it)
