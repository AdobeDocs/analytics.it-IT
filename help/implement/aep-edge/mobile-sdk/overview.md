---
title: Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile
description: Utilizzare l’estensione Mobile SDK in Adobe Experience Platform Data Collection per inviare dati ad Adobe Analytics.
source-git-commit: 97bff355a5d9bb737d510221b63ba1321aaf5812
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile

L’Adobe Experience Platform Mobile SDK aiuta ad alimentare soluzioni e servizi di Adobe Experience Cloud nelle app mobile. È disponibile per Android™, iOS e vari framework di sviluppo multipiattaforma. La configurazione viene gestita tramite Raccolta dati di Adobe Experience Platform.
>[!IMPORTANT]
>
>Un’estensione Adobe Analytics è disponibile anche in Raccolta dati di Adobe Experience Platform. Se installi questa estensione, non sfrutti XDM o la rete Edge.

## SDK per Adobe Experience Platform

Panoramica di alto livello delle attività di implementazione:

![Adobe Analytics tramite il flusso di lavoro dell’estensione Analytics](../../assets/mobilesdk-annotated.png)

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
<td><b>Configurare un datastream</b>. Un datastream rappresenta la configurazione lato server durante l'implementazione dell'SDK per web Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en">Configurare un datastream<a></td> 
</tr>

<td>4</td>
<td><b>Aggiungere un servizio Adobe Analytics</b> al tuo datastream. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics">Aggiungere il servizio Adobe Analytics a un datastream</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Creare una proprietà mobile</b>. Una proprietà è un contenitore che si riempie con estensioni, regole, elementi dati e librerie.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">Impostare una proprietà mobile</a></tr>

<tr>
<td>6</td>
<td><b>Installare l’estensione Adobe Experience Platform Edge Network</b> nella proprietà tag mobile e configura il datastream nell’estensione .</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform Edge Network</a>
</tr>

<tr>
<td>7</td>
<td><b>Usa il codice nella tua app</b> per registrare le estensioni necessarie e caricare la configurazione del tag.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Imposta la configurazione</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Implementazione e funzionalità di test</b> utilizzando una combinazione di elementi dati, regole, estensioni aggiuntive e chiamate API SDK nella tua app. Inspect, convalida ed esegui il debug della raccolta dati e delle esperienze per la tua app mobile.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Utilizzare l'applicazione di esempio</a>
</tr>

<tr>
<td>9</td>
<td><b>Estendere e convalidare l’implementazione dell’app mobile</b> prima di spingerlo verso la produzione.</td>
<td></td> 
</tr>

</table>


## Estensione Adobe Analytics.

Panoramica di alto livello delle attività di implementazione:

![Adobe Analytics tramite il flusso di lavoro dell’estensione Analytics](../../assets/mobilesdk-analytics-annotated.png)

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
<td><b>Installare l’estensione Adobe Analytics</b> nella proprietà tag mobile e configura l’estensione in modo che punti alla suite di rapporti.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">Estensione Adobe Analytics per la proprietà mobile</a>
</tr>

<tr>
<td>4</td>
<td><b>Usa il codice nella tua app</b> per registrare le estensioni necessarie e caricare la configurazione del tag.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Imposta la configurazione</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Implementazione e funzionalità di test</b> utilizzando una combinazione di elementi dati, regole, estensioni aggiuntive e chiamate API SDK nella tua app. Inspect, convalida ed esegui il debug della raccolta dati e delle esperienze per la tua app mobile.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Utilizzare l'applicazione di esempio</a>
</tr>

<tr>
<td>6</td>
<td><b>Estendere e convalidare l’implementazione dell’app mobile</b> prima di spingerlo verso la produzione.</td>
<td></td> 
</tr>

</table>

## Risorse aggiuntive

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it#)

- [Documentazione di Mobile SDK](https://developer.adobe.com/client-sdks/documentation/)



