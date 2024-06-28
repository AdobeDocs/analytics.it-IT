---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 4633225cc35658a7de39a40cd77df00137a54461
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 97%

---

# Note sulla versione corrente di Adobe Analytics (giugno 2024)

**Ultimo aggiornamento**: giovedì 26 giugno 2024

Queste note sulla versione coprono il periodo di rilascio dal 12 giugno fino a tutto luglio. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Selezionare più campi in un filtro a discesa** | Quando a un filtro con menu discesa sono stati aggiunti più campi, ora gli utenti possono selezionare più campi alla volta. Il pannello viene filtrato per includere uno qualsiasi dei campi selezionati. <p>In precedenza, gli utenti potevano selezionare un solo campo alla volta in un filtro con menu a discesa.</p><p>Per ulteriori informazioni, consulta [Segmenti a discesa statici](/help/analyze/analysis-workspace/c-panels/panels.md#static-drop-down-segments) in [Panoramica dei pannelli](/help/analyze/analysis-workspace/c-panels/panels.md).</p><p>[Visualizza una dimostrazione video di questa funzione](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/use-multi-select-drop-down-filters).</p> |  | 19 giugno 2024 |
| **Sommario per progetti Workspace** | È ora disponibile un nuovo sommario dei progetti. Il sommario fornisce collegamenti che consentono agli utenti di passare rapidamente a pannelli e visualizzazioni all’interno del progetto. Il sommario può essere abilitato per singoli progetti o per tutti i progetti di un determinato utente.<p>Per ulteriori informazioni, consulta [Sommario di un progetto](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md).</p><p>[Visualizza una dimostrazione video di questa funzione](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/create-a-toc-in-analysis-workspace).</p> |  | 19 giugno 2024 |
| **Creare collegamenti ipertestuali per elementi dimensionali in una tabella a forma libera** | In Analysis Workspace puoi creare collegamenti ipertestuali per uno o più elementi dimensionali, per renderli cliccabili all’interno di una tabella a forma libera. <p>Puoi creare collegamenti ipertestuali per elementi dimensionali che hanno valori URL, oppure puoi creare URL personalizzati per elementi dimensionali che hanno valori non URL.</p><p>Puoi creare URL dinamici personalizzati per più elementi dimensionali, utilizzando le variabili. Le variabili possono fare riferimento al valore di un elemento dimensionale o alla dimensione del raggruppamento.</p><p>Per ulteriori informazioni, consulta [Creare collegamenti ipertestuali per le dimensioni in una tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).</p><p>[Visualizza una dimostrazione video di questa funzione](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/tips-and-tricks/create-hyperlinks-in-freeform-tables).</p> |  | 19 giugno 2024 |
| **Impostazioni dell’amministratore per controllare gli account e le posizioni utilizzati per l’esportazione e l’importazione** | Una nuova [scheda “Impostazioni amministratore” in Gestione posizioni](/help/components/locations/locations-manager.md#configure-company-wide-settings-administrators-only) consente agli amministratori di controllare se gli utenti possono creare e modificare account e posizioni. Queste impostazioni si applicano quando gli utenti configurano gli [account cloud di importazione ed esportazione](/help/components/locations/configure-import-accounts.md) e le [posizioni cloud di importazione ed esportazione](/help/components/locations/configure-import-locations.md). <p>Gli amministratori possono anche limitare i tipi di account (Google Cloud Platform, Azure RBAC, Amazon S3 e così via) che gli utenti possono creare e utilizzare.</p><p>In precedenza, tutti gli utenti potevano creare, modificare e utilizzare account e posizioni per qualsiasi tipo di account.</p> | 12 giugno 2024 | 20 giugno 2024 |
| **Condividere account e posizioni utilizzati per l’esportazione e l’importazione** | Gli utenti possono ora rendere disponibili a tutti gli utenti della propria organizzazione gli account e le posizioni creati. Solo i proprietari degli account e delle posizioni e gli amministratori di sistema possono modificarli ed eliminarli.<p>In precedenza, gli account e le posizioni potevano essere utilizzati solo dall’utente che li aveva creati.</p><p>Queste impostazioni sono disponibili quando gli utenti [configurano account e posizioni di importazione ed esportazione cloud](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-accounts)[](https://experienceleague.adobe.com/it/docs/analytics/components/locations/configure-import-locations). </p> | 12 giugno 2024 | 20 giugno 2024 |
| **Fare in modo che Activity Map utilizzi un numero inferiore di chiamate server per Web SDK** | Attualmente, gli eventi di collegamento Activity Map vengono conteggiati come propri eventi e comportano costi aggiuntivi. Questo miglioramento raccoglie alcuni eventi di collegamento e li inserisce nell’hit successivo, in modo simile a come gli eventi vengono gestiti da AppMeasurement. <p>Il link alla documentazione seguirà a breve</p> | La versione beta aperta inizia il giovedì 10 luglio 2024 | Da definire |
| **Nuova guida API per le origini dati** | Gli endpoint [API origini dati di Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-sources/) forniscono metodi per creare, visualizzare, eliminare e caricare negli account di origini dati. |  | Disponibile ora |
| **Nuovi metodi nella guida dell’API per le classificazioni** | Nella guida dell’API per le classificazioni sono stati aggiunti due nuovi metodi per recuperare le partizioni di file.<ul><li>[Ottenere una partizione del file nel processo di classificazione](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/#get-classification-job-file-partition-list)</li><li>[Ottenere una partizione del file nel processo di esportazione della classificazione](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/#get-classification-export-job-file-part)</li></ul> |  | Disponibile ora |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* Sono stati risolti i seguenti problemi di classificazione: AN-347682; AN-348396; AN-348625; AN-348668; AN-348926; AN-348936; AN-349040; AN-349191; AN-349195; AN-349443; AN-349697; AN-349758; AN-349862; AN-350051; AN-350054; AN-350208; AN-350497; AN-350525; AN-351067
* Sono stati risolti i seguenti problemi relativi alle Data Warehouse: AN-346862; AN-349409; AN-349926; AN-350629; AN-350996
* Sono stati risolti i seguenti problemi relativi ai feed di dati: AN-346727; AN-348282; AN-348334; AN-348725; AN-348726; AN-348823; AN-349081; AN-349207; AN-349307; AN-349539; AN-349710; AN-349729; AN-349742; AN-349878; AN-349943; AN-350527;
* Sono stati risolti i seguenti problemi relativi alle origini dati: AN-350038
* Sono stati risolti i seguenti problemi di Analysis Workspace: AN-342953; AN-346346; AN-349590; AN-349717; AN-350057; AN-350697; AN-350904
* Sono stati risolti i seguenti problemi relativi a Report Builder: AN-348903; AN-350691
* Sono stati risolti i seguenti problemi relativi a A4T: AN-347690; AN-350853

### Altre correzioni apportate ad Analytics

AN-346470; AN-346850; AN-347227; AN-348145; AN-348564; AN-349001; AN-349008; AN-349211; AN-349719; AN-350523;

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza di 13 mesi di`cust_visids`** salvati | 22 maggio 2024 | Una prossima versione del motore di elaborazione degli hit di Analytics, **prevista per luglio 2024**, inizierà ad applicare una scadenza di 13 mesi di `cust_visids` salvati. Se nella suite di rapporti è abilitato “Abilita unione visitatori”, questa impostazione viene utilizzata per trovare `cust_visid` per un `visid_high/visid_low value` senza `cust_visid` sull’hit. Attualmente, non vi è alcuna scadenza della mappatura di un `cust_visid` per un `visid_high/visid_low`. Con questa versione, se sono trascorsi 13 mesi o più da quando `visid_high/visid_low` ha avuto un `cust_visid` su un hit, la mappatura scadrà. |
| **Aggiornamenti per area geografica ISO** | 10 maggio 2024 | Il 7 giugno 2024 Adobe eseguirà gli aggiornamenti per l’area geografica ISO 2024. Con questa versione, sono previsti aggiornamenti minori relativi alle aree geografiche. |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.26.0), fare riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2024](/help/release-notes/2024.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione del componente aggiuntivo Streaming Media Collection](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
