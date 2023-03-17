---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 5739b9bd20d63c51343127832778c4c3836993b3
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 88%

---

# Note sulla versione corrente di Adobe Analytics (marzo 2023)

**Ultimo aggiornamento**: 10 marzo 2023

I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate in Adobe Analytics {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Dizionario dati in Analysis Workspace** | Il dizionario dati consente sia agli utenti che agli amministratori di tenere traccia dei componenti (dimensioni, metriche) nel proprio ambiente Analytics, nonché di gestirli e comprenderli meglio. [Ulteriori informazioni](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 15 marzo 2023 | 22 marzo 2023 |
| **Significato dei dati nei dashboard per dispositivi mobili** | Il signifcato dei dati consente di aggiungere più visualizzazioni di dettagli personalizzabili alle tessere nei progetti di scorecard per dispositivi mobili. Utilizza il significato dei dati per approfondire i driver chiave, le metriche correlate e i diversi passaggi del percorso del cliente. Puoi scorrere facilmente queste visualizzazioni per comprendere il significato complessivo dietro le metriche chiave. [Ulteriori informazioni](/help/analyze/mobile-app/create-scorecard.md#create-data-story) | N/D | 8 marzo 2023 |
| **Date di scadenza per il progetto programmato** | È possibile impostare date di scadenza massime per i progetti programmati fino a un anno, indipendentemente dalla frequenza di programmazione. | N/D | 8 marzo 2023 |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** - Accesso solo alle Private Beta | <p>Ora puoi condividere collegamenti di sola lettura ai progetti Analysis Workspace con persone che non hanno accesso ad Adobe Analytics. Puoi condividere i collegamenti dei progetti con persone esterne all’organizzazione o con persone all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>Per iscriverti alle Private Beta, contatta il team del tuo account Adobe.</p> | 15 marzo 2023 (Private Beta) | Aprile 2023 |
| **Aggiornamenti dell’intervallo di date del pannello** | In Workspace sono stati aggiunti i seguenti miglioramenti:<ul><li>A partire dalla versione di febbraio, gli elementi dimensionali e le anteprime dei dati si basano sull’intervallo di date del pannello e non sugli ultimi 90 giorni. </li><li>Tutti gli elementi dimensionali elencati si basano sui dati all’interno dell’intervallo di date del pannello. Se un elemento dimensionale contiene dati al di fuori dell’intervallo di date, puoi visualizzare dati aggiuntivi oltre l’intervallo di date nella parte inferiore dell’elenco.</li><li>I Dimension privi di dati possono essere visualizzati nella barra a sinistra. Fai clic su mostra altre opzioni per visualizzare gli elementi dimensionali con dati al di fuori dell’intervallo date del pannello.</li><li>Le anteprime dei dati nei generatori di segmenti e metriche calcolate si basano sull’intervallo di date del pannello, a meno che non siano accessibili dai gestori dei componenti, che non hanno un pannello associato e sono ancora basate sugli ultimi 90 giorni.</li><li>Le anteprime dei dati visualizzano dati o componenti in base all’intervallo di date del pannello.</li></ul> | N/D | 8 febbraio 2023 |

## Correzioni in Adobe Analytics

AN-308177; AN-308727; AN-308846; AN-309591; AN-310614; AN-311544; AN-311570; AN-311665; AN-311948; AN-312108; AN-312114; AN-312142; AN-312143; AN-312389; AN-312391; AN-312431; AN-312453; AN-312454; AN-312458; AN-312503; AN-312533; AN-312682; AN-312698; AN-312714; AN-312738; AN-312807; AN-312829; AN-312849; AN-312875; AN-312980; AN-312997; AN-313059; AN-313077; AN-313110; AN-313195; AN-313196; AN-313258; AN-313554; AN-313580; AN-313702; AN-313820; AN-313844; AN-313859; AN-313879; AN-314273

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Aggiornamento delle ricerche dei dispositivi a causa di suggerimenti client Google** | 27 febbraio 2023 | L’utilizzo degli hint client, pianificati per il 16 febbraio 2023, è stato posticipato al fine di garantire al meglio la qualità delle ricerche del dispositivo tramite hint. Si è proceduto con la prima fase della versione per il supporto degli hint client il 27 febbraio 2023. La seconda e ultima fase del rilascio è stata completata giovedì 2 marzo 2023. [Ulteriori informazioni](/help/technotes/client-hints.md) |
| **Disponibilità del connettore di origine di Analytics** | 15 febbraio 2023 | Il 28 febbraio 2023, il connettore di origine di Analytics è stato reso disponibile nel nuovo data center di Adobe Experience Platform in Canada. |
| **Migrazione automatica all’architettura del set di classificazione** | 8 febbraio 2023 | Nei prossimi mesi, Adobe pianifica di migrare tutte le classificazioni in tutte le organizzazioni all’architettura di classificazione più recente. Si stima che la migrazione degli ultimi clienti avverrà a maggio 2023. Non è richiesta alcuna azione da parte del cliente e non è previsto alcun tempo di inattività. Questa nuova architettura offre numerosi vantaggi, tra cui:<ul><li>Tempo di elaborazione notevolmente ridotto (72 ore → 24 ore)</li><li>Possibilità di utilizzare l’interfaccia dei [set di classificazione](/help/components/classifications/sets/overview.md)</li><li>Opzione per utilizzare in futuro i dati di classificazione in Adobe Experience Platform tramite il [Connettore di origine di Adobe Analytics per i dati di classificazione](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=it)</li></ul>Nota le seguenti modifiche che possono potenzialmente influire sul flusso di lavoro dell’organizzazione:<ul><li>Quando si utilizza il browser o l’importazione FTP, “[!UICONTROL Overwrite on conflict]” è sempre abilitato.</li><li>Quando si utilizza il browser o l’importazione FTP, l’opzione per esportare immediatamente dopo l’importazione non è più supportata.</li><li>L’endpoint `GetDimensions` dell’API di Analytics 2.0 ora restituisce identificatori stringa per le classificazioni anziché identificatori numerici. È comunque possibile utilizzare gli identificatori numerici, ma Adobe consiglia di utilizzare i nuovi identificatori stringa laddove possibile. Gli identificatori numerici possono essere recuperati utilizzando il parametro `?expansion=hidden` della stringa di query.</li></ul>Se desideri una pianificazione di migrazione più specifica per la tua organizzazione o se hai domande/dubbi su questa migrazione, contatta l’assistenza clienti di Adobe. [Ulteriori informazioni](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Fine del ciclo di vita per[!DNL Reports & Analytics]** | 7 marzo 2023 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita.<p>Il 31 dicembre 2023 termineremo molte delle funzioni associate a Reports &amp; Analytics, tra cui, a titolo esemplificativo: rapporti pianificati, estratti di dati e rapporti DL. Dopo il 31 dicembre 2023, tutti i rapporti pianificati non verranno più inviati. In **Aprile 2023**, tutti i rapporti la cui scadenza era prevista dopo il 31 dicembre 2023 verranno automaticamente aggiornati con scadenza il 31 dicembre 2023. Inoltre, non è più possibile pianificare rapporti futuri oltre il 31 dicembre 2023. |
| **Fine del ciclo di vita della metrica [!UICONTROL People]** | 9 marzo 2023 | Con l’obsolescenza di [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html?lang=it), la metrica Persone relativa a Device Co-op non è più rilevante. L’8 maggio 2023 verrà rimossa la funzione [!UICONTROL People] metrica. A questo punto, i dati verranno reindirizzati alla metrica [!UICONTROL Unique Visitor] per evitare che progetti, segmenti e metriche calcolate si interrompano.<p>**Nota**: la metrica [[!UICONTROL People] associata a Cross-Device Analytics](/help/components/metrics/people.md) non è interessata da questo annuncio. |
| **Fine del ciclo di vita della [!UICONTROL Publishing Lists] caratteristica** | 29 settembre 2022 | Come parte della fine del ciclo di vita di Reports &amp; Analytics, gli [!UICONTROL Publishing Lists] sono destinati a raggiungere la fine del ciclo di vita a **dicembre 2023**. Non sarà possibile creare nuovi [!UICONTROL Publishing Lists] o accedere a quelli esistenti per inviare o pianificare progetti di [!UICONTROL Analysis Workspace]. |
| **Fine del ciclo di vita per Data Workbench** | 14 settembre 2022 | Adobe intende terminare il ciclo di vita di Data Workbench a partire dal **31 dicembre 2023**. Vedi [Annuncio della fine del ciclo di vita di Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=it) per i dettagli. Per qualsiasi domanda, contatta l’Adobe Account Manager della tua organizzazione. |
| **Fine del ciclo di vita per [!DNL Reports & Analytics]** | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.23.0), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
