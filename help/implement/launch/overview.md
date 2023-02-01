---
title: Implementare Adobe Analytics utilizzando l’estensione Analytics
description: Scopri come implementare Adobe Analytics utilizzando tag ed estensione Analytics
feature: Launch Implementation
source-git-commit: aef1d613437688b7eed704b227c41e4fbe4677dd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 19%

---

# Implementare Adobe Analytics utilizzando l’estensione Analytics

Nel corso della vita di Adobe Analytics, Adobe ha offerto diversi metodi per implementare il codice sul sito per la raccolta dei dati. Il metodo attualmente consigliato da Adobe è tramite i tag in Adobe Experience Platform.

Tag in Adobe Experience Platform è una soluzione di gestione dei tag che consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza affidarsi ad alcun team di sviluppo dell’organizzazione per aggiornare il codice sul sito.

Tutti i clienti con un contratto Adobe Experience Cloud attivo possono utilizzare i tag . Se non sei sicuro di avere accesso, contatta uno degli amministratori di sistema di Experience Cloud della tua organizzazione.

Panoramica di alto livello delle attività di implementazione:



![Adobe Analytics tramite il flusso di lavoro dell’estensione Analytics](../assets/analytics-extension-annotated.png)

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
<td><b>Creare un livello di dati</b>per gestire il tracciamento dei dati sul sito web.</td>
<td>
<a href="../prepare/data-layer.md">Creare un livello di dati</a>
</td>
</tr>

<tr>
<td>3</td>
<td><b><b>Creare una proprietà tag</b>. Le proprietà sono contenitori sovrapposti utilizzati per fare riferimento ai dati di gestione dei tag.</td>
<td><a ref="../launch/create-analytics-property.md">Creare una proprietà tag in Adobe Analytics</a></td>
</tr>

<tr>
<td>4</td><td><b>Installare l’estensione Analytics</b> nella proprietà tag . Configura l’estensione Analytics per l’invio di dati ad Adobe Analytics.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=en">Panoramica dell’estensione Adobe Analytics</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Implementare in un ambiente di sviluppo</b>. Avere un ambiente in cui è possibile eseguire iterazioni sullo sviluppo dei tag.</td>
<td><a href="./deploy-dev.md">Distribuire un'implementazione di Analytics in un ambiente di sviluppo</td>
</tr>

<tr>
<td>6</td> 
<td><b>Convalidare e pubblicare nell’ambiente di produzione</b>. Aggiungi la proprietà tag al sito Web. Quindi utilizza elementi dati, regole e così via per personalizzare la tua implementazione.</td>
<td><a href="./validate-publish-prod.md">Convalidare un'implementazione di sviluppo e pubblicare in produzione</a></td>
</tr>

</table>

## Risorse aggiuntive

I tag possono essere altamente personalizzati. Ulteriori informazioni su come ottenere il massimo da Adobe Analytics includendo i dati giusti nella tua implementazione.

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it#): Scopri come funziona l’interfaccia e quali estensioni sono disponibili.

- [Variabili di implementazione](../vars/overview.md): Determina le variabili che desideri inviare ai server di raccolta dati.
