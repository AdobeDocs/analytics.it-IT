---
title: Implementare Adobe Analytics utilizzando l’API Edge Network di Adobe Experience Platform
description: Utilizza l’API Edge Network di Adobe Experience Platform per inviare dati ad Adobe Analytics.
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/lvnplKx6dPwmmbZWgSShGvZXD2TtUoigi-HNiKutZSg'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 20%

---

# Implementare Adobe Analytics utilizzando l’API Edge Network di Adobe Experience Platform

In genere si utilizza l’API di Experience Platform Edge Network per raccogliere i dati lato server anziché lato client e durante la raccolta di dati da dispositivi quali dispositivi IoT, set-top box e applicazioni desktop. Poi invii i dati alla rete Edge e a servizi come Adobe Analytics.

Considera anche l’API di Edge Network quando hai bisogno che i dati sensibili vengano raccolti in modo sicuro e autenticati in tutta la rete. Per ulteriori informazioni, vedere [Autenticazione](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html).

Panoramica ad alto livello dei compiti di implementazione:

![Adobe Analytics utilizzando il flusso di lavoro dell&#39;estensione Analytics](../../assets/edge-network-server-api-annotated.png)

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
<td><b>Imposta schemi</b>. Per standardizzare la raccolta dati da utilizzare nelle applicazioni che sfruttano Adobe Experience Platform, Adobe ha creato lo standard aperto e pubblicamente documentato Experience Data Model (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=it">Panoramica dell’interfaccia utente degli schemi</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Configura uno stream di dati</b>. Uno stream di dati rappresenta la configurazione lato server quando si utilizzano le API dall’API Edge Network di Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it">Configurare uno stream di dati<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>Implementare e testare la raccolta dati</b> utilizzando le API di raccolta dati evento singolo e evento batch.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=it">Raccolta dati evento singolo</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html">Raccolta dati evento batch</a>
</tr>

<td>5</td>
<td><b>Aggiungi un servizio Adobe Analytics</b> allo stream di dati. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=it">Interazione con Adobe Analytics</a></td>
</tr>


</table>

Per ulteriori informazioni, consulta la [documentazione API di Edge Network](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=it).

