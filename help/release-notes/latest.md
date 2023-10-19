---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 69cffe2bc97a81cb9e4b989f2193dc2deb6e8d22
workflow-type: tm+mt
source-wordcount: '1228'
ht-degree: 51%

---

# Note sulla versione corrente di Adobe Analytics (ottobre 2023)

**Ultimo aggiornamento**: 19 ottobre 2023

Le note sulla versione di ottobre coprono il periodo di rilascio dal 4 ottobre 2023 al 25 ottobre 2023. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzionalità | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Sono disponibili nuove colonne per la gestione dei componenti** | Durante la gestione dei componenti sono ora disponibili le seguenti nuove colonne:<ul><li>Utilizzato in<p>Questa colonna è disponibile nel [Gestione metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) e [Gestore segmenti](/help/components/segmentation/segmentation-workflow/seg-manage.md).</p></li><li>Ultimo utilizzo<p>Questa colonna è disponibile nel [Gestione metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md), il [Gestore segmenti](/help/components/segmentation/segmentation-workflow/seg-manage.md)e [Gestione avvisi](/help/components/c-alerts/alert-manager.md).</p></li></ul><p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato. Puoi utilizzare il dizionario dati insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell’organizzazione e per comprenderne meglio il funzionamento.</p> | 20 settembre 2023 | 4 ottobre 2023 |
| **Miglioramenti di Reporting Activity Manager** | Il Reporting Activity Manager ti consente di visualizzare la capacità di reporting per ogni suite di rapporti della tua organizzazione.  Offre agli amministratori una visibilità dettagliata sul consumo di reporting per diagnosticare e risolvere facilmente i problemi di capacità durante i periodi in cui si verificano picchi di reporting. Di seguito sono riportati alcuni miglioramenti disponibili in Reporting Activity Manager: <ul><li>Limita richieste successive: oltre ad annullare le richieste correnti, gli amministratori possono ora limitare le richieste per un periodo di tempo definito. Gli amministratori possono limitare le richieste per richiesta, progetto e utente.</li><li>Oltre alle metriche Utilizzo e Capacità, Reporting Activity Manager ora include più dati sull&#39;attività di reporting: colonna Complessità, colonna Utente e colonna Connessione.</li><li>Tutte le cancellazioni e le restrizioni effettuate nel Reporting Activity Manager sono ora visibili nel Registro di controllo. Gli amministratori possono utilizzare il registro di controllo per visualizzare ciò che è attualmente annullato. Gli annullamenti non possono essere annullati nel Reporting Activity Manager o nel Registro di controllo.</li></ul><p>Per ulteriori informazioni, consulta [Panoramica di Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | 17 ottobre 2023 | 24 ottobre 2023 |
| **Miglioramenti a Data Warehouse** | Durante la creazione di una richiesta Data Warehouse, ora puoi configurare un account cloud da utilizzare come destinazione del rapporto. Per l’invio dei dati sono disponibili i seguenti tipi di account cloud:<ul><li>Amazon S3</li><li>Piattaforma Google Cloud</li><li>SAS di Azure</li><li>RBAC di Azure</li><li>E-mail (opzione già disponibile in precedenza)</li></ul>FTP, SFTP, Azure Blob e S3 sono ancora disponibili come destinazioni di rapporti, ma non sono più consigliati.<p>È stata migliorata anche l’esperienza utente durante la creazione e la gestione delle richieste Data Warehouse. Per ulteriori informazioni, consulta [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) e [Gestire le richieste Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=it). | 12 settembre 2023 | Fino all’8 novembre 2023 |
| **Migra al Customer Journey Analytics i progetti Adobe Analytics ed eventuali componenti inclusi** | Ora puoi migrare i progetti Adobe Analytics al Customer Journey Analytics. Questo processo semplifica la transizione da Adobe Analytics a Customer Journey Analytics. <p>Quando esegui la migrazione dei progetti al Customer Journey Analytics, le risorse vengono mappate da una suite di rapporti di Adobe Analytics a una visualizzazione dati del Customer Journey Analytics.</p> <p>Esegui la migrazione dei progetti al Customer Journey Analytics dall’interfaccia di Adobe Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)</p> | N/D | 9 ottobre 2023 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* Sono stati risolti dei problemi a causa dei quali i rapporti A4T non venivano visualizzati nell’interfaccia utente di Target/Analytics. (AN-329375, AN-329745, AN-330026)

AN-313983; AN-324189; AN-325095; AN-325677; AN-325886; AN-326068; AN-326360; AN-326458; AN-327290; AN-327315; AN-327353; AN-327505; AN-327589; AN-327609; AN-327922; AN-328110; AN-328222; AN-328261; AN-328496; AN-328577; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-328629; AN-328736; 328888 328899 328902 328921 328958 329208 329277 329332 329334 329335 329336 329357 329385 329387 329397 329463 329501 329504 329505 329515 329524 329526 329534 329539 329541 329543 329545 329564 329570 329623 329624 329636 329646 329647 329668 329701 329737 329741 329751 329812 329813 329821 329824 329833 329848 329852 329861 329863 329874 329882 329911 329917 329942 329954 329968 329971 329982 330044 330052 330131 330132 330230 330352 330367 330541 330599; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Offuscamento IP completo per gli hit di Adobe Experience Edge** | 27 settembre 2023 | L’offuscamento dell’IP per gli hit provenienti da Experience Edge verrà aggiornato più tardi nel mese di ottobre 2023. In aprile, Experience Edge ha aggiunto la possibilità di oscurare gli indirizzi IP. A quel tempo, Adobe Analytics supportava solo l’offuscamento parziale degli IP, a causa del modo in cui Analytics elabora gli hit da Experience Edge. Quando i clienti hanno scelto l’offuscamento completo per Experience Edge, Analytics ha ricevuto solo IP parzialmente offuscati. Quando questa modifica viene implementata, Analytics riceverà l’IP completamente offuscato. |
| **Adobe Analytics Livestream - API di Analytics 2.0** | 27 settembre 2023 | I clienti ora possono accedere alla [Guida all’endpoint per Adobe Analytics Livestream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/) nelle API di Adobe Analytics 2.0 invece della posizione precedente, con le API 1.4. I clienti che utilizzano le credenziali JWT Adobe I/O devono effettuare la migrazione alle credenziali server-to-server Adobe I/O OAuth entro il 1° gennaio 2025. (Vedi i dettagli nella sezione Avvisi di fine del ciclo di vita riportati di seguito.) |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fine del ciclo di vita per[!DNL Reports & Analytics]** | 7 marzo 2023 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita.<p>Il 31 dicembre 2023 termineremo molte delle funzioni associate a Reports &amp; Analytics, tra cui, a titolo esemplificativo: rapporti pianificati, estratti di dati e rapporti DL. Dopo il 31 dicembre 2023, tutti i rapporti pianificati non verranno più inviati. Ad **aprile 2023**, tutti i rapporti, la cui scadenza era stata pianificata dopo il 31 dicembre 2023, verranno automaticamente aggiornati con scadenza il 31 dicembre 2023. Inoltre, non è più possibile pianificare rapporti futuri oltre il 31 dicembre 2023. |
| **Fine del ciclo di vita della [!UICONTROL Publishing Lists] caratteristica** | 29 settembre 2022 | Come parte della fine del ciclo di vita di Reports &amp; Analytics, gli [!UICONTROL Publishing Lists] sono destinati a raggiungere la fine del ciclo di vita a **dicembre 2023**. Non sarà possibile creare nuovi [!UICONTROL Publishing Lists] o accedere a quelli esistenti per inviare o pianificare progetti di [!UICONTROL Analysis Workspace]. |
| **Fine del ciclo di vita per Data Workbench** | 14 settembre 2022 | Adobe intende terminare il ciclo di vita di Data Workbench a partire dal **31 dicembre 2023**. Vedi [Annuncio della fine del ciclo di vita di Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=it) per i dettagli. Per qualsiasi domanda, contatta l’Adobe Account Manager della tua organizzazione. |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.25.0), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
