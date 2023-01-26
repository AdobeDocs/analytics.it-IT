---
title: Opzioni per attenuare l’effetto delle limitazioni dei cookie del browser
description: Scopri come attenuare l’effetto delle limitazioni dei cookie del browser per migliorare la raccolta dei dati per Adobe Analytics.
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
source-git-commit: 860621a058826ba8bf602d87a702f835c7c00a37
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 7%

---

# Opzioni per attenuare l’effetto delle limitazioni dei cookie del browser

Questo documento illustra le opzioni per mantenere l’identificazione persistente dei visitatori tra proprietà e soluzioni man mano che i principali browser implementano misure di prevenzione del tracciamento per i cookie.

Adobe Analytics si basa sui cookie di prime parti per registrare l’attività in loco di un visitatore. Analytics si basa anche sui cookie di terze parti per comprendere l’attività off-site di un visitatore, ad esempio l’attività su altri domini di cui sei titolare. I cookie di terze parti sono bloccati su molti browser e non saranno disponibili per la maggior parte con la prossima rimozione del supporto da parte di Chrome (attualmente pianificata per la fine del 2024). I cookie di prime parti sono consentiti su tutti i browser, ma hanno una scadenza limitata su Safari e altri browser in Apple [Prevenzione del tracking ITP](https://webkit.org/tracking-prevention) misure. Per ulteriori informazioni sulle limitazioni attuali dei cookie del browser, vedi [Cookie di Adobe Analytics e browser](cookies.md).

Queste limitazioni del browser riflettono una più ampia transizione dal tracciamento anonimo di terze parti verso la condivisione esplicita di informazioni tra utenti e marchi di cui si fidano. Per supportare questa mossa, Adobe offre ai clienti dei modi di integrare i cookie tradizionali includendo identificatori durevoli raccolti tramite le loro relazioni di prima parte.

## Analisi dei Customer Journey Analytics e tra dispositivi

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=it) e [Analisi multidispositivo](/help/components/cda/overview.md) consente agli utenti di includere identificatori durevoli, come accessi con hash, oltre ai cookie. Questo consente di comprendere il percorso del cliente tra dispositivi e, nel caso di Customer Journey Analytics, tra canali online e offline:

* **Customer Journey Analytics** è basato su Adobe Experience Platform e offre la flessibilità di combinare dati online e offline in Analysis Workspace, in base a qualsiasi ID cliente comune. Puoi specificare l’ID da utilizzare per una determinata analisi ed esaminare i dati in Analysis Workspace. I clienti di Analytics Select, Prime e Ultimate possono acquistare questo prodotto aggiuntivo.

* **Analisi multidispositivo** è un miglioramento della versione tradizionale di Adobe Analytics che consente ai clienti di utilizzare identificatori alternativi per i visitatori. Questa funzionalità consente di passare da una visualizzazione incentrata sul dispositivo a una visualizzazione incentrata sulla persona. Analisi multidispositivo è disponibile per i clienti Analytics Ultimate.

## Raccolta di dati lato server

La raccolta lato server offre la flessibilità di fornire un proprio identificatore anziché utilizzare i meccanismi del browser per l’impostazione dei cookie.

Puoi inviare dati al server di Analytics utilizzando [API di inserimento dati](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) o [API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). L’API di inserimento dati in blocco è consigliata per nuove implementazioni lato server. Per un confronto tra le due API, vedi &quot;[Quale strumento Adobe Analytics usare](/help/analyze/get-started/which-analytics-tool.md).&quot;

## ID dispositivo di prima parte (FPID) con SDK per web

Con Adobe Experience Platform Web SDK puoi impostare e gestire identificatori dispositivo personalizzati anziché ID Experience Cloud (ECID) generati dagli Adobi. Questi sono denominati ID dispositivo di prime parti (FPID). Puoi trovare ulteriori informazioni [qui](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=it).

## Ulteriori informazioni

Per i passi pratici che la tua azienda può compiere per effettuare la transizione dai cookie di terze parti, vedi [Acquisisci e mantieni i clienti in un mondo senza cookie con Adobe](https://business.adobe.com/solutions/cookieless.html) e in profondità [Oltre al cookie di terze parti: Guida completa a un mondo senza cookie di terze parti](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
>
>[Cookie di Adobe Analytics e browser](cookies.md)
