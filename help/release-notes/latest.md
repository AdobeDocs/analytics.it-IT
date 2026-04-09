---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 7a245e2c24e8763c93150aa5b9f3ac2d197f6f1f
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 32%

---

# Note sulla versione corrente di Adobe Analytics (aprile 2026)

**Ultimo aggiornamento**: venerdì 9 aprile 2026

Queste note sulla versione coprono il periodo di rilascio di aprile 2026. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ---- |
| **Server MCP per Adobe Analytics** <br/>È ora possibile collegare Adobe Analytics ai flussi di lavoro agenti esistenti utilizzando MCP (Model Context Protocol). Puoi richiedere rapporti e informazioni utilizzando il linguaggio naturale.<p>Il collegamento alla documentazione seguirà a breve.</p> | | Fine di aprile 2026 |
| **Servizi multimediali in streaming: supporto dei dati di pianificazione** <br/>È ora possibile caricare dati pianificati di contenuti multimediali in streaming passati per tenere traccia in modo più semplice e preciso del pubblico.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 ottobre 2025 | Prima metà del 2026<p>Rilascio originariamente pianificato per il 29 ottobre 2025</p> |
| **Formattazione aggiuntiva dell&#39;intervallo di date API**<br/> Sono ora supportati due nuovi formati per specificare intervalli di date nelle richieste di report API di Analytics 2.0. Ciò include una formula di data e un formato misto. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#date-range-field--supported-formats) | | Marzo 2026 |
| **Dimensione facoltativa nelle richieste di report API**<br/> Nelle richieste API di report non è richiesto un oggetto dimensione. Se non è specificata alcuna dimensione, la risposta mostra i dati per un rapporto sui totali. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/#using-dimension-in-report-payload-requests) | | Marzo 2026 |
| **Rapporto API avanzato con tendenza data**<br/> Nuova guida report avanzato con tendenza data API di Adobe Analytics 2.0. Crea rapporti API con tendenze per le date avanzati utilizzando confronti tra intervalli di date e segmenti. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/advanced/) | | Marzo 2026 |

## Correzioni in Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-442813, AN-442410, AN-441943, AN-441717, AN-434855, AN-431409, AN-429777, AN-429048, AN-428892, AN-428189, AN-425215
**Classificazioni**: AN-443453, AN-443275, AN-443148, AN-442906, AN-442232, AN-442207, AN-442148, AN-442133, AN-441937, AN-441901, AN-441807, AN-441671, AN-441333, AN-441302, AN-441149, AN-441132, AN-441085, AN-441048, AN-440846, AN-440727 440716 440511 440496 432100, AN-, AN-, AN-, AN-, AN-
**Feed dati e Data Warehouse**: AN-442211, AN-441719, AN-441183, AN-441011, AN-440625, AN-438953
**Migrazione**: AN-442467, AN-440380, AN-440357
**Esportazioni**:
**Report Builder**: AN-441136, AN-438147, AN-425150
**Generazione rapporti**: AN-441506, AN-440919, AN-440545, AN-440300
**Suite di rapporti**: AN-439429, AN-439423, AN-430988
**Report pianificati**:
**Segmentazione**:
**Altro**: AN-423359, AN-406242, AN-397985


## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Miglioramenti all&#39;elaborazione Livestream** | giovedì 14 gennaio 2026 | Adobe prevede di apportare miglioramenti e modifiche alla formattazione dei payload LiveStream. Questi aggiornamenti forniscono una migliore parità tra LiveStream e altre funzioni di Adobe Analytics, come Analysis Workspace. È disponibile un endpoint di anteprima che consente di verificare le modifiche pianificate. Consulta le [Note sulla versione di LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) per l&#39;elenco completo delle modifiche e l&#39;anteprima dei dettagli dell&#39;endpoint. Il 13 aprile 2026, Adobe pianifica un passaggio definitivo al formato del payload aggiornato. |
| **Rimozione suite di cifratura TLS 1.2** | giovedì 11 febbraio 2026 | Avviso agli amministratori: il 27 maggio 2026 Adobe pianifica di rimuovere il supporto per le seguenti suite di cifratura TLS 1.2 dai server di raccolta dati di Adobe.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>Per la maggior parte delle implementazioni non è richiesta alcuna azione da parte del cliente. Questa modifica interessa principalmente i dati di Analytics inviati da applicazioni native legacy che utilizzano librerie TLS obsolete e un numero limitato di visitatori web su browser o sistemi operativi obsoleti. La rimozione del supporto per queste suite di crittografia migliora la sicurezza e allinea Adobe ai moderni standard di crittografia. Meno dello 0,1% del traffico di raccolta dati si basa attualmente su queste suite di cifratura.</p> |
| **Report Builder legacy** | 18 giugno 2025 | Il componente aggiuntivo legacy di Report Builder verrà ritirato a giugno 2026. Tutti gli utenti devono iniziare ad aggiornare le cartelle di lavoro legacy al [nuovo Report Builder](/help/analyze/report-builder/rb-overview.md). Il nuovo Report Builder è disponibile per i clienti di Adobe Analytics e Customer Journey Analytics. Ha [parità di funzionalità](/help/analyze/report-builder/convert-workbooks.md#unsupported) oltre a numerose nuove funzioni convenienti e miglioramenti all&#39;interfaccia utente. Per facilitare il processo di aggiornamento, il nuovo Report Builder include una funzione di conversione della cartella di lavoro semplice. Il nuovo Report Builder è disponibile solo come componente aggiuntivo tramite Microsoft Store. Molte organizzazioni richiedono un processo di approvazione interno prima che il componente aggiuntivo possa essere reso disponibile agli utenti. Attendi l’ora per questo processo e inizia a lavorare con la tua organizzazione ora per assicurarti di disporre del tempo sufficiente per aggiornare le cartelle di lavoro prima della data di fine del ciclo di vita. |
| **Accesso tramite domini legacy o tramite SSO legacy** | venerdì 10 aprile 2025 | Adobe prevede di aggiornare il modo in cui gli utenti accedono ad Adobe Analytics per migliorare la sicurezza e semplificare l’esperienza di accesso. Come parte di questo impegno, l&#39;accesso tramite domini legacy o tramite SSO legacy, incluso `my.omniture.com`, verrà interrotto definitivamente il **2 gennaio 2026**. Dopo questa data, le credenziali di accesso legacy e l’SSO legacy non funzioneranno più. Tutti gli utenti dovranno effettuare l&#39;accesso tramite `experience.adobe.com` utilizzando i propri ID Adobe Experience Cloud. Se hai bisogno di assistenza con il tuo Experience Cloud ID, contatta l&#39;amministratore Adobe Analytics della tua organizzazione o l&#39;[Assistenza clienti Adobe](https://helpx.adobe.com/it/contact.html). |
| **API Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |


## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, fai riferimento alle [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Risorse correlate

* [Note sulle versioni precedenti 2025](/help/release-notes/2025.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Streaming Media Services](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
