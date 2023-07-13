---
title: Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK
description: Utilizza l’estensione Web SDK in Adobe Experience Platform Data Collection per inviare dati ad Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
source-git-commit: bef853934683f647e05d42e1a751217c8f9b5dc4
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 22%

---

# Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK

Puoi utilizzare [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) per inviare dati ad Adobe Analytics. Questo metodo di implementazione funziona traducendo il [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) in un formato utilizzato da Analytics.

Puoi inviare dati a Experience Edge direttamente tramite Web SDK o l’estensione Web SDK in Tags.

## SDK per web

Panoramica ad alto livello dei compiti di implementazione:

![Come implementare Adobe Analytics utilizzando il flusso di lavoro Web SDK, come descritto in questa sezione.](../../assets/websdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Attività</b></th><th style="width:35%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td>1</td>
<td>Assicurati di avere <b>definizione di una suite di rapporti</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurare schemi e set di dati</b>. Per standardizzare la raccolta dati da utilizzare nelle applicazioni che sfruttano Adobe Experience Platform, Adobe ha creato lo standard aperto e pubblicamente documentato Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=it">Panoramica dell’interfaccia utente degli schemi</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it">Panoramica dell’interfaccia utente dei set di dati</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Creare un livello di dati</b> per gestire il tracciamento dei dati sul sito web.</td>
<td><a href="../../prepare/data-layer.md">Creare un livello di dati</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>Installare la versione standalone predefinita</b>. Puoi fare riferimento alla libreria (<code>alloy.js</code>) sulla rete CDN direttamente sulla pagina oppure scaricala e ospitala sulla tua infrastruttura. In alternativa, è possibile utilizzare il pacchetto NPM.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version">Installazione della versione standalone pregenerata</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package">Utilizzo del pacchetto NPM</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configurare uno stream di dati</b>. Un flusso di dati rappresenta la configurazione lato server durante l’implementazione di Adobe Experience Platform Web SDK.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">Configurare uno stream di dati<a></td> 
</tr>

<td>6</td>
<td><b>Aggiungere un servizio Adobe Analytics</b> allo stream di dati. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Aggiungere il servizio Adobe Analytics a uno stream di dati</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configurare l’SDK per web</b>. Assicurati che la libreria installata nel passaggio 4 sia configurata correttamente con l’ID dello stream di dati (precedentemente noto come ID di configurazione edge )<code>edgeConfigId</code>)), id organizzazione (<code>orgId</code>) e altre opzioni disponibili.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it">Configurare l’SDK per web</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Esegui comandi</b> e/o <b>tracciare gli eventi</b>. Una volta implementato il codice di base nella pagina web, puoi iniziare a eseguire comandi ed eventi di tracciamento con l’SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en">Esegui comandi</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en">Tracciare gli eventi</a></td>
</tr>

<tr>
<td>9</td><td><b>Estendere e convalidare l’implementazione</b> prima di implementarlo in produzione.</td><td></td> 
</tr>
</table>


## Estensione Web SDK

Panoramica ad alto livello dei compiti di implementazione:

![Come implementare Adobe Analytics utilizzando il flusso di lavoro dell’estensione Web SDK, come descritto in questa sezione.](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Attività</b></th><th style="width:35%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td>1</td>
<td>Assicurati di avere <b>definizione di una suite di rapporti</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurare schemi e set di dati</b>. Per standardizzare la raccolta dati da utilizzare nelle applicazioni che sfruttano Adobe Experience Platform, Adobe ha creato lo standard aperto e pubblicamente documentato Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=it">Panoramica dell’interfaccia utente degli schemi</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it">Panoramica dell’interfaccia utente dei set di dati</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Creare un livello di dati</b> per gestire il tracciamento dei dati sul sito web.</td>
<td><a href="../../prepare/data-layer.md">Creare un livello di dati</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Configurare uno stream di dati</b>. Un flusso di dati rappresenta la configurazione lato server durante l’implementazione di Adobe Experience Platform Web SDK.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">Configurare uno stream di dati<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>Aggiungere un servizio Adobe Analytics</b> allo stream di dati. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Aggiungere il servizio Adobe Analytics a uno stream di dati</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Creare una proprietà tag</b>. Le proprietà sono contenitori generali utilizzati per fare riferimento ai dati di gestione dei tag.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web">Creare o configurare una proprietà tag per il Web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Installare e configurare l’estensione Web SDK</b> nella proprietà tag. Configura l’estensione Web SDK per inviare i dati allo stream di dati configurato nel passaggio 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en">Panoramica dell’estensione Adobe Experience Platform Web SDK</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Iterare, convalidare e pubblicare</b> alla produzione. Aggiungi la proprietà tag al tuo sito web. Quindi utilizza elementi dati, regole e così via, per personalizzare l’implementazione.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en">Panoramica sulla pubblicazione</a></td>
</tr>

</table>


## Risorse aggiuntive

I tag possono essere altamente personalizzati. Scopri come ottenere il massimo da Adobe Analytics includendo i dati corretti nella tua implementazione.

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it#): scopri come funziona l’interfaccia e quali estensioni sono disponibili.

- [Documentazione di Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=it)
