---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 987638b1a5601a4c5713611b463e4ec77479ed8d
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 31%

---

# Note sulla versione corrente di Adobe Analytics (versione di giugno 2025)

**Ultimo aggiornamento**: giovedì 18 giugno 2025

Queste note sulla versione coprono il periodo dal 18 giugno al 15 luglio 2025. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Supporto per destinazioni sicure nel nuovo Report Builder** | Sono state aggiunte nuove destinazioni di esportazione al componente aggiuntivo Report Builder. Sono supportate le seguenti destinazioni di archiviazione cloud: <ul><li>Amazon S3 con ruolo ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> FTP non più supportato a causa di problemi di sicurezza. Il link alla documentazione seguirà a breve. |  | Giugno 18,2025 |
| **Nuova esperienza di anteprima** | Il pannello Anteprima, utilizzato per visualizzare in anteprima segmenti, metriche calcolate e altro ancora, ora utilizza una visualizzazione a barre orizzontali invece di una ad anello. |  | giovedì 18 giugno 2025 |
| **Finestra di dialogo modello di attribuzione modificato** | Ora puoi definire separatamente il contenitore e il periodo di tempo nella finestra di dialogo del modello di attribuzione. |  | Giugno 18,2025 |
| **Navigazione aggiornata all&#39;interfaccia utente Attributi del cliente** | L&#39;interfaccia utente Attributi del cliente è ora accessibile direttamente dal selettore delle app in Adobe Experience Cloud. |  | Da definire |
| **Contenuti multimediali in streaming: supporto dei dati di pianificazione** | Ora puoi caricare dati pianificati di contenuti multimediali in streaming precedenti per tracciare in modo più semplice e preciso il pubblico. Di seguito sono riportati alcuni esempi di contenuti live supportati con la pianificazione del caricamento dei dati:<ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati dei visualizzatori per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati dei visualizzatori per argomenti o segmenti di programma specifici. Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.<p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, e non era possibile collegare una determinata sessione a singoli argomenti o segmenti di programma. Ulteriori informazioni |  | giovedì 25 giugno 2025 |
| **Supporto per il pre-rendering di Chrome** | Controlla il comportamento delle librerie di raccolta dati quando Chrome esegue il pre-rendering di una pagina. Il link alla documentazione seguirà a breve. |  | martedì 30 giugno 2025 |

## Correzioni in Adobe Analytics

**A4T**: AN-379045
**Advertising Analytics**: AN-377338
**Avvisi**: AN-377229
**Analysis Workspace**: AN-378891; AN-379589; AN-379604; AN-381270; AN-382264; AN-382414;
**API 1.4**: AN-380188
**API 2.0**: AN-373078; AN-379006; AN-381248
**Classificazioni**: AN-379209; AN-379315; AN-379567; AN-379573; AN-379749; AN-379764; AN-379818; AN-380433; AN-381670; AN-381751; AN-381994; AN-382055; AN-382682; AN-383059; AN-383409
**Analisi contributi**: AN-369822
**Feed dati**: AN-365552; AN-367158; AN-378288; AN-379754; AN-380433; AN-380855; AN-380959; AN-381115; AN-381657; AN-381931
**Data Warehouse**: AN-379244
**Piattaforma**: AN-375847
**Regole di elaborazione**: AN-375157
**Report Builder**: AN-371395; AN-372174; AN-373815; AN-383194
**Chiamate server**: AN-380930
**Registri di utilizzo e accesso**: AN-372130; AN-382123
**Suite di rapporti virtuali**: AN-382010


## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Report Builder legacy** | giovedì 18 giugno 2025 | Il componente aggiuntivo legacy di Report Builder verrà ritirato a giugno 2026. Tutti gli utenti devono iniziare ad aggiornare le cartelle di lavoro legacy al [nuovo Report Builder](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/rb-overview). Il nuovo Report Builder è disponibile per i clienti di Adobe Analytics e Customer Journey Analytics. Ha [parità di funzionalità](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/convert-workbooks#unsupported) oltre a numerose nuove funzioni convenienti e miglioramenti all&#39;interfaccia utente. Per facilitare il processo di aggiornamento, il nuovo Report Builder include una funzione di conversione della cartella di lavoro semplice. Il nuovo Report Builder è disponibile solo come componente aggiuntivo tramite Microsoft Store. Molte organizzazioni richiedono un processo di approvazione interno prima che il componente aggiuntivo possa essere reso disponibile agli utenti. Attendi l’ora per questo processo e inizia a lavorare con la tua organizzazione ora per assicurarti di disporre del tempo sufficiente per aggiornare le cartelle di lavoro prima della data di fine del ciclo di vita. |
| **Accesso tramite domini legacy o tramite SSO legacy** | venerdì 10 aprile 2025 | Adobe prevede di aggiornare il modo in cui gli utenti accedono ad Adobe Analytics per migliorare la sicurezza e semplificare l’esperienza di accesso. Come parte di questo impegno, l&#39;accesso tramite domini legacy o tramite SSO legacy, incluso `my.omniture.com`, verrà interrotto definitivamente il **2 gennaio 2026**. Dopo questa data, le credenziali di accesso legacy e l’SSO legacy non funzioneranno più. Tutti gli utenti dovranno effettuare l&#39;accesso tramite `experience.adobe.com` utilizzando i propri ID Adobe Experience Cloud. Se hai bisogno di assistenza con il tuo Experience Cloud ID, contatta l&#39;amministratore Adobe Analytics della tua organizzazione o l&#39;[Assistenza clienti Adobe](https://helpx.adobe.com/contact.html). |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | sabato 17 gennaio 2025 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di Adobe I/O devono effettuare la migrazione alle credenziali server-to-server di Adobe I/O OAuth entro il **30 giugno 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1 maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **API Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |



## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, fai riferimento alle [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Risorse correlate

* [Note sulle versioni precedenti 2025](/help/release-notes/2025.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
