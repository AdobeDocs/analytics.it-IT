---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: c8d38d67590c0422ed898d20ffa788b5fd34041c
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 51%

---

# Note sulla versione corrente di Adobe Analytics (versione del 23 ottobre 2024)

**Ultimo aggiornamento**: giovedì 23 ottobre 2024

Queste note sulla versione coprono il periodo dal 16 ottobre 2024 alla fine del 2024. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Nuovo Report Builder per Adobe Analytics** | La nuova applicazione di Report Builder introduce un aggiornamento importante ad Adobe Analytics, che include prestazioni migliorate, interfaccia utente semplificata, supporto API 2.0 e supporto per Microsoft Excel su Mac, Windows e browser web. Questa applicazione può essere utilizzata insieme all’applicazione legacy, ma non sullo stesso file. È disponibile una funzione di aggiornamento per aggiornare le cartelle di lavoro legacy alla nuova applicazione. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics/analyze/report-builder/report-buider-overview) |  | 16 ottobre 2024 |
| **Esportazione JSON per la migrazione dell&#39;implementazione dei tag in tag Web SDK** | Questo aggiornamento dell’estensione tag di Analytics è correlato alla migrazione a Web SDK. Puoi utilizzare questo aggiornamento all’estensione Adobe Analytics come parte del flusso di lavoro per ricreare le configurazioni delle estensioni con l’estensione Web SDK. Nell’estensione tag di Adobe Analytics, puoi visualizzare le impostazioni di eVar, prop ed eventi come JSON, che possono essere esportate per la modifica e incluse nell’estensione Web SDK. |  | giovedì 23 ottobre 2024 |

## Correzioni in Adobe Analytics

Analysis Workspace: AN-356287; AN-358435; AN-359456; AN-359826; AN-360215
Strumenti di amministrazione: AN-342485; AN-347931; AN-348704; AN-357723; AN-358453; AN-358717; AN-359548; AN-360136
Classificazioni: AN-359025; AN-359283; AN-359368; AN-359710; AN-359752; AN-359759; AN-359799; AN-359887; AN-360543; AN-360566; AN-360612; AN-360741; AN-360942; AN-360952
Analytics tra dispositivi: AN-359210
Attributi del cliente: AN-357897
Raccolta dati: AN-351131; AN-351309; AN-355678; AN-359856
Feed dati: AN-359699
API Data Repair: AN-360256
Origini dati: AN-359290
Data Warehouse: AN-359820
Avvisi eccedenza: AN-358132

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **I clienti non appartenenti a Campaign perderanno l&#39;accesso a Triggers** | 16 ottobre 2023 | Il 30 gennaio 2025, i clienti di Adobe Analytics che non dispongono di una licenza Adobe Campaign perderanno l’accesso alla possibilità di configurare e utilizzare Triggers. I clienti devono acquistare Campaign, pianificare l’interruzione dell’utilizzo di Triggers o esaminare altri strumenti di Adobe che offrono funzionalità di Triggers. |
| **Campi XDM aggiuntivi dei dettagli di implementazione mappati automaticamente** | 11 settembre 2024 | Quando si utilizza Adobe Experience Platform Edge Network per inviare dati ad Adobe Analytics, i campi XDM `xdm.implementationdetails.name` e `xdm.implementationdetails.environment` ora vengono sempre mappati alle variabili di dati di contesto `c.a.x.implementationdetails.name` e `c.a.x.implementationdetails.environment`. In precedenza, alcuni scenari impedivano il popolamento di questi valori. Adeguare le regole di elaborazione pertinenti in base alla disponibilità di questi valori. |

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Fine del ciclo di vita per l’API di Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno chiusi e le integrazioni correnti create utilizzando questi servizi cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |


## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.26.0), fare riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2024](/help/release-notes/2024.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione del componente aggiuntivo Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
