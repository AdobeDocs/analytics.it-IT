---
title: Implementare Adobe Analytics utilizzando l’API del server di rete Edge di Adobe Experience Platform
description: Utilizza l’API del server di rete Edge di Adobe Experience Platform per inviare dati ad Adobe Analytics.
exl-id: 1ede95b7-4f17-4d69-aba6-62b253b6693a
feature: Implementation Basics
source-git-commit: 5ebc53e8706f60988b289df060be9b02b5dc778f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 12%

---

# Implementare Adobe Analytics utilizzando l’API del server di rete Edge di Adobe Experience Platform

In genere si utilizza l’API server di rete Edge di Experienci Platform per raccogliere dati da dispositivi come dispositivi IoT, set-top box e applicazioni desktop. Quindi invia i dati alla rete Edge e a servizi come Adobe Analytics.

Considera anche l’API del server di rete Edge quando richiedi che i dati sensibili vengano raccolti in modo sicuro e autenticati in tutta la rete. Consulta [Autenticazione](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/authentication.html?lang=en) per ulteriori informazioni.

Panoramica ad alto livello dei compiti di implementazione:

![Adobe Analytics utilizzando il flusso di lavoro dell’estensione Analytics](../../assets/edge-network-server-api.svg)

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
<td><b>Configurare uno stream di dati</b>. Un flusso di dati rappresenta la configurazione lato server quando si utilizzano le API dall’API di Adobe Experience Platform Edge Network.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en">Configurare uno stream di dati<a></td> 
</tr>

<tr>
<td>4</td>
<td><b>Implementare e testare la raccolta dei dati</b> utilizzando le API di raccolta dati di eventi Single event e Batch.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=en">Raccolta di dati per evento singolo</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html?lang=en">Raccolta dati di eventi batch</a>
</tr>

<td>5</td>
<td><b>Aggiungere un servizio Adobe Analytics</b> allo stream di dati. Tale servizio controlla se e come i dati vengono inviati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=ens">Interazione con Adobe Analytics</a></td>
</tr>


</table>

Consulta [Documentazione API del server di rete Edge](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/overview.html?lang=it), e un esempio [integrazione con Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/interacting-other-adobe-solutions/interacting-adobe-analytics.html?lang=it) per ulteriori informazioni.

