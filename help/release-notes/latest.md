---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d81412790f5658d90890c48eca50548cd57b4b48
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 55%

---

# Note sulla versione corrente di Adobe Analytics (versione di marzo 2025)

**Ultimo aggiornamento**: sabato 11 aprile 2025

Queste note sulla versione coprono il periodo compreso tra il 5 marzo e maggio 2025. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Inventario di Analytics** | L’inventario di Analytics fornisce una panoramica completa dell’ambiente Adobe Analytics, compreso il numero di progetti e componenti, suite di rapporti, utenti e altro ancora. Automatizzando il processo di inventario, puoi comprendere rapidamente lo sforzo necessario per passare da Adobe Analytics a Customer Journey Analytics. Questo renderà la transizione più semplice e veloce. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory) |  | 26 marzo 2025 |
| **Aggiornamento al campo dati contestuali di Analytics`a.locale`** | Questo aggiornamento cambia il modo in cui il campo dei dati contestuali di Analytics `a.locale` viene impostato durante la raccolta di dati tramite Experience Edge. Quando i dati vengono inviati ad Adobe Analytics utilizzando Experience Edge, i campi Analytics vengono compilati in base a una mappatura dei campi XDM. Il mapping per `c.a.locale` fa riferimento a un campo XDM non standard, `xdm.environment.language`. Questo campo verrà aggiornato per fare riferimento al campo corretto, `xdm.environment._dc.language`.<p>Il mapping continuerà a fare riferimento a `xdm.environment.language` per compatibilità con le versioni precedenti. Per la continuità, se sono impostati entrambi i campi, `xdm.environment.language` ha la precedenza. Puoi visualizzare l&#39;elenco completo delle mappature da XDM ai campi Analytics standard [qui](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/xdm-var-mapping). | | 5 marzo 2025 |
| **Guida per l’aggiornamento di Customer Journey Analytics** | Consente di generare una guida dettagliata per l’aggiornamento da Adobe Analytics a Customer Journey Analytics. Questa guida è personalizzata per l’organizzazione e prende in considerazione l’attuale ambiente Adobe Analytics, gli utilizzi previsti di Customer Journey Analytics ed eventuali compromessi legati al risparmio di tempo che l’organizzazione desidera fare.<p>Per iniziare a generare la guida personalizzata, accedi a [!DNL Customer Journey Analytics], quindi seleziona **[!UICONTROL Upgrade to Customer Journey Analytics]** nella scheda **[!UICONTROL Workspace]**.<p>[Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | 11 marzo 2025 |
| **Dimensioni solo Data Warehouse** | Sulla base del feedback ricevuto dai clienti, abbiamo deciso di effettuare una nuova valutazione. La funzione automatica di solo Data Warehouse non verrà rilasciata come annunciato in precedenza. | | Da definire |


## Correzioni in Adobe Analytics

**Activity Map**: 361038
**Strumenti di amministrazione**: AN-362178; AN-369483
**API di Analytics 1.4**: AN-369615
**Analysis Workspace**: AN-353491; AN-363403; AN-367230; AN-367313; AN-368582; AN-369821; AN-370227;
**Classificazioni**: AN-369848; AN-370196; AN-370226; AN-370437
**Feed dati**: AN-366162; AN-368906; AN-369066; AN-369087; AN-369225; AN-369798
**Governance dei dati**: AN-365157
**Origini dati**: AN-367550
**Piattaforma**: AN-363931
**Report Builder**: AN-367460; AN-368975

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| N/D |  |  |

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | sabato 17 gennaio 2025 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di Adobe I/O devono effettuare la migrazione alle credenziali server-to-server di Adobe I/O OAuth entro il **30 giugno 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1 maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fine del ciclo di vita per l’API di Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, fai riferimento alle [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Risorse correlate

* [Note sulle versioni precedenti 2025](/help/release-notes/2025.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
