---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 924f5f670d2f29269a5ba6623079e839f1fe8122
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 53%

---

# Note sulla versione corrente di Adobe Analytics (versione di febbraio 2025)

**Ultimo aggiornamento**: 21 febbraio 2024

Queste note sulla versione coprono il periodo dall’11 febbraio a metà marzo 2025. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Periodo di conservazione ID transazione** | Il periodo di conservazione dell’ID transazione di 90 giorni è stato esteso a 25 mesi. La variabile `transactionID` identifica in modo univoco una transazione in modo che l’hit possa collegarsi ai dati caricati tramite le origini dati. Ulteriori informazioni [qui](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/transactionid) e [qui](https://experienceleague.adobe.com/en/docs/analytics/import/data-sources/transactionid). |  | venerdì 20 febbraio 2025 |
| **Riferimento API feed dati** | Il [riferimento](https://adobedocs.github.io/analytics-2.0-apis/?urls.primaryName=Data%20Feeds%20APIs) per l&#39;API Feed dati è ora disponibile. |  | 30 gennaio 2025 |
| **API Livestream - Implementazione client** | Utilizza l’implementazione client Livestream per utilizzare i dati Livestream. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/clientcode/) |  | mercoledì 18 febbraio 2025 |
| **Aggiornamento all&#39;API delle classificazioni** | Ora puoi rimuovere singoli campi o chiavi di classificazione dal server. Questo fornisce un’alternativa all’eliminazione di un intero set di dati di classificazione con il metodo DELETE. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/remove-values/) |  | mercoledì 18 febbraio 2025 |


## Correzioni in Adobe Analytics

**Analysis Workspace**: AN-359974; AN-366212; AN-368460
**Classificazioni**: AN-367186; AN-367328; AN-368548
**Migrazione componenti**: AN-364529; AN-366398; AN-367509;
**Feed dati**: AN-365685; AN-366745; AN-367256; AN-367349; AN-368363
**Data Warehouse**: AN-368178; AN-368331;
**App mobile**: AN-367137
**Piattaforma**: AN-351924; AN-365540; AN-365866; AN-366898; AN-367856; AN-367933
**Report Builder**: AN-366456; AN-366655;
**Suite di rapporti virtuali**: AN-367411
**Regole VISTA**: AN-365331

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Prossimo aggiornamento del campo dati contestuali di Analytics`a.locale`** | sabato 21 febbraio 2025 | Il 5 marzo 2025 verrà aggiornato il modo in cui viene impostato il campo dei dati contestuali di Analytics `a.locale` durante la raccolta dei dati tramite Experience Edge. Quando i dati vengono inviati ad Adobe Analytics utilizzando Experience Edge, i campi Analytics vengono compilati in base a una mappatura dei campi XDM. Il mapping per `c.a.locale` fa riferimento a un campo XDM non standard, `xdm.environment.language`. Questo campo verrà aggiornato per fare riferimento al campo corretto, `xdm.environment._dc.language`.  Il mapping continuerà a fare riferimento a `xdm.environment.language` per compatibilità con le versioni precedenti. Per la continuità, se sono impostati entrambi i campi, `xdm.environment.language` avrà la precedenza. Puoi visualizzare l&#39;elenco completo delle mappature da XDM ai campi Analytics standard [qui](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping). |
| **Chi non fa parte della clientela di Campaign perderanno l’accesso ai trigger** | 16 ottobre 2023 | Il 30 gennaio 2025, i clienti Adobe Analytics che non dispongono di una licenza Adobe Campaign hanno perso l&#39;accesso alla possibilità di configurare e utilizzare [Triggers](https://experienceleague.adobe.com/en/docs/core-services/interface/services/triggers). La clientela dovrà acquistare Campaign oppure pianificare l’interruzione dell’uso di trigger, o cercare altri strumenti di Adobe che offrono le funzionalità dei trigger. |

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | sabato 17 gennaio 2025 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di Adobe I/O devono effettuare la migrazione alle credenziali server-to-server di Adobe I/O OAuth entro il **30 giugno 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1 maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fine del ciclo di vita per l’API di Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.26.0), fare riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2024](/help/release-notes/2024.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
