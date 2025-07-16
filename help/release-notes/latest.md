---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: ebe6716a3dde89d7212385c25044fb533d7737c2
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 32%

---

# Note sulla versione corrente di Adobe Analytics (versione di luglio 2025)

**Ultimo aggiornamento**: giovedì 16 luglio 2025

Queste note sulla versione coprono il periodo di rilascio dal 7 luglio al 15 agosto 2025. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Campi TNT Livestream con algoritmi** | Livestream è in fase di aggiornamento per garantire che la tecnologia continui a essere moderna e stabile. Come parte di questo aggiornamento, se il campo TNT contiene un algoritmo, inizieremo a incorporare il campo TNT nell’output Livestream. Tuttavia, sono inclusi solo gli elementi precedentemente supportati: `campaignId`, `recipeId`, `trafficType`, `actionId` e `actionName`. Lo schema TNT complessivo per Livestream rimane invariato. |   | Luglio 7,2025 |
| **Navigazione aggiornata all&#39;interfaccia utente Attributi del cliente** | L&#39;interfaccia utente Attributi del cliente è ora accessibile direttamente dal selettore delle app in Adobe Experience Cloud. | mercoledì 1 luglio 2025 | Da definire |

## Correzioni in Adobe Analytics

**Activity Map**: 360987
**Analysis Workspace**: AN-378094; AN-380979; AN-382908; AN-387652;
**Classificazioni**: AN-382412; AN-383157; AN-384616; AN-384803; AN-385933; AN-387320; AN-387351; AN-387832; AN-387833; AN-387839; AN-387915;
**Raccolta dati**: AN-387661
**Feed dati**: AN-375172; AN-384369; AN-387859; AN-387952; AN-388155;
**Piattaforma**: AN-382813; AN-386627; AN-386815
**Privacy**: AN-384390
**Report Builder**: AN-388035
**Generazione rapporti**: AN-380441
**Rapporti pianificati**: AN-378280; AN-378331
**Confronto segmenti**: AN-368766


## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Report Builder legacy** | 18 giugno 2025 | Il componente aggiuntivo legacy di Report Builder verrà ritirato a giugno 2026. Tutti gli utenti devono iniziare ad aggiornare le cartelle di lavoro legacy al [nuovo Report Builder](https://experienceleague.adobe.com/it/docs/analytics/analyze/report-builder/rb-overview). Il nuovo Report Builder è disponibile per i clienti di Adobe Analytics e Customer Journey Analytics. Ha [parità di funzionalità](https://experienceleague.adobe.com/it/docs/analytics/analyze/report-builder/convert-workbooks#unsupported) oltre a numerose nuove funzioni convenienti e miglioramenti all&#39;interfaccia utente. Per facilitare il processo di aggiornamento, il nuovo Report Builder include una funzione di conversione della cartella di lavoro semplice. Il nuovo Report Builder è disponibile solo come componente aggiuntivo tramite Microsoft Store. Molte organizzazioni richiedono un processo di approvazione interno prima che il componente aggiuntivo possa essere reso disponibile agli utenti. Attendi l’ora per questo processo e inizia a lavorare con la tua organizzazione ora per assicurarti di disporre del tempo sufficiente per aggiornare le cartelle di lavoro prima della data di fine del ciclo di vita. |
| **Accesso tramite domini legacy o tramite SSO legacy** | venerdì 10 aprile 2025 | Adobe prevede di aggiornare il modo in cui gli utenti accedono ad Adobe Analytics per migliorare la sicurezza e semplificare l’esperienza di accesso. Come parte di questo impegno, l&#39;accesso tramite domini legacy o tramite SSO legacy, incluso `my.omniture.com`, verrà interrotto definitivamente il **2 gennaio 2026**. Dopo questa data, le credenziali di accesso legacy e l’SSO legacy non funzioneranno più. Tutti gli utenti dovranno effettuare l&#39;accesso tramite `experience.adobe.com` utilizzando i propri ID Adobe Experience Cloud. Se hai bisogno di assistenza con il tuo Experience Cloud ID, contatta l&#39;amministratore Adobe Analytics della tua organizzazione o l&#39;[Assistenza clienti Adobe](https://helpx.adobe.com/it/contact.html). |
| **API Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](/help/admin/c-admin-api/c-admin-14-api-eol.md).</p> |


## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, fai riferimento alle [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Risorse correlate

* [Note sulle versioni precedenti 2025](/help/release-notes/2025.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/products/adobe-experience-cloud-products.html)
