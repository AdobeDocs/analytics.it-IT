---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d7beee25af3551426eb905f0e727545de068b2d9
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 42%

---

# Note sulla versione corrente di Adobe Analytics (versione di gennaio 2025)

**Ultimo aggiornamento**: martedì 22 gennaio 2024

Queste note sulla versione coprono il periodo di rilascio dal 15 gennaio a metà febbraio 2025. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Pianificazione nel nuovo Report Builder** | La programmazione non consente solo di pianificare le nuove cartelle di lavoro del Report Builder. Inoltre, consente di recuperare i metadati delle vecchie attività pianificate quando si convertono cartelle di lavoro legacy. In questo modo, quando si convertono le cartelle di lavoro legacy in nuove cartelle di lavoro e le si pianifica, le si inviano alle stesse e-mail e alla stessa frequenza delle cartelle di lavoro legacy. [Ulteriori informazioni](/help/analyze/report-builder/schedule-reportbuilder.md) |  | 22 gennaio 2025 |
| **Miglioramenti ai report (noti anche come modelli) in Analysis Workspace** | Sono ora disponibili diversi miglioramenti per i rapporti (noti anche come modelli):<ul><li>Ora denominato [!UICONTROL Templates] (non più denominato [!UICONTROL Reports]).</li><li>È stata migliorata l’esperienza dell’utente per visualizzare e trovare i modelli, inclusa l’opzione per visualizzare i modelli in una vista a colonne o a schede.</li><li>Posizione nuova e più intuitiva per i modelli aziendali (in **[!UICONTROL Workspace]** > **[!UICONTROL Templates]**).</li><li>In precedenza, si accedeva ai modelli aziendali dalla finestra di dialogo durante la creazione di un progetto.</li><li>Sono disponibili ulteriori modelli predefiniti.</li></ul>[Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/templates/use-templates).<p>Gli amministratori possono creare modelli e salvarli per l’utilizzo da parte di altri nella società di accesso. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/templates/create-templates) | giovedì 15 gennaio 2025 | venerdì 30 gennaio 2025 |
| **Periodo di conservazione ID transazione** | Il periodo di conservazione dell’ID transazione di 90 giorni verrà esteso a 25 mesi a febbraio del 2025. La variabile `transactionID` identifica in modo univoco una transazione in modo che l’hit possa collegarsi ai dati caricati tramite le origini dati. (Link alla documentazione da seguire) |  | mercoledì 11 febbraio 2025 |

## Correzioni in Adobe Analytics

**A4T**: AN-355602; AN-365988
**Activity Map**: AN-365320
**Admin Console**: AN-363884
**Strumenti di amministrazione**: AN-356747; AN-358776
**Advertising Analytics**: AN-355488
**Analysis Workspace**: AN-345318; AN-354801; AN-357052; AN-358975; AN-362886; AN-363831; AN-364124; AN-365257; AN-365319; AN-365462; AN-366194
**API di Analytics 1.4**: AN-358059
**Classificazioni**: AN-360049; AN-360424; AN-360745; AN-362208; AN-362345; AN-362560; AN-362576; AN-362633; AN-362653; AN-362762; AN-362815; AN-362881; AN-362885; AN-362973; AN-363343; AN-363558; AN-363860; AN-364239; AN-364480; AN-364451; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-364528; AN-364548 364552 364585 364598 364643 364715 364912 364997 365081 365189 365197 365203 365431 365647 365794 366546; AN-
**Migrazione componenti**: AN-362236; AN-365429
**Analisi contributi**: AN-360146
**Feed dati**: AN-356997; AN-362470; AN-362498; AN-362775; AN-363323; AN-363413; AN-363569; AN-364063; AN-364142; AN-364294; AN-364298; AN-364325; AN-364367; AN-364594; AN-364995; AN-365127; AN-365272; AN-365519; AN-365760; AN-366152;
**API Data Repair**: AN-362773; AN-362874
**Origini dati**: AN-360745; AN-362202; AN-364566
**Data Warehouse**: AN-361447; AN-362616; AN-364524; AN-365108
**App mobile**: AN-362856; AN-365270
**Avvisi di eccedenza**: AN-355594; AN-364547
**Piattaforma**: AN-358914; AN-360205; AN-362990; AN-364550; AN-365454; AN-365485
**Report Builder**: AN-363478; AN-364433; AN-365610
**Gestione attività di reporting**: AN-362440
**Segmentazione**: AN-359921
**Regole VISTA**: AN-362927

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Chi non fa parte della clientela di Campaign perderanno l’accesso ai trigger** | 16 ottobre 2023 | Il 30 gennaio 2025, i clienti Adobe Analytics che non dispongono di una licenza Adobe Campaign perderanno l&#39;accesso alla possibilità di configurare e utilizzare [Triggers](https://experienceleague.adobe.com/en/docs/core-services/interface/services/triggers). La clientela dovrà acquistare Campaign oppure pianificare l’interruzione dell’uso di trigger, o cercare altri strumenti di Adobe che offrono le funzionalità dei trigger. |

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
