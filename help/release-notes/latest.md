---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c156ab154bc34ffb653c9ad5509c409f475db39d
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 57%

---

# Note sulla versione corrente di Adobe Analytics (febbraio 2023)

**Ultimo aggiornamento**: 7 marzo 2023

I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate in Adobe Analytics {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Interfaccia utente aggiornata per le etichette Privacy dei dati** | L’interfaccia aggiornata semplifica il processo di creazione, gestione e modifica delle etichette sulla privacy dei dati per i componenti della suite di rapporti. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | N/D | 8 febbraio 2023 |
| **Nascondere gli intervalli di date di confronto nelle scorecard per dispositivi mobili** | Con le scorecard per dispositivi mobili, puoi attivare/disattivare **[!UICONTROL Include comparison dates]** per visualizzare o nascondere le date di confronto. | N/D | 8 febbraio 2023 |
| **Aggiornamenti del calendario in Workspace** | <ul><li>Date del pannello di ancoraggio: è possibile correlare i componenti dell’intervallo di date al calendario del pannello. [Ulteriori informazioni](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>Aggiornamenti dello stile del calendario: gli stili del calendario nell’interfaccia utente sono stati aggiornati per presentare un flusso di lavoro più coerente e facile da usare.</li><li>Aggiornamenti della formula del calendario: se si utilizzano date relative, tutte le formule del calendario rispecchieranno l&#39;inizio dell&#39;intervallo di date del pannello. [Ulteriori informazioni](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | N/D | 8 febbraio 2023 |
| **Aggiornamenti dell’intervallo di date del pannello** | In Workspace sono stati aggiunti i seguenti miglioramenti:<ul><li>A partire dalla versione di febbraio, le anteprime dei dati e dei componenti saranno basate sull’intervallo di date del pannello e non sugli ultimi 90 giorni. </li><li>Tutti gli elementi dimensionali visualizzati saranno disponibili in base all’intervallo di date del pannello.</li><li>Tutte le anteprime di date nel segmento e i generatori di metriche calcolate saranno basati sull’intervallo di date del pannello (a meno che non siano accessibili dai gestori dei componenti che non hanno un pannello associato, saranno comunque basati sugli ultimi 90 giorni).</li><li>Tutte le anteprime dei dati mostreranno dati o componenti in base all’intervallo di date del pannello.</li></ul> | N/D | 8 febbraio 2023 |
| **Filtro riga/colonna per lo streaming del connettore di origine di Adobe Analytics** | Il connettore di origine di Analytics in Adobe Experience Platform ora consente di filtrare i dati di Analytics che vengono utilizzati per popolare i profili nel [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it). Il filtro a livello di riga consente di ridurre il numero di eventi associati ai profili. Il filtro a livello di colonna consente di ridurre la rilevanza degli eventi stessi, consentendoti in tal modo di ottimizzare l’utiizzo delle adesioni al profilo. Questo filtro si applica solo ai dati inviati al Profilo cliente in tempo reale e al [servizio Identity](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it). **Il filtro non influisce sui dati inviati al Data Lake per l’utilizzo in applicazioni come Customer Journey Analytics**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it#filtering-for-profile) | N/D | Riprogrammato per il 29 marzo 2023 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

-302282; AN-303127; AN-303541; AN-303550; AN-305282; AN-306504; AN-307351; AN-307496; AN-307530; AN-307947; AN-308497; AN-; AN-308610; AN-308777; AN-308994; AN-309143; AN-309404; AN-309414; AN-309445; AN-309575; AN-309630; AN-309658; AN-309690; AN-309742; AN-309861; AN-309967; AN-309973; AN-310059; AN-310132; AN-310168; AN-310238; AN-310241; AN-310301; AN-310318; AN-310324; AN-310335; AN-310338; AN-310460; AN-310500; AN-310684; AN-310690; AN-311010; AN-311022; AN-311043; AN-311125; AN-311250; AN-311370; AN-311458;

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Aggiornamento delle ricerche dei dispositivi a causa di suggerimenti client Google** | 27 febbraio 2023 | L’utilizzo degli hint client, pianificati per il 16 febbraio 2023, è stato posticipato al fine di garantire meglio la qualità delle ricerche del dispositivo tramite hint. Abbiamo completato la prima fase della versione per il supporto di Client Hints il 27 febbraio 2023 e la seconda e ultima fase giovedì 2 marzo 2023. [Ulteriori informazioni](/help/technotes/client-hints.md) |
| **Disponibilità del connettore di origine di Analytics** | 15 febbraio 2023 | Il 28 febbraio 2023, il connettore di origine di Analytics è stato reso disponibile nel nuovo data center Adobe Experience Platform in Canada. |
| **Migrazione automatica all’architettura del set di classificazione** | 8 febbraio 2023 | Nei prossimi mesi, Adobe pianifica di migrare tutte le classificazioni in tutte le organizzazioni all’architettura di classificazione più recente. Si stima che gli ultimi clienti a migrare avverranno a maggio 2023. Non è richiesta alcuna azione da parte del cliente e non è previsto alcun tempo di inattività. Questa nuova architettura offre numerosi vantaggi, tra cui:<ul><li>Tempo di elaborazione notevolmente ridotto (72 ore → 24 ore)</li><li>La possibilità di utilizzare [Set di classificazione](/help/components/classifications/sets/overview.md) UI</li><li>L’opzione per utilizzare in futuro i dati di classificazione in Adobe Experience Platform tramite [Connettore di origine di Adobe Analytics per i dati di classificazione](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Tieni presente le seguenti modifiche che possono potenzialmente influire sul flusso di lavoro dell’organizzazione:<ul><li>Quando si utilizza il browser o l’importazione FTP, &quot;[!UICONTROL Overwrite on conflict]&#39; è sempre abilitato.</li><li>Quando si utilizza il browser o l’importazione FTP, l’opzione per esportare immediatamente dopo l’importazione non è più supportata.</li><li>API di Analytics 2.0 `GetDimensions` l’endpoint ora restituisce identificatori stringa per le classificazioni anziché identificatori numerici. È comunque possibile utilizzare gli identificatori numerici, ma Adobe consiglia di utilizzare i nuovi identificatori stringa laddove possibile. Gli identificatori numerici possono essere recuperati utilizzando `?expansion=hidden` parametro stringa query.</li></ul>Se desideri una pianificazione di migrazione più specifica per la tua organizzazione o se hai domande/dubbi su questa migrazione, contatta l’Assistenza clienti di Adobe. [Ulteriori informazioni](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Fine del ciclo di vita per [!DNL Reports & Analytics]** | 7 marzo 2023 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita.<p>Il 31 dicembre 2023 termineremo molte delle funzioni di Reports &amp; Analytics associate, tra cui, a titolo esemplificativo: rapporti pianificati, estratti di dati e rapporti DL. Dopo il 31 dicembre 2023, tutti i rapporti pianificati non verranno più inviati. In entrata **Aprile 2023**, tutti i rapporti la cui scadenza era prevista dopo il 31 dicembre 2023 verranno automaticamente aggiornati e torneranno a scadere il 31 dicembre 2023. Inoltre, non è più possibile pianificare rapporti futuri oltre il 31 dicembre 2023. |
| **Fine del ciclo di vita di alcune funzioni di Reports &amp; Analytics e pianificazione del Report Builder** | 9 febbraio 2023 | Le seguenti funzionalità di pianificazione sono state terminate il 31 gennaio 2023:<ul><li>Opzione &quot;termina dopo x occorrenze&quot; per le attività orarie nel Report Builder</li><li>Possibilità di pianificare nuovi rapporti e scaricare estratti di dati in Reports and Analytics</li></ul><p>**Nota**: queste funzioni sono state originariamente terminate ad aprile 2022, ma la modifica è stata annullata. Abbiamo inoltre inviato una notifica che segnala che queste funzioni sono state temporaneamente ripristinate e che verranno terminate nuovamente il 31 gennaio 2023. |
| **Fine del ciclo di vita della [!UICONTROL Publishing Lists] caratteristica** | 29 settembre 2022 | Come parte della fine del ciclo di vita di Reports &amp; Analytics, gli elenchi di pubblicazione sono destinati a raggiungere la fine del ciclo di vita a **dicembre 2023**. Non sarà possibile creare nuovi elenchi di pubblicazione o accedere a quelli esistenti per inviare o pianificare progetti di Analysis Workspace. |
| **Fine del ciclo di vita per Data Workbench** | 14 settembre 2022 | Adobe intende terminare il ciclo di vita di Data Workbench a partire dal **31 dicembre 2023**. Vedi [Annuncio della fine del ciclo di vita di Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=it) per i dettagli. Per qualsiasi domanda, contatta il team del tuo account di Adobe. |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.23.0), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
