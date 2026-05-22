---
title: Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile
description: Utilizzare l’estensione Mobile SDK in Adobe Experience Platform Data Collection per inviare dati ad Adobe Analytics.
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/ooh8s8pNYbbsD9BmF48Nv3OyHN5JtDQonQw0Z1t4XXc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 565
ht-degree: 24%

---

# Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile

Adobe Experience Platform Mobile SDK consente di potenziare le soluzioni e i servizi Adobe CX Enterprise nelle app mobili. È disponibile per Android™, iOS e vari framework di sviluppo multipiattaforma. La configurazione viene gestita tramite Raccolta dati di Adobe Experience Platform.

>[!IMPORTANT]
>
>Un’estensione Adobe Analytics è disponibile anche in Raccolta dati di Adobe Experience Platform. Se installi questa estensione, non sfrutti XDM o la rete Edge.

## Adobe Experience Platform SDK

Panoramica ad alto livello dei compiti di implementazione:

![Adobe Analytics utilizzando il flusso di lavoro dell&#39;estensione Analytics](../../assets/mobilesdk-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Attività</b></th><th style="width:35%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td>1</td>
<td>Assicurati di aver <b>definito una suite di rapporti</b>.</td>
<td><a href="../../../admin/tools/manage-rs/report-suites-admin.md">Report Suite Manager</a></td>
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
<td><b>Installa l'estensione Adobe Experience Platform Edge Network</b> nella proprietà del tag per dispositivi mobili e configura lo stream di dati nell'estensione.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/edge-network/">Adobe Experience Platform Edge Network</a>
</tr>

<tr>
<td>6</td>
<td><b>Utilizza il codice nella tua app</b> per registrare le estensioni necessarie e caricare la configurazione di tag.</td>
<td><a href="https://developer.adobe.com/client-sdks/documentation/user-guides/getting-started-with-platform/overview/#set-up-the-configuration">Configurare la configurazione</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Implementa e verifica la funzionalità</b> utilizzando una combinazione di elementi dati del tag, regole, estensioni aggiuntive e chiamate API di SDK nell'app. Ispeziona, convalida ed esegui il debug della raccolta dati e delle esperienze per la tua app mobile.</td>
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
<td><a href="../../../admin/tools/manage-rs/report-suites-admin.md">Report Suite Manager</a></td>
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
<td><b>Implementa e verifica la funzionalità</b> utilizzando una combinazione di elementi dati del tag, regole, estensioni aggiuntive e chiamate API di SDK nell'app. Ispeziona, convalida ed esegui il debug della raccolta dati e delle esperienze per la tua app mobile.</td>
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
