---
title: Opzioni per attenuare l’effetto delle limitazioni dei cookie del browser
description: Scopri come attenuare l’effetto delle limitazioni dei cookie del browser per migliorare la raccolta dei dati per Adobe Analytics.
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 5%

---


# Opzioni per attenuare l’effetto delle limitazioni dei cookie del browser

Questo documento spiega come preservare l’identificazione persistente dei visitatori tra proprietà e soluzioni man mano che i principali browser implementano misure di prevenzione del tracciamento per i cookie.

Adobe Analytics si basa sui cookie di prime parti per registrare l’attività in loco di un visitatore. Analytics si basa anche sui cookie di terze parti per comprendere l’attività off-site di un visitatore, ad esempio l’attività su altri domini di cui sei titolare. I cookie di terze parti sono bloccati su molti browser e non saranno disponibili per la maggior parte con la prossima rimozione del supporto da parte di Chrome (attualmente pianificata per il 2022). I cookie di prime parti sono consentiti su tutti i browser, ma hanno una scadenza limitata su Safari e altri browser secondo le misure di [prevenzione del tracciamento ITP](https://webkit.org/tracking-prevention) di Apple. Per ulteriori informazioni sulle limitazioni attuali dei cookie del browser, consulta &quot;[Cookie di Adobe Analytics e del browser](cookies.md).

Queste limitazioni del browser riflettono una più ampia transizione dal tracciamento anonimo di terze parti verso la condivisione esplicita di informazioni tra utenti e marchi di cui si fidano. Per supportare questa mossa, Adobe offre ai clienti dei modi di integrare i cookie tradizionali includendo identificatori durevoli raccolti tramite le loro relazioni di prima parte.

## Analisi dei Customer Journey Analytics e tra dispositivi

[Adobe Customer Percorso ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) Analytics e utenti di  [Cross-Device ](/help/components/cda/overview.md) Analytics per includere identificatori durevoli, come accessi con hash, oltre ai cookie:

* **Percorso di clienti** Analytics consente l’analisi cross-channel in Analysis Workspace tramite un’integrazione con Adobe Experience Platform. consolida i dati dei clienti online e offline disponibili al momento della query in Experience Platform, utilizzando qualsiasi ID.

* **Analisi multidispositivo** consente di identificare in che modo i dispositivi digitali si associano alle persone e uniscono il percorso di utenti in qualsiasi ID utilizzando il servizio Adobe Experience Platform Identity. Utilizza il grafico Adobe Experience Cloud Device Co-op, un grafico a dispositivi privato o unione basata sui campi.

## Raccolta di dati lato server

La raccolta lato server offre la flessibilità di fornire un proprio identificatore anziché utilizzare i meccanismi del browser per l’impostazione dei cookie.

Puoi importare dati lato server in Analytics utilizzando l’ [API di inserimento dati](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) o l’ [API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). Per un confronto tra le due API, consulta &quot;[Quale strumento Adobe Analytics usare](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)&quot;.

## Ulteriori informazioni

Per i passaggi pratici che la tua azienda può compiere per effettuare la transizione dai cookie di terze parti, consulta &quot;[Acquisire e mantenere i clienti in un mondo senza cookie con Adobe](https://business.adobe.com/solutions/cookieless.html)&quot; e l&#39;approfondimento &quot;[Pensare oltre il cookie di terze parti: La guida completa a un mondo senza cookie di terze parti](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
>
>[Cookie di Adobe Analytics e browser](cookies.md)
