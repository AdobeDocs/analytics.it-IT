---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: feb6942a54f61850ce11e08008b5694c53436e6d
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 38%

---

# Note sulla versione corrente di Adobe Analytics (febbraio 2023)

**Ultimo aggiornamento**: 17 febbraio 2023

I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate in Adobe Analytics

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Interfaccia utente aggiornata per le etichette Privacy dei dati** | L’interfaccia aggiornata semplifica il processo di creazione, gestione e modifica delle etichette per la privacy dei dati per i componenti della suite di rapporti. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/data-labels/gdpr-setup-reportsuite.html?lang=en) | N/D | 8 febbraio 2023 |
| **Nascondere intervalli di date di confronto nelle scorecard per dispositivi mobili** | Con le scorecard per dispositivi mobili, puoi attivare/disattivare **[!UICONTROL Include comparison dates]** impostazione per visualizzare o nascondere le date del confronto. | N/D | 8 febbraio 2023 |
| **Aggiornamenti del calendario in Workspace** | <ul><li>Date del pannello di ancoraggio: Puoi rendere i componenti dell’intervallo di date relativi al calendario del pannello. [Ulteriori informazioni](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#relative-panel-dates)</li><li>Aggiornamenti dello stile del calendario: Gli stili del calendario in tutta l’interfaccia utente sono stati aggiornati per presentare un flusso di lavoro più coerente e facile da usare.</li><li>Aggiornamenti della formula del calendario: Se si utilizzano date relative, tutte le formule del calendario rifletteranno l&#39;inizio dell&#39;intervallo di date del pannello. [Ulteriori informazioni](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md#formula-relative-dates)</li></ul> | N/D | 8 febbraio 2023 |
| **Aggiornamenti degli intervalli di date del pannello** | In Workspace sono stati aggiunti i seguenti miglioramenti:<ul><li>A partire dalla versione di febbraio, le anteprime dei dati e dei componenti saranno basate sull’intervallo di date del pannello e non sugli ultimi 90 giorni. </li><li>Tutti i componenti elencati nella barra a sinistra saranno disponibili in base all’intervallo di date del pannello.</li><li>Tutte le anteprime di date nel segmento e i generatori di metriche calcolate saranno basate sull’intervallo di date del pannello (a meno che non siano accessibili dai gestori dei componenti, che non hanno un pannello associato, saranno comunque basate sugli ultimi 90 giorni).</li><li>Tutte le anteprime dei dati visualizzeranno dati o componenti in base all’intervallo di date del pannello.</li></ul> | N/D | 8 febbraio 2023 |
| **Filtro riga/colonna per lo streaming del connettore sorgente Adobe Analytics** | Il connettore di origine di Analytics in Adobe Experience Platform ora consente di filtrare i dati di Analytics che vengono utilizzati per popolare i profili in [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it). Il filtro a livello di riga consente di ridurre il numero di eventi associati ai profili. Il filtro a livello di colonna consente di ridurre la ricchezza degli eventi stessi, consentendoti in tal modo di ottimizzare l’uso delle adesioni al profilo. Questo filtro si applica solo ai dati inviati a Profilo cliente in tempo reale e [Servizio identità](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it). **Il filtro non influisce sui dati inviati a Data Lake per l&#39;utilizzo in applicazioni come Customer Journey Analytics**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en#filtering-for-profile) | N/D | 22 febbraio 2023 |

{style=&quot;table-layout:auto&quot;}

## Correzioni in Adobe Analytics

-302282; AN-303127; AN-303541; AN-303550; AN-305282; AN-306504; AN-307351; AN-307496; AN-307530; AN-307947; AN-308497; AN-; AN-308610; AN-308777; AN-308994; AN-309143; AN-309404; AN-309414; AN-309445; AN-309575; AN-309630; AN-309658; AN-309690; AN-309742; AN-309861; AN-309967; AN-309973; AN-310059; AN-310132; AN-310168; AN-310238; AN-310241; AN-310301; AN-310318; AN-310324; AN-310335; AN-310338; AN-310460; AN-310500; AN-310684; AN-310690; AN-311010; AN-311022; AN-311043; AN-311125; AN-311250; AN-311370; AN-311458;

## Avvisi importanti per gli amministratori di Adobe Analytics

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Aggiornamento delle ricerche dei dispositivi a causa di suggerimenti client Google** | 17 febbraio 2023 | **L’utilizzo di suggerimenti client, pianificato per il 16 febbraio 2023, è stato posticipato al fine di garantire una migliore qualità delle ricerche dei dispositivi tramite suggerimenti. Comunicheremo tra breve una nuova data di rollout.** [Ulteriori informazioni](/help/technotes/client-hints.md) |
| **Disponibilità del connettore di origine di Analytics** | 15 febbraio 2023 | Il 28 febbraio 2023, il Connettore sorgente di Analytics sarà reso disponibile nel nuovo data center Adobe Experience Platform situato in Canada. |
| **Migrazione automatica all’architettura del set di classificazioni** | 8 febbraio 2023 | Nei prossimi mesi, Adobe prevede di migrare tutte le classificazioni tra tutte le organizzazioni all’architettura di classificazione più recente. Si stima che gli ultimi clienti che hanno effettuato la migrazione avranno luogo a maggio 2023. Non è richiesta alcuna azione da parte del cliente e non è previsto alcun tempo di inattività. Questa nuova architettura offre numerosi vantaggi, tra cui:<ul><li>Tempi di elaborazione significativamente ridotti (72 ore → 24 ore)</li><li>La possibilità di utilizzare [Set di classificazioni](/help/components/classifications/sets/overview.md) Interfaccia</li><li>L’opzione per utilizzare i dati di classificazione in Adobe Experience Platform in futuro tramite [Connettore sorgente Adobe Analytics per i dati di classificazione](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)</li></ul>Tieni presente le seguenti modifiche che possono influenzare potenzialmente il flusso di lavoro della tua organizzazione:<ul><li>Quando utilizzi il browser o l’importazione FTP, &quot;[!UICONTROL Overwrite on conflict]&#39; è sempre abilitato.</li><li>Quando utilizzi il browser o l’importazione FTP, l’opzione per esportare immediatamente dopo l’importazione non è più supportata.</li><li>API di Analytics 2.0 `GetDimensions` endpoint restituisce ora identificatori stringa per le classificazioni anziché identificatori numerici. È ancora possibile utilizzare gli identificatori numerici, ma in Adobe si consiglia di utilizzare, ove possibile, i nuovi identificatori stringa. Gli identificatori numerici possono essere recuperati utilizzando `?expansion=hidden` parametro della stringa query.</li></ul>Contatta l’Assistenza clienti di Adobe se desideri una pianificazione della migrazione più specifica per la tua organizzazione o se hai domande o dubbi su questa migrazione. [Ulteriori informazioni](/help/components/classifications/sets/overview.md) |

{style=&quot;table-layout:auto&quot;}

## Avvisi di fine del ciclo di vita (EOL)

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Fine del ciclo di vita di alcune funzionalità di Reports &amp; Analytics e di pianificazione dei Report Builder** | 9 febbraio 2023 | Le seguenti funzionalità di pianificazione sono scadute il 31 gennaio 2023:<ul><li>Opzione &quot;fine dopo x occorrenze&quot; per le attività orarie nel Report Builder</li><li>Possibilità di pianificare nuovi report e scaricare estratti di dati in Reports and Analytics</li></ul><p>**Nota**: Queste funzioni sono state originariamente interrotte nell’aprile 2022, ma sono state ripristinate. Abbiamo inoltre inviato una notifica del ripristino temporaneo di queste funzioni e della loro reterminazione il 31 gennaio 2023. |
| **Fine del ciclo di vita della [!UICONTROL Publishing Lists] caratteristica** | 29 settembre 2022 | Come parte della fine del ciclo di vita di Reports &amp; Analytics, gli elenchi di pubblicazione sono destinati a raggiungere la fine del ciclo di vita a **dicembre 2023**. Non sarà possibile creare nuovi elenchi di pubblicazione o accedere a quelli esistenti per inviare o pianificare progetti di Analysis Workspace. |
| **Fine del ciclo di vita per Data Workbench** | 14 settembre 2022 | Adobe intende terminare il ciclo di vita di Data Workbench a partire dal **31 dicembre 2023**. Vedi [Annuncio della fine del ciclo di vita di Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=it) per i dettagli. Per qualsiasi domanda, contatta l’Adobe Account Manager della tua organizzazione. |
| **Fine del ciclo di vita per [!DNL Reports & Analytics]** | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.23.0), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
