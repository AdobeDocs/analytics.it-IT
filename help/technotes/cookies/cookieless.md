---
title: Opzioni per attenuare l’effetto delle limitazioni dei cookie del browser
description: Scopri come attenuare l’effetto delle limitazioni dei cookie del browser per migliorare la raccolta dei dati per Adobe Analytics.
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
role: Admin
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 1%

---

# Opzioni per attenuare l’effetto delle limitazioni dei cookie del browser

Questo documento illustra le opzioni per mantenere l’identificazione persistente dei visitatori tra le proprietà e le soluzioni, in quanto i principali browser implementano misure di prevenzione del tracciamento per i cookie.

Adobe Analytics si basa su cookie di prime parti per registrare l’attività di un visitatore sul sito. Analytics si basa anche su cookie di terze parti per comprendere l’attività off-site di un visitatore, ad esempio l’attività su altri domini di cui sei proprietario. I cookie di terze parti sono bloccati su molti browser e non saranno in gran parte disponibili con la prossima rimozione del supporto di Chrome (attualmente pianificata per la fine del 2024). I cookie di prime parti sono consentiti su tutti i browser ma hanno una scadenza limitata su Safari e altri browser in Apple [Prevenzione del tracciamento ITP](https://webkit.org/tracking-prevention) misure. Per ulteriori informazioni sulle attuali limitazioni dei cookie del browser, consulta [Cookie di Adobe Analytics e del browser](cookies.md).

Queste limitazioni dei browser riflettono un più ampio passaggio dal tracciamento anonimo di terze parti alla condivisione esplicita di informazioni tra utenti e marchi di cui si fidano. Per supportare questa migrazione, Adobe offre ai clienti dei modi per integrare i cookie tradizionali includendo identificatori durevoli raccolti tramite le relazioni di prima parte.

## Analytics per Customer Journey Analytics e multidispositivo

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it) e [Analytics tra dispositivi](/help/components/cda/overview.md) consente agli utenti di includere oltre ai cookie anche identificatori durevoli, come gli accessi con hash. Questo consente di comprendere il percorso del cliente tra i dispositivi e, nel caso del Customer Journey Analytics, tra i canali online e offline:

* **Customer Journey Analytics** è basato su Adobe Experience Platform e offre la flessibilità di combinare dati online e offline in Analysis Workspace, in base a qualsiasi ID cliente comune. Puoi specificare l’ID da utilizzare per una determinata analisi ed esplorare i dati in Analysis Workspace. I clienti di Analytics Select, Prime e Ultimate possono acquistarlo come prodotto aggiuntivo.

* **Analytics tra dispositivi** è un miglioramento del tradizionale Adobe Analytics che consente ai clienti di utilizzare identificatori alternativi per i visitatori. Questa funzionalità consente di passare da una visualizzazione incentrata sul dispositivo a una incentrata sulla persona. Analytics tra dispositivi è disponibile per i clienti Analytics Ultimate.

## Raccolta di dati lato server

La raccolta lato server offre la flessibilità di fornire il proprio identificatore anziché affidarsi ai meccanismi del browser per l’impostazione dei cookie.

È possibile inviare dati ad Analytics lato server utilizzando [API di inserimento dati](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) o [API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). L’API di inserimento dati in blocco è consigliata per le nuove implementazioni lato server. Per un confronto tra le due API, consulta la sezione &quot;[Quale strumento Adobe Analytics usare](/help/analyze/get-started/which-analytics-tool.md).&quot;

## ID dispositivo di prime parti (FPID) con Web SDK

Con Adobe Experience Platform Web SDK puoi scegliere di impostare e gestire i tuoi identificatori di dispositivo invece degli ID di Experience Cloud generati dagli Adobi (ECID). Questi sono denominati ID dispositivo di prime parti (FPID, first party device ID). Puoi trovare ulteriori informazioni [qui](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=it).

## Ulteriori informazioni

Per informazioni pratiche sulla transizione dai cookie di terze parti, consulta [Acquisisci e mantieni i clienti in un mondo senza cookie con Adobe](https://business.adobe.com/solutions/cookieless.html) e la documentazione dettagliata [Pensare oltre il cookie di terze parti: la tua guida completa a un mondo senza cookie di terze parti](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
>
>[Cookie di Adobe Analytics e del browser](cookies.md)
