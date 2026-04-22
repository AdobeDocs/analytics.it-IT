---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 907f510e02a0f5cb378c139a20cc147304ad0d70
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 91%

---

# Note sulla versione corrente di Adobe Analytics (aprile 2026)

**Ultimo aggiornamento**: giovedì 22 aprile 2026

Queste note sulla versione coprono il periodo di rilascio di aprile 2026. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ---- |
| **Server MCP per Adobe Analytics** <br/>I server MCP (Model Context Protocol) di Analytics consentono di collegare un client MCP supportato ad Adobe Analytics. Una volta connesso, il client MCP può richiamare strumenti specifici per il prodotto per recuperare dati, eseguire query o eseguire operazioni supportate come parte di un flusso di lavoro LLM o agente. Per ulteriori informazioni, vedere [Server MCP di Analytics](https://developer.adobe.com/analytics-mcp/docs/).<p>Se hai utilizzato questi server MCP durante il periodo beta, tieni presente che esistono URL diversi tra gli endpoint beta e di produzione. Assicurati che tutti i flussi di lavoro agenti creati durante il periodo beta vengano aggiornati per utilizzare gli endpoint di produzione prima del 31 maggio.</p> | | giovedì 29 aprile 2026 |
| **Servizi multimediali in streaming: supporto dei dati di pianificazione** <br/>Ora puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 ottobre 2025 | Prima metà del 2026<p>Rilascio originariamente pianificato per il 29 ottobre 2025</p> |
| **Formattazione aggiuntiva dell’intervallo di date API**<br/> Sono ora supportati due nuovi formati per specificare gli intervalli di date nelle richieste di rapporti API di Analytics 2.0. Ciò include una formula di data e un formato misto. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#date-range-field--supported-formats) | | Marzo 2026 |
| **Dimensione facoltativa nelle richieste di rapporti API**<br/> Non è necessario un oggetto dimensione nelle richieste di rapporti API. Se non è specificata alcuna dimensione, la risposta mostra i dati di un rapporto sui totali. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#using-dimension-in-report-payload-requests) | | Marzo 2026 |
| **Rapporti API avanzati con tendenze sulle date**<br/> Nuova guida dei rapporti API avanzati con tendenze sulle date di Adobe Analytics 2.0. Crea rapporti API avanzati con tendenze sulle date utilizzando confronti e segmenti di intervalli di date. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced/) | | Marzo 2026 |

## Correzioni in Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-442813, AN-442410, AN-441943, AN-441717, AN-434855, AN-431409, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Classificazioni**: AN-443453, AN-443275, AN-443148, AN-442906, AN-442232, AN-442207, AN-442148, AN-442133, AN-441937, AN-441901, AN-441807, AN-441671, AN-441333, AN-441302, AN-441149, AN-441132, AN-441085, AN-441048, AN-440846, AN-440727, AN-440716, AN-440511, AN-440496, AN-432100
**Feed di dati e Data Warehouse**: AN-442211, AN-441719, AN-441183, AN-441011, AN-440625, AN-438953
**Migrazione**: AN-442467, AN-440380, AN-440357
**Esportazioni**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Reporting**: AN-441506, AN-440919, AN-440545, AN-440300
**Suite di rapporti**: AN-439429, AN-439423, AN-430988
**Rapporti pianificati**:
**Segmentazione**:
**Altro**: AN-423359, AN-406242, AN-397985


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
* [Note sulla versione dei servizi multimediali in streaming &#x200B;](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
