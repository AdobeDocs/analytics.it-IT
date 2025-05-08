---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 0bd4075a15edeeccdd9db8a70a1e871f9fc5af20
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 45%

---

# Note sulla versione corrente di Adobe Analytics (versione di aprile 2025)

**Ultimo aggiornamento**: 16 aprile 2025

Queste note sulla versione coprono il periodo di rilascio dal 26 marzo al maggio 2025. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Inventario di Analytics** | L’inventario di Analytics fornisce una panoramica completa dell’ambiente Adobe Analytics, compreso il numero di progetti e componenti, suite di rapporti, utenti e altro ancora. Automatizzando il processo di inventario, puoi comprendere rapidamente lo sforzo necessario per passare da Adobe Analytics a Customer Journey Analytics. Questo renderà la transizione più semplice e veloce. [Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/analytics-inventory) |  | 26 marzo 2025 |
| **Dimensioni solo Data Warehouse** | Sulla base del feedback ricevuto dai clienti, abbiamo deciso di effettuare una nuova valutazione. Non verrà rilasciata la funzione per sole dimensioni automatiche di Data Warehouse, come annunciato in precedenza. | | Da definire |

## Correzioni in Adobe Analytics

**A4T**: AN-370625; AN-371279; AN-371351
**Strumenti di amministrazione**: AN-365072; AN-371303
**Analysis Workspace**: AN-363831; AN-369554
**Classificazioni**: AN-370519; AN-370727; AN-370827; AN-370941; AN-370995; AN-371377; AN-371597; AN-371868; AN-371869; AN-372510; AN-372650; AN-373164; AN-373300; AN-373308; AN-373592
**Raccolta dati**: AN-371877
**Feed dati**: AN-368676; AN-370225; AN-370514; AN-370521; AN-370687; AN-370761; AN-370911; AN-371047; AN-371542; AN-371627; AN-371746; AN-372708; AN-373068; AN-373179
**Data Warehouse**: AN-366649; AN-369817; AN-370705; AN-371127; AN-371995; AN-372596; AN-372940
**Canali marketing**: AN-372308
**App mobile**: AN-370287; AN-371335; AN-371374
**Piattaforma**: AN-369510; AN-370435; AN-372150
**Report Builder**: AN-369830; AN-371395; AN-372983

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| N/D |  |  |

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Accesso tramite domini legacy o tramite SSO legacy** | venerdì 10 aprile 2025 | Adobe prevede di aggiornare il modo in cui gli utenti accedono ad Adobe Analytics per migliorare la sicurezza e semplificare l’esperienza di accesso. Come parte di questo impegno, l&#39;accesso tramite domini legacy o tramite SSO legacy, incluso `my.omniture.com`, verrà interrotto definitivamente il **2 gennaio 2026**. Dopo questa data, le credenziali di accesso legacy e l’SSO legacy non funzioneranno più. Tutti gli utenti dovranno effettuare l&#39;accesso tramite `experience.adobe.com` utilizzando i propri ID Adobe Experience Cloud. Se hai bisogno di assistenza con il tuo Experience Cloud ID, contatta l&#39;amministratore Adobe Analytics della tua organizzazione o l&#39;[Assistenza clienti Adobe](https://helpx.adobe.com/it/contact.html). |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | sabato 17 gennaio 2025 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di Adobe I/O devono effettuare la migrazione alle credenziali server-to-server di Adobe I/O OAuth entro il **30 giugno 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1 maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs)</li></ul> |
| **Fine del ciclo di vita per l’API di Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, fai riferimento alle [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Risorse correlate

* [Note sulle versioni precedenti 2025](/help/release-notes/2025.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
