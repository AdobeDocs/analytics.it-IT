---
title: Transizione da una piattaforma di analisi di terze parti ad Adobe Analytics
description: Scopri i concetti chiave per ottenere i rapporti, rivolti agli utenti che hanno familiarità con altre piattaforme, come Google Analytics.
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 6%

---


# Transizione da una piattaforma di analisi di terze parti ad Adobe Analytics

Questa guida presenta i tipi di report più comuni che consentono di apprendere i concetti e i flussi di lavoro di base in Adobe Analytics, concentrandosi sulle somiglianze e le differenze chiave tra Adobe e altri strumenti più diffusi. Questa guida è stata progettata per gli analisti che hanno familiarità con i concetti di base dell&#39;analisi digitale, ma che hanno familiarità con Adobe Analytics. Presuppone che l&#39;organizzazione disponga di un&#39;implementazione funzionante che invia dati ai server di raccolta dati Adobe. Se la tua organizzazione non ha ancora configurato un&#39;implementazione di Adobe Analytics, inizia con la [Adobe Analytics First Admin Guide](/help/admin/admin-console/first-admin-guide.md).

Google Analytics e Adobe Analytics sono piattaforme potenti per ottenere informazioni preziose sulle prestazioni del sito Web. Ognuna di esse dispone di una propria architettura di elaborazione e di un&#39;interfaccia utente, che offrono a ogni piattaforma vantaggi unici. Questa guida è stata progettata per aiutare un utente a seguire Google Analytics con Adobe Analytics.

In Adobe Analytics, dopo aver effettuato l&#39;accesso ad Adobe Experience Cloud, i rapporti di base sono due modi principali:

* **Reporting e analisi** è il metodo storico per l&#39;estrazione di report di base. Il menu a sinistra contiene un elenco di rapporti prefabbricati che consentono all&#39;utente di passare a un rapporto desiderato e ottenere i dati. Segmenti e metriche possono fornire personalizzazioni aggiuntive. Gli utenti che hanno esperienza con i rapporti di Google Analytics potrebbero avere familiarità con questo layout.
* **Analysis Workspace** è il metodo attualmente consigliato per eseguire il pulling della maggior parte dei report. Il menu a sinistra consente all’utente di trascinare e rilasciare componenti per creare un proprio rapporto. Consente una maggiore libertà per soddisfare le esigenze di reporting esatte. Gli utenti esperti nella creazione di dashboard di Google Analytics e di rapporti personalizzati potrebbero avere familiarità con questo layout.

La maggior parte dei rapporti può essere creata sia in [!UICONTROL Reports & Analytics] che [!UICONTROL Analysis Workspace]. Tuttavia, alcuni report possono essere estratti solo utilizzando una piattaforma o l&#39;altra. Nella maggior parte dei casi, Adobe consiglia di utilizzare [!UICONTROL Analysis Workspace], a meno che una funzione specifica non sia disponibile solo in [!UICONTROL Reports & Analytics].

## Percorso di apprendimento consigliato

Adobe consiglia di iniziare con le nozioni di base assolute per ottenere i dati dei rapporti:

* [Creare un rapporto di base in Analysis Workspace per gli utenti GA](reports/create-report.md)

Una volta acquisita familiarità con i componenti in [!UICONTROL Analysis Workspace], puoi imparare a ricreare la maggior parte dei rapporti utilizzando i componenti appropriati.

* [Creare rapporti in tempo reale in Adobe Analytics](reports/realtime-reports.md)
* [Creazione di rapporti sull&#39;audience in Adobe Analytics](reports/audience-reports.md)
* [Creare rapporti di acquisizione in Adobe Analytics](reports/acquisition-reports.md)
* [Creare rapporti sul comportamento in Adobe Analytics](reports/behavior-reports.md)
* [Creare rapporti sulle conversioni in Adobe Analytics](reports/conversions-reports.md)

Dopo aver appreso il pulling dei report, è possibile comprendere [le differenze](processing-differences.md) di elaborazione e architettura per riconciliare i diversi numeri ottenuti tra le piattaforme. Sono inoltre disponibili [le domande frequenti](faq.md) .
