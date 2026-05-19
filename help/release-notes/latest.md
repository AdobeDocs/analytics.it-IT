---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 2be38df3df510c4e460497be8c085ed2a26b4760
workflow-type: tm+mt
source-wordcount: 1365
ht-degree: 60%

---

# Note sulla versione corrente di Adobe Analytics (maggio 2026)

**Ultimo aggiornamento**: 13 maggio 2026

Queste note sulla versione coprono il periodo di rilascio di maggio 2026. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ---- |
| **Server MCP per Adobe Analytics** <br/>I server MCP (Model Context Protocol) di Analytics consentono di collegare un client MCP supportato ad Adobe Analytics. Una volta connesso, il client MCP può richiamare strumenti specifici per il prodotto per recuperare dati, eseguire query o eseguire operazioni supportate come parte di un flusso di lavoro LLM o agente. Per ulteriori informazioni, vedere [Server MCP di Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Se hai utilizzato questi server MCP durante il periodo beta, tieni presente che esistono URL diversi tra gli endpoint beta e di produzione. Assicurati che tutti i flussi di lavoro agenti creati durante il periodo beta vengano aggiornati per utilizzare gli endpoint di produzione prima del 31 maggio.</p> | | 5 maggio 2026 |
| **area di lavoro Percorsi in Adobe Analytics** <br/>area di lavoro Percorsi è una visualizzazione in Analysis Workspace che consente di ottenere informazioni approfondite su un percorso di utenti definito analizzando il modo in cui le persone procedono attraverso il percorso o ne escono. Consente di creare un grafico flessibile di nodi e frecce che rappresentano qualsiasi combinazione di eventi, elementi dimensionali e segmenti inclusi nel percorso. I dati vengono aggiornati quando si trascinano i nodi nell’area di lavoro o si riorganizzano gli eventi e le condizioni del percorso.<p>In precedenza, l’area di lavoro percorso era disponibile solo per Customer Journey Analytics.</p><p>Per ulteriori informazioni sull&#39;area di lavoro Percorso in Adobe Analytics, vedere [Panoramica sull&#39;area di lavoro Percorso](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md). </p><p>Per informazioni su come creare una visualizzazione dell&#39;area di lavoro del Percorso in Adobe Analytics, consulta [Configurare l&#39;area di lavoro del Percorso](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).</p> | 18 maggio 2026 | 5 giugno 2026 |
| **Guida alla generazione di rapporti API per i modelli di attribuzione** <br/>È disponibile una nuova Guida alla generazione di rapporti per i modelli di attribuzione API di Adobe Analytics 2.0. La guida illustra come includere i dati degli oggetti modello di attribuzione nei rapporti API di Dimension.<p>Per ulteriori informazioni, vedere [Modelli di attribuzione API Dimension](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/attmodel).</p> | | Maggio 2026 |
| **Servizi multimediali in streaming: supporto dei dati di pianificazione** <br/>Ora puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 ottobre 2025 | Prima metà del 2026<p>Rilascio originariamente pianificato per il 29 ottobre 2025</p> |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-446522, AN-445779, AN-445759, AN-444676, AN-442813, AN-441943, AN-441717, AN-441538, AN-441123, AN-440976, AN-440952, AN-440919, AN-440599, AN-439797, AN-434855, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Classificazioni**: AN-447743, AN-447296, AN-447130, AN-446552, AN-446324, AN-446040, AN-445841, AN-445753, AN-444992, AN-444979, AN-444428, AN-444332, AN-443507, AN-442906, AN-442232, AN-442207, AN-442133, AN-442035, AN-441901, AN-441807 441671 441333 441302 441267 441132 441085 441048 440846 440727 440716 440496 440429 432100, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-
**Feed dati e Data Warehouse**: AN-447344, AN-446654, AN-445126, AN-444492, AN-442802, AN-442211, AN-442048, AN-441719, AN-441534, AN-441300, AN-441183, AN-441011, AN-440625
**Migrazione**: AN-442467, AN-440380, AN-440357
**esportazioni**:
**Report Builder**: AN-448697, AN-447128, AN-441148, AN-441136, AN-438147, AN-425150
**Generazione rapporti**: AN-445123, AN-444869, AN-443453, AN-443275, AN-443148, AN-442464, AN-442148, AN-441811, AN-441506, AN-441149, AN-441119, AN-440545, AN-440511, AN-440300, AN-431409, AN-423359, AN-406242
**Suite di rapporti**:
**Report pianificati**:
**Segmentazione**:
**Altro**: AN-449159, AN-444661, AN-439429, AN-439423, AN-430988, AN-397985


## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Miglioramenti dell’elaborazione Livestream** | giovedì 14 gennaio 2026 | Adobe intende apportare miglioramenti e modifiche alla formattazione dei payload di LiveStream. Questi aggiornamenti offrono una migliore parità tra LiveStream e altre funzioni di Adobe Analytics, per esempio Analysis Workspace. È disponibile un endpoint di anteprima per testare le modifiche pianificate. Consulta [Note sulla versione di LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) per l’elenco completo delle modifiche e i dettagli sull’endopoint di anteprima. Adobe intende effettuare una transizione definitiva al formato di payload aggiornato in data 13 aprile 2026. |
| **Rimozione delle suite di crittografia TLS 1.2** | 11 febbraio 2026 | Avviso agli amministratori: il 27 maggio 2026 Adobe intende rimuovere il supporto delle seguenti suite di crittografia TLS 1.2 dai server di raccolta dati di Adobe.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>Per la maggior parte delle implementazioni non è richiesta alcuna azione da parte del cliente. Questa modifica interessa principalmente i dati di Analytics inviati da applicazioni native precedenti che utilizzano librerie TLS non aggiornate e da un numero limitato di visitatori web su browser o sistemi operativi obsoleti. La rimozione del supporto per queste suite di crittografia migliora la sicurezza e allinea Adobe ai moderni standard di crittografia. Attualmente, meno dello 0,1% del traffico di raccolta dati si basa su queste suite di crittografia.</p> |
| **Report Builder legacy** | 18 giugno 2025 | Il componente aggiuntivo precedente di Report Builder sarà ritirato a giugno 2026. Tutti gli utenti devono iniziare a eseguire l’aggiornamento delle cartelle di lavoro precedenti al [nuovo Report Builder](/help/analyze/report-builder/rb-overview.md). Il nuovo Report Builder è disponibile sia per i clienti di Adobe Analytics che di Customer Journey Analytics. Offre [quasi le stesse funzioni](/help/analyze/report-builder/convert-workbooks.md#unsupported), oltre a numerose nuove funzioni utili e miglioramenti dell’interfaccia utente. Per agevolare il processo di aggiornamento, il nuovo Report Builder include una facile funzione di conversione della cartella di lavoro. Il nuovo Report Builder è disponibile solo come componente aggiuntivo tramite Microsoft Store. Molte organizzazioni richiedono un processo di approvazione interno prima di rendere il componente aggiuntivo disponibile per gli utenti. Attendi il tempo necessario per questo processo e inizia a cooperare subito con la tua organizzazione per assicurarti di disporre del tempo sufficiente per eseguire l’aggiornamento delle cartelle di lavoro prima della data di fine del ciclo di vita. |
| **Accesso tramite domini precedenti o SSO precedente** | venerdì 10 aprile 2025 | Adobe intende aggiornare il modo in cui gli utenti accedono ad Adobe Analytics per migliorare la sicurezza e semplificare l’esperienza di accesso. In tale contesto, l’accesso tramite domini precedenti o SSO precedente, tra cui `my.omniture.com`, verrà interrotto definitivamente il **2 gennaio 2026**. Dopo questa data, le credenziali di accesso precedenti e l’SSO precedente non funzioneranno più. Tutti gli utenti dovranno effettuare l’accesso tramite `experience.adobe.com` con i propri ID Adobe Experience Cloud. Per assistenza con il tuo ID Experience Cloud, contatta l’amministratore di Adobe Analytics della tua organizzazione o l’[Assistenza clienti di Adobe](https://helpx.adobe.com/it/contact.html). |
| **API di Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |


## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, consulta le [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Risorse correlate

* [Note sulle versioni precedenti 2025](/help/release-notes/2025.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Streaming Media Services](https://experienceleague.adobe.com/it/docs/media-analytics/using/release-notes/release-notes)
* Ultimi aggiornamenti sulle versioni dei [prodotti Adobe CX Enterprise](https://business.adobe.com/products/adobe-experience-cloud-products.html)
