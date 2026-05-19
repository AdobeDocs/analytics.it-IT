---
title: Implementare Adobe Analytics utilizzando l’estensione Analytics
description: Scopri come implementare Adobe Analytics utilizzando i tag e l’estensione Analytics
feature: Tags
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/bnn0eqUbhHvQL2YPd1qVa9cSWWvGbAAae33IyC-w9kA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 396
ht-degree: 25%

---

# Implementare Adobe Analytics utilizzando l’estensione Analytics

Nel corso del ciclo di vita di Adobe Analytics, Adobe ha offerto diversi metodi per implementare il codice sul sito per la raccolta dati. Il metodo attualmente consigliato da Adobe è tramite [Tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it) in Adobe Experience Platform.

Tag in Adobe Experience Platform è una soluzione di gestione dei tag che consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di implementare codice personalizzato. Tutte queste attività possono essere eseguite senza dover ricorrere a un team di sviluppatori nell’organizzazione per aggiornare il codice sul sito.

Tutti i clienti con un contratto Adobe CX Enterprise attivo possono utilizzare i tag. Se non si è sicuri di avere accesso, contattare uno degli amministratori di sistema CX Enterprise della propria organizzazione.

Panoramica ad alto livello dei compiti di implementazione:



![Come implementare Adobe Analytics utilizzando il flusso di lavoro dell&#39;estensione Analytics, come descritto in questa sezione.](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Attività</b></th><th style="width:35%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td> 1</td>
<td>Assicurati di aver <b>definito una suite di rapporti</b>.</td>
<td><a href="../../admin/tools/manage-rs/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Crea un livello dati</b> per gestire il tracciamento dei dati sul tuo sito Web.</td>
<td>
<a href="../prepare/data-layer.md">Creare un livello dati</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>Crea una proprietà tag</b>. Le proprietà sono contenitori generali utilizzati per fare riferimento ai dati di gestione dei tag.</td>
<td><a href="../launch/create-analytics-property.md">Creare una proprietà tag in Adobe Analytics</a></td>
</tr>

<tr>
<td>4</td><td><b>Installa l'estensione Analytics</b> nella proprietà tag. Configura l’estensione Analytics per inviare dati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=it">Panoramica dell’estensione Adobe Analytics</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Distribuisci in un ambiente di sviluppo</b>. Disporre di un ambiente in cui eseguire iterazioni sullo sviluppo dei tag.</td>
<td><a href="./deploy-dev.md">Implementazione di Analytics in un ambiente di sviluppo</td>
</tr>

<tr>
<td>6</td> 
<td><b>Convalida e pubblicazione in produzione</b>. Incorpora il codice per includere la proprietà tag nelle pagine del sito web. Quindi utilizza elementi dati, regole e così via, per personalizzare l’implementazione.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=it#embed-code">Codice di incorporamento</a><br/><a href="./validate-publish-prod.md">Convalidare un'implementazione di sviluppo e pubblicare in produzione</a></td>
</tr>

</table>

## Risorse aggiuntive

I tag possono essere altamente personalizzati. Scopri come ottenere il massimo da Adobe Analytics includendo i dati corretti nella tua implementazione.

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it#): scopri come funziona l&#39;interfaccia e quali estensioni sono disponibili.

- [Variabili di implementazione](../vars/overview.md): determinare le variabili da inviare ai server di raccolta dati.
