---
title: Opzioni per mitigare l’effetto delle limitazioni dei cookie del browser
description: Scopri come mitigare l’effetto delle limitazioni dei cookie del browser per migliorare la raccolta dei dati per Adobe Analytics.
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
role: Admin
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 99%

---

# Opzioni per mitigare l’effetto delle limitazioni dei cookie del browser

Questo documento illustra le opzioni per preservare l’identificazione persistente dei visitatori tra proprietà e soluzioni poiché i principali browser implementano misure di prevenzione del tracciamento per i cookie.

Adobe Analytics si basa su cookie di prime parti per registrare l’attività interna di un visitatore. Analytics si basa anche su cookie di terze parti per comprendere l’attività esterna di un visitatore, come l’attività su altri domini di tua proprietà. I cookie di terze parti sono bloccati su molti browser e saranno in gran parte non disponibili con l’imminente rimozione del supporto da parte di Chrome (attualmente prevista per la fine del 2024). I cookie di prime parti sono consentiti su tutti i browser ma hanno una scadenza limitata su Safari e altri browser nell’ambito delle [misure di prevenzione del tracciamento ITP](https://webkit.org/tracking-prevention) di Apple. Per ulteriori informazioni sulle attuali limitazioni sui cookie del browser, consulta [Adobe Analytics e cookie del browser](cookies.md).

Queste limitazioni del browser riflettono un più ampio allontanamento dal tracciamento anonimo di terze parti verso la condivisione esplicita delle informazioni tra utenti e marchi di cui si fidano. Per supportare questa iniziativa, Adobe offre alla clientela la modalità per integrare i cookie tradizionali includendo identificatori durevoli raccolti tramite le relazioni di prima parte.

## Customer Journey Analytics e Cross Device Analytics

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it) e [Cross-Device Analytics](/help/components/cda/overview.md) consentono agli utenti di includere identificatori durevoli, come accessi con hash, oltre ai cookie. Ciò consente di comprendere il percorso del cliente su tutti i dispositivi e, nel caso di Customer Journey Analytics, sui canali online e offline:

* **Customer Journey Analytics** è basato su Adobe Experience Platform e offre la flessibilità di combinare dati online e offline in Analysis Workspace, in base a qualsiasi ID cliente comune. Puoi specificare quale ID desideri utilizzare per una determinata analisi ed esplorare i dati in Analysis Workspace. I clienti di Analytics Select, Prime e Ultimate possono acquistare questo prodotto aggiuntivo.

* **Cross-Device Analytics** è un miglioramento del tradizionale Adobe Analytics che consente di utilizzare identificatori alternativi per i visitatori. Questa funzionalità ti consente di passare da una visione incentrata sul dispositivo a una visione incentrata sulla persona. Cross-Device Analytics è disponibile per i clienti Analytics Ultimate.

## Raccolta dati lato server

La raccolta lato server offre la flessibilità di fornire il proprio identificatore anziché fare affidamento sui meccanismi del browser per l’impostazione dei cookie.

Puoi inviare dati al lato server di Analytics utilizzando l’[API di inserimento dati](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) o l’[API di inserimento dati in blocco](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/). L’API di inserimento dati in blocco è consigliata per le nuove implementazioni lato server. Per un confronto tra le due API, consulta “[Quale strumento di Adobe Analytics dovrei utilizzare](/help/analyze/get-started/which-analytics-tool.md).”

## ID dispositivo di prime parti (FPID) con Web SDK

Con Adobe Experience Platform Web SDK puoi scegliere di impostare e gestire i tuoi identificatori di dispositivo invece degli ID di Experience Cloud (ECID) generati da Adobe. Questi sono indicati come ID dispositivo di prime parti (FPID). Puoi trovare ulteriori informazioni [qui](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=it).

## Ulteriori informazioni

Per i passaggi pratici che la tua azienda può intraprendere per abbandonare i cookie di terze parti, consulta [Acquisire e mantenere i clienti in un mondo senza cookie con Adobe](https://business.adobe.com/it/solutions/cookieless.html) e l’approfondimento [Pensare oltre i cookie di terze parti: la guida completa per un mondo senza cookie di terze parti](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).”

>[!MORELIKETHIS]
>
>[Cookie di Adobe Analytics e del browser](cookies.md)
