---
title: Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK
description: Utilizza l’estensione Web SDK in Adobe Experience Platform Data Collection per inviare dati ad Adobe Analytics.
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 22%

---

# Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK

Puoi utilizzare [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) per inviare dati ad Adobe Analytics. Questo metodo di implementazione funziona traducendo il [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it) in un formato utilizzato da Analytics.

Puoi inviare dati a Experience Edge direttamente utilizzando l’SDK per web o tramite l’estensione SDK per web in Tag.

## SDK per web

Panoramica di alto livello delle attività di implementazione:

![Implementazione del flusso di lavoro Adobe Analytics tramite SDK per web](../../assets/websdk-annotated.png)

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
<td><b>Configurazione di schemi e set di dati</b>. Per standardizzare la raccolta di dati da utilizzare nelle applicazioni che sfruttano Adobe Experience Platform, Adobe ha creato lo standard aperto e documentato pubblicamente, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=it">Panoramica dell’interfaccia utente degli schemi</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it">Panoramica dell’interfaccia utente dei set di dati</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Creare un livello di dati</b> per gestire il tracciamento dei dati sul sito web.</td>
<td><a href="../../prepare/data-layer.md">Creare un livello di dati</a></td>
</tr>

<tr>
<td> 4</td>
<td><b>Installare la versione standalone predefinita</b>. Puoi fare riferimento alla libreria (<code>alloy.js</code>) sulla rete CDN direttamente sulla tua pagina o scaricala e ospitala sulla tua infrastruttura. In alternativa, è possibile utilizzare il pacchetto NPM.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version">Installazione della versione autonoma predefinita</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package">Utilizzo del pacchetto NPM</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configurare un datastream</b>. Un datastream rappresenta la configurazione lato server durante l'implementazione dell'SDK per web Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">Configurare un datastream<a></td> 
</tr>

<td>6</td>
<td><b>Aggiungere un servizio Adobe Analytics</b> al tuo datastream. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Aggiungere il servizio Adobe Analytics a un datastream</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configurare l’SDK per web</b>. Assicurati che la libreria installata nel passaggio 4 sia configurata correttamente con l'ID del datastream (precedentemente noto come id di configurazione perimetrale (<code>edgeConfigId</code>), id organizzazione (<code>orgId</code>) e altre opzioni disponibili.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it">Configurare l’SDK per web</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Esegui comandi</b> e/o <b>eventi di tracciamento</b>. Una volta implementato il codice di base sulla pagina web, puoi iniziare a eseguire comandi ed eventi di tracciamento con l'SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en">Esegui comandi</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en">Tracciare gli eventi</a></td>
</tr>

<tr>
<td>9</td><td><b>Estendi e convalida l’implementazione</b> prima di spingerlo verso la produzione.</td><td></td> 
</tr>
</table>


## Estensione SDK per web

Panoramica di alto livello delle attività di implementazione:

![Implementare Adobe Analytics tramite il flusso di lavoro dell&#39;estensione dell&#39;SDK per web](../../assets/websdk-extension-annotated.png)

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
<td><b>Configurazione di schemi e set di dati</b>. Per standardizzare la raccolta di dati da utilizzare nelle applicazioni che sfruttano Adobe Experience Platform, Adobe ha creato lo standard aperto e documentato pubblicamente, Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=it">Panoramica dell’interfaccia utente degli schemi</a> e <a href="https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=it">Panoramica dell’interfaccia utente dei set di dati</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Creare un livello di dati</b> per gestire il tracciamento dei dati sul sito web.</td>
<td><a href="../../prepare/data-layer.md">Creare un livello di dati</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Configurare un datastream</b>. Un datastream rappresenta la configurazione lato server durante l'implementazione dell'SDK per web Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">Configurare un datastream<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>Aggiungere un servizio Adobe Analytics</b> al tuo datastream. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Aggiungere il servizio Adobe Analytics a un datastream</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Creare una proprietà tag</b>. Le proprietà sono contenitori sovrapposti utilizzati per fare riferimento ai dati di gestione dei tag.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web">Creare o configurare una proprietà tag per il Web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Installare e configurare l’estensione SDK per web</b> nella proprietà tag. Configura l'estensione Web SDK per inviare dati al datastream configurato nel passaggio 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en">Panoramica dell’estensione Adobe Experience Platform Web SDK</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Itera, convalida e pubblica</b> alla produzione. Aggiungi la proprietà tag al sito Web. Quindi utilizza elementi dati, regole e così via per personalizzare la tua implementazione.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en">Panoramica sulla pubblicazione</a></td>
</tr>

</table>


## Risorse aggiuntive

I tag possono essere altamente personalizzati. Ulteriori informazioni su come ottenere il massimo da Adobe Analytics includendo i dati giusti nella tua implementazione.

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it#): Scopri come funziona l’interfaccia e quali estensioni sono disponibili.

- [Documentazione di Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=it)
