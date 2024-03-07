---
title: Implementare Adobe Analytics utilizzando l’estensione Analytics
description: Scopri come implementare Adobe Analytics utilizzando i tag e l’estensione Analytics
feature: Tags
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
role: Admin, Developer
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 8%

---

# Implementare Adobe Analytics utilizzando l’estensione Analytics

Durante il ciclo di vita di Adobe Analytics, Adobe ha offerto diversi metodi per implementare nel sito il codice per la raccolta dati. Il metodo consigliato corrente di Adobe è tramite [Tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it) in Adobe Experience Platform.

I tag in Adobe Experience Platform sono una soluzione di gestione dei tag che consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza dover ricorrere a team di sviluppo nell’organizzazione per aggiornare il codice sul sito.

Tutti i clienti con un contratto Adobe Experience Cloud attivo possono utilizzare i tag. Se non sai se puoi accedervi, contatta uno degli amministratori di sistema Experienci Cloud della tua organizzazione.

Panoramica ad alto livello dei compiti di implementazione:



![Come implementare Adobe Analytics utilizzando il flusso di lavoro dell’estensione di Analytics, come descritto in questa sezione.](../assets/analytics-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Attività</b></th><th style="width:35%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td> 1</td>
<td>Assicurati di avere <b>definizione di una suite di rapporti</b>.</td>
<td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Creare un livello di dati</b> per gestire il tracciamento dei dati sul sito web.</td>
<td>
<a href="../prepare/data-layer.md">Creare un livello di dati</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>Creare una proprietà tag</b>. Le proprietà sono contenitori generali utilizzati per fare riferimento ai dati di gestione dei tag.</td>
<td><a href="../launch/create-analytics-property.md">Creare una proprietà tag in Adobe Analytics</a></td>
</tr>

<tr>
<td>4</td><td><b>Installare l’estensione Analytics</b> nella proprietà tag. Configura l’estensione Analytics per inviare dati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=it">Panoramica dell’estensione Adobe Analytics</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Implementare in un ambiente di sviluppo</b>. Disporre di un ambiente in cui eseguire iterazioni sullo sviluppo dei tag.</td>
<td><a href="./deploy-dev.md">Implementazione di Analytics in un ambiente di sviluppo</td>
</tr>

<tr>
<td>6</td> 
<td><b>Convalida e pubblicazione in produzione</b>. Incorpora il codice per includere la proprietà tag nelle pagine del sito web. Quindi utilizza elementi dati, regole e così via, per personalizzare l’implementazione.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html#embed-code">Codice di incorporamento</a><br/><a href="./validate-publish-prod.md">Convalidare un’implementazione di sviluppo e pubblicare in produzione</a></td>
</tr>

</table>

## Risorse aggiuntive

I tag possono essere altamente personalizzati. Scopri come ottenere il massimo da Adobe Analytics includendo i dati corretti nella tua implementazione.

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#): scopri come funziona l’interfaccia e quali estensioni sono disponibili.

- [Variabili di implementazione](../vars/overview.md): determina le variabili da inviare ai server di raccolta dati.
