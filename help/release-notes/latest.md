---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
hold: true
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2: id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 6dd4e1e089cf72c03c8d2fd43ac87e919efa0602
workflow-type: tm+mt
source-wordcount: 1061
ht-degree: 49%

---

# Note sulla versione corrente di Adobe Analytics (settembre 2026)

**Ultimo aggiornamento**: 8 settembre 2026

Queste note sulla versione coprono il periodo di rilascio di settembre 2026. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ---- |
| **Limitare i segmenti all&#39;intervallo di date del rapporto**<br/> I dati in un rapporto di Workspace possono estendersi oltre l&#39;intervallo di date del rapporto quando un segmento include componenti per l&#39;intervallo di date.<p>È ora disponibile una nuova opzione che consente di limitare i risultati all’intervallo di date del rapporto indipendentemente da qualsiasi componente data incluso nel segmento.</p><p>Questa opzione è disponibile quando crei o modifichi un segmento il cui contenitore di livello superiore è Visitatore.</p><p>Per ulteriori informazioni, vedere [Generare segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md#components).</p> | 26 agosto 2026 | 9 settembre 2026 |
| **Aggiornamenti del rilevamento bot**<br/> Quando si utilizza la raccolta dati di Edge con il Web SDK, sono disponibili i seguenti aggiornamenti del rilevamento bot:<ul><li>Ora puoi creare regole di rilevamento bot per identificare le eccezioni nel traffico che altrimenti verrebbero trattate come generate da bot. Le regole esistenti e future continueranno a utilizzare l’impostazione predefinita contrassegnare il traffico corrispondente come generato da bot.</li><li>Le regole bot personalizzate ora vengono eseguite prima delle regole di rilevamento dei bot IAB. Questa modifica non influisce sui punteggi dei bot, ma i nomi delle regole bot associati a un evento possono cambiare.</li></ul><p>Nota: questo aggiornamento si applica solo alle implementazioni di raccolta dati di Edge che utilizzano il Web SDK. Non si applica alle librerie precedenti come AppMeasurement.</p><p>Il collegamento alla documentazione seguirà a breve.</p> | | Inizio settembre 2026 |
| **Aggiornamenti API per i set di classificazione**<br/> La documentazione API per i set di classificazione ora include informazioni aggiornate sull&#39;endpoint e sui parametri per la configurazione delle richieste API per i set di classificazione.<p>Per ulteriori informazioni, consulta la [Guida dell&#39;endpoint Classificazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/).</p> | 5 settembre 2026 | 30 settembre 2026 |
| **Indicazioni sulla codifica di itemId data nelle guide al report API 2.0**<br/> Le guide al report con tendenze data API di Adobe Analytics 2.0 ora includono nuove sezioni che spiegano come vengono codificati i parametri e i valori data `itemId`. Questo consente di configurare e migrare ai servizi API 2.0 dalle API 1.4, ora obsolete.<p>Per ulteriori informazioni, vedere la [Guida ai report KPI](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/kpi) e la [Guida ai report avanzati](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced).</p> | 5 settembre 2026 | 30 settembre 2026 |

### Correzioni in Adobe Analytics

**Activity Map**: AN-488579, AN-487247
**Analysis Workspace**: AN-487374, AN-487119, AN-468907, AN-468810, AN-468363, AN-468096, AN-467414, AN-466986, AN-466982, AN-465073, AN-463571, AN-462373
**Classificazioni**: AN-490825, AN-490802, AN-490549, AN-490472, AN-487782, AN-487286, AN-486531, AN-478859, AN-469929, AN-469033, AN-468944, AN-468827, AN-468592, AN-468326, AN-467115, AN-466995, AN-465636, AN-465616, AN-465380, AN-464911 464338 463677 462729 462577 461040 459316, AN-, AN-, AN-, AN-, AN-, AN-, AN-
**Feed dati e Data Warehouse**: AN-487624, AN-487287, AN-479923, AN-479166, AN-479109, AN-468483
**Migrazione**:
**Esportazioni**: AN-467131
**Report Builder**: AN-487486, AN-478944, AN-470036, AN-468589, AN-468436, AN-456747, AN-456700, AN-442695
**Generazione rapporti**: AN-468621, AN-465383, AN-463924
**Suite di rapporti**: AN-468484, AN-468460, AN-465385
**Rapporti pianificati**:
**Segmentazione**: AN-486561
**Altro**: AN-488549, AN-467426, AN-465265, AN-464645, AN-459714, AN-459323, AN-454514

### Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Report Builder legacy** | 18 giugno 2025 | Il componente aggiuntivo precedente di Report Builder sarà ritirato a giugno 2026. Tutti gli utenti devono iniziare a eseguire l’aggiornamento delle cartelle di lavoro precedenti al [nuovo Report Builder](/help/analyze/report-builder/rb-overview.md). Il nuovo Report Builder è disponibile sia per i clienti di Adobe Analytics che di Customer Journey Analytics. Offre [quasi le stesse funzioni](/help/analyze/report-builder/convert-workbooks.md#unsupported), oltre a numerose nuove funzioni utili e miglioramenti dell’interfaccia utente. Per agevolare il processo di aggiornamento, il nuovo Report Builder include una facile funzione di conversione della cartella di lavoro. Il nuovo Report Builder è disponibile solo come componente aggiuntivo tramite Microsoft Store. Molte organizzazioni richiedono un processo di approvazione interno prima di rendere il componente aggiuntivo disponibile per gli utenti. Attendi il tempo necessario per questo processo e inizia a cooperare subito con la tua organizzazione per assicurarti di disporre del tempo sufficiente per eseguire l’aggiornamento delle cartelle di lavoro prima della data di fine del ciclo di vita. |
| **API di Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **31 agosto 2026**, i seguenti servizi API legacy di Analytics hanno raggiunto la fine del ciclo di vita e sono stati chiusi e le integrazioni create utilizzando questi servizi non funzioneranno più:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, consulta le [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).

## Funzioni posticipate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Servizi multimediali in streaming: supporto dei dati di pianificazione** <br/>Ora puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data). | 29 ottobre 2025 | Da definire<p>(Originariamente previsto per il 29 ottobre 2025)</p> |


>[!MORELIKETHIS]
>
>* [Note sulle versioni precedenti per il 2026](/help/release-notes/2026.md)
>* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
>* [Note sulla versione dei servizi multimediali in streaming ](https://experienceleague.adobe.com/it/docs/media-analytics/using/release-notes/release-notes)
>* Ultimi aggiornamenti sulle versioni dei [prodotti Adobe CX Enterprise](https://business.adobe.com/products/adobe-experience-cloud-products.html)

