---
title: Implementare Adobe Analytics utilizzando l’estensione Analytics
description: Scopri come implementare Adobe Analytics utilizzando tag ed estensione Analytics
feature: Launch Implementation
source-git-commit: 472faef9c6ef99d4e58f2f5a9a71ca8d058f0ee2
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 10%

---

# Implementare Adobe Analytics utilizzando l’estensione Analytics

Nel corso della vita di Adobe Analytics, Adobe ha offerto diversi metodi per implementare il codice sul sito per la raccolta dei dati. Il metodo attualmente consigliato da Adobe è tramite i tag in Adobe Experience Platform.

Tag in Adobe Experience Platform è una soluzione di gestione dei tag che consente di distribuire il codice Analytics insieme ad altri requisiti di assegnazione tag. Adobe offre integrazioni con altre soluzioni e prodotti e consente di distribuire codice personalizzato. Tutte queste attività possono essere eseguite senza affidarsi ad alcun team di sviluppo dell’organizzazione per aggiornare il codice sul sito.

Tutti i clienti con un contratto Adobe Experience Cloud attivo possono utilizzare i tag . Se non sei sicuro di avere accesso, contatta uno degli amministratori di sistema di Experience Cloud della tua organizzazione.

Panoramica di alto livello delle attività di implementazione:

![Adobe Analytics tramite il flusso di lavoro dell’estensione Analytics](../assets/analytics-extension-annotated.png)

| | Attività | Ulteriori informazioni | |-| —|—| | 1 | Assicurati di avere **definizione di una suite di rapporti**. | [Report Suite Manager](../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **Creare un livello di dati** per gestire il tracciamento dei dati sul sito web. | [Creare un livello di dati](../prepare/data-layer.md) | | 3 | **Creare una proprietà tag**. Le proprietà sono contenitori sovrapposti utilizzati per fare riferimento ai dati di gestione dei tag.| [Creare una proprietà tag Adobe Analytics](../launch/create-analytics-property.md) | | 4 | **Installare l’estensione Analytics** nella proprietà tag . Configura l’estensione Analytics per l’invio di dati ad Adobe Analytics. | [Panoramica dell&#39;estensione Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=en) | | 5 | **Distribuire in un ambiente di sviluppo**. Avere un ambiente in cui è possibile eseguire iterazioni sullo sviluppo dei tag. | [Distribuire un&#39;implementazione di Analytics in un ambiente di sviluppo](./deploy-dev.md) | | 6 | **Convalidare e pubblicare in produzione**. Aggiungi la proprietà tag al sito Web. Quindi utilizza elementi dati, regole e così via per personalizzare la tua implementazione.| [Convalidare un&#39;implementazione di sviluppo e pubblicare in produzione](./validate-publish-prod.md) |

## Risorse aggiuntive

I tag possono essere altamente personalizzati. Ulteriori informazioni su come ottenere il massimo da Adobe Analytics includendo i dati giusti nella tua implementazione.

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it#): Scopri come funziona l’interfaccia e quali estensioni sono disponibili.

- [Variabili di implementazione](../vars/overview.md): Determina le variabili che desideri inviare ai server di raccolta dati.
