---
title: Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile
description: Utilizzare l’estensione Mobile SDK in Adobe Experience Platform Data Collection per inviare dati ad Adobe Analytics.
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 8b585a1a05b5fcabd343da52a4b6f05fea8fd86f
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 28%

---

# Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile

L’Adobe Experience Platform Mobile SDK aiuta ad alimentare soluzioni e servizi di Adobe Experience Cloud nelle app mobile. È disponibile per Android™, iOS e vari framework di sviluppo multipiattaforma. La configurazione viene gestita tramite Raccolta dati di Adobe Experience Platform.

>[!IMPORTANT]
>
>Un’estensione Adobe Analytics è disponibile anche in Raccolta dati di Adobe Experience Platform. Se installi questa estensione, non sfrutti XDM o la rete Edge.

## SDK per Adobe Experience Platform

Panoramica ad alto livello dei compiti di implementazione:

![Adobe Analytics utilizzando il flusso di lavoro dell&#39;estensione Analytics](../../assets/mobilesdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Attività</b></th><th style="width:35%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td>1</td>
<td>Assicurati di aver <b>definito una suite di rapporti</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configura uno stream di dati</b>. Un flusso di dati rappresenta la configurazione lato server durante l’implementazione di Adobe Experience Platform Web SDK.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=it">Configurare uno stream di dati<a></td> 
</tr>

<td>3</td>
<td><b>Aggiungi un servizio Adobe Analytics</b> allo stream di dati. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=it#analytics">Aggiungere il servizio Adobe Analytics a uno stream di dati</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Crea una proprietà mobile</b>. Una proprietà è un contenitore che si riempie con estensioni, regole, elementi dati e librerie.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/">Configurare una proprietà mobile</a></tr>

<tr>
<td>5</td>
<td><b>Installa l'estensione dell'Edge Network Adobe Experience Platform</b> nella proprietà del tag per dispositivi mobili e configura lo stream di dati nell'estensione.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Edge Network Adobe Experience Platform</a>
</tr>

<tr>
<td>6</td>
<td><b>Utilizza il codice nella tua app</b> per registrare le estensioni necessarie e caricare la configurazione di tag.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Configurare la configurazione</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Implementa e verifica la funzionalità</b> utilizzando una combinazione di elementi dati del tag, regole, estensioni aggiuntive e chiamate API SDK nell'app. Inspect, convalida ed esegui il debug della raccolta dati e delle esperienze per la tua app mobile.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Utilizza l'applicazione di esempio</a>
</tr>

<tr>
<td>8</td>
<td><b>Estendi e convalida l'implementazione dell'app mobile</b> prima di inviarla alla produzione.</td>
<td></td> 
</tr>

</table>


## Estensione Adobe Analytics.

Panoramica ad alto livello dei compiti di implementazione:

![Adobe Analytics utilizzando il flusso di lavoro dell&#39;estensione Analytics](../../assets/mobilesdk-analytics-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Attività</b></th><th style="width:35%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td>1</td>
<td>Assicurati di aver <b>definito una suite di rapporti</b>.</td>
<td><a href="../../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Installa l'estensione Adobe Analytics</b> nella proprietà dei tag per dispositivi mobili e configura l'estensione in modo che punti alla suite di rapporti.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/adobe-analytics/">Estensione Adobe Analytics per la proprietà mobile</a>
</tr>

<tr>
<td>3</td>
<td><b>Utilizza il codice nella tua app</b> per registrare le estensioni necessarie e caricare la configurazione di tag.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Configurare la configurazione</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Implementa e verifica la funzionalità</b> utilizzando una combinazione di elementi dati del tag, regole, estensioni aggiuntive e chiamate API SDK nell'app. Inspect, convalida ed esegui il debug della raccolta dati e delle esperienze per la tua app mobile.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#use-the-sample-application">Utilizza l'applicazione di esempio</a>
</tr>

<tr>
<td>5</td>
<td><b>Estendi e convalida l'implementazione dell'app mobile</b> prima di inviarla alla produzione.</td>
<td></td> 
</tr>

</table>

## Risorse aggiuntive

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it#)

- [Documentazione di Mobile SDK](https://developer.adobe.com/client-sdks/documentation/)
