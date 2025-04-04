---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: bf6a811aac7d881517944c8308fd97e719791cc0
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 38%

---

# Note sulla versione corrente di Adobe Analytics (versione di marzo 2025)

**Ultimo aggiornamento**: sabato 4 aprile 2025

Queste note sulla versione coprono il periodo compreso tra il 5 marzo e maggio 2025. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Inventario di Analytics** | L’inventario di Analytics fornisce una panoramica completa dell’ambiente Adobe Analytics, compreso il numero di progetti e componenti, suite di rapporti, utenti e altro ancora. Automatizzando il processo di inventario, puoi comprendere rapidamente lo sforzo necessario per passare da Adobe Analytics a Customer Journey Analytics. Questo renderà la transizione più semplice e veloce. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory) |  | 26 marzo 2025 |
| **Aggiornamento al campo dati contestuali di Analytics`a.locale`** | Questo aggiornamento cambia il modo in cui il campo dei dati contestuali di Analytics `a.locale` viene impostato durante la raccolta di dati tramite Experience Edge. Quando i dati vengono inviati ad Adobe Analytics utilizzando Experience Edge, i campi Analytics vengono compilati in base a una mappatura dei campi XDM. Il mapping per `c.a.locale` fa riferimento a un campo XDM non standard, `xdm.environment.language`. Questo campo verrà aggiornato per fare riferimento al campo corretto, `xdm.environment._dc.language`.<p>Il mapping continuerà a fare riferimento a `xdm.environment.language` per compatibilità con le versioni precedenti. Per la continuità, se sono impostati entrambi i campi, `xdm.environment.language` ha la precedenza. Puoi visualizzare l&#39;elenco completo delle mappature da XDM ai campi Analytics standard [qui](https://experienceleague.adobe.com/it/docs/analytics/implementation/aep-edge/xdm-var-mapping). | | 5 marzo 2025 |
| **Guida per l’aggiornamento di Customer Journey Analytics** | Consente di generare una guida dettagliata per l’aggiornamento da Adobe Analytics a Customer Journey Analytics. Questa guida è personalizzata per l’organizzazione e prende in considerazione l’attuale ambiente Adobe Analytics, gli utilizzi previsti di Customer Journey Analytics ed eventuali compromessi legati al risparmio di tempo che l’organizzazione desidera fare.<p>Per iniziare a generare la guida personalizzata, accedi a [!DNL Customer Journey Analytics], quindi seleziona **[!UICONTROL Upgrade to Customer Journey Analytics]** nella scheda **[!UICONTROL Workspace]**.<p>[Ulteriori informazioni](https://experienceleague.adobe.com/it/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) |  | 11 marzo 2025 |
| **Dimensioni solo Data Warehouse** | A partire da maggio 2025, Adobe inizierà a impostare determinate dimensioni (variabili personalizzate come eVar e prop) come &quot;Solo Data Warehouse&quot;. Ciò si applica alle dimensioni che presentano le seguenti caratteristiche:<ul><li> In un periodo di più mesi, la variabile raggiunge il limite di traffico basso nei primi giorni del mese.</li><li>> 90% dei valori trasmessi vengono visualizzati una sola volta nel corso del mese.</li></ul>Alcuni esempi includono dimensioni contenenti marche temporali, UUID o altri dati con cardinalità estremamente elevata e in cui nuovi valori univoci vengono trasmessi per quasi ogni hit (o visita o visitatore) nel corso del mese. Queste dimensioni di solito superano molto rapidamente i limiti di traffico ridotto e solo una porzione molto piccola dei valori è segnalabile in Analysis Workspace. In questo modo i rapporti che utilizzano queste dimensioni creano confusione, poiché non mostrano informazioni utili o accurate. Queste dimensioni non seguono lo scopo o non traggono vantaggio dalla funzionalità a traffico ridotto, che ha lo scopo di fornire un modo per generare rapporti sui valori che diventano &quot;popolari&quot; dopo che la dimensione ha superato i limiti di traffico ridotto durante il mese. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics/technotes/low-traffic.)<p>Le dimensioni contrassegnate come &quot;Solo Data Warehouse&quot; non saranno disponibili per il reporting in Analysis Workspace. Tuttavia, saranno ancora disponibili per il reporting tramite Data Warehouse, perché qui non si applicano limiti di traffico ridotti.<p>Ciò non significa che ogni dimensione che ha raggiunto i limiti di traffico ridotto sia una candidata per essere contrassegnata come &quot;solo Data Warehouse&quot;. La maggior parte delle dimensioni che raggiungono i limiti di traffico ridotto soddisfano effettivamente l’intenzione della funzionalità di traffico ridotto:<ul><li>La maggior parte dei valori passati non è univoca.</li><li>I valori comuni continuano ad arrivare dopo che i limiti di traffico ridotti sono stati raggiunti durante il mese.</li><li>Possono comunque verificarsi nuovi valori &quot;popolari&quot;.</li></ul>Solo le dimensioni in cui quasi tutti i valori passati sono nuovi e univoci verranno contrassegnate come &quot;Solo Data Warehouse&quot;. Aumentare i limiti di traffico ridotti non è una soluzione data l&#39;unicità dei dati raccolti in queste situazioni. | | Maggio 2025 |


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
