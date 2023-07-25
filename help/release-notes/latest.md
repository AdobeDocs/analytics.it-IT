---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: f996448224ffebd57023c8d8e4eeeccb4d6e2a47
workflow-type: ht
source-wordcount: '912'
ht-degree: 100%

---

# Note sulla versione corrente di Adobe Analytics (luglio 2023)

**Ultimo aggiornamento**: 10 luglio 2023

I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Configurare le posizioni di archiviazione di account cloud per l’acquisizione dei dati di classificazione** | Ora puoi gestire le posizioni di archiviazione di account cloud utilizzate per l’automazione dei set di classificazione. [Ulteriori informazioni](/help/components/locations/configure-import-accounts.md)<p> | N/D | 10 luglio 2023 |
| **Miglioramenti alle operazioni di filtro per Data Repair** | Sono stati aggiunti tre miglioramenti alle operazioni di filtro per Data Repair:<ul><li>Filtrare per una variabile al fine di modificare una seconda variabile. Esempio: se `eVar2` contiene “@”, elimina `eVar3`.</li><li>Filtrare per valori numerici o non numerici</li><li>Applicare più filtri con un operatore AND. Esempio: dove `eVar2="a"` AND `eVar3="b"`</li></ul>[Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 21 giugno 2023 | 12 luglio 2023 |
| **Destinazioni sicure per l’esportazione di feed di dati** | I feed di dati ora possono essere inviati alle seguenti destinazioni di archiviazione cloud:<ul><li>Amazon S3</li><li>RBAC di Azure</li><li>SAS di Azure</li><li>Piattaforma Google Cloud</li></ul>Le destinazioni precedentemente disponibili (FTP, SFTP, S3 e Azure Blob) non sono più consigliate. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=it) | 12 giugno 2023 | 13 luglio 2023 |
| **Nuova variabile AppMeasurement** | La variabile `decodeLinkParameters` gestisce i casi edge in cui le implementazioni codificano caratteri multibyte nelle variabili di tracciamento dei collegamenti. La maggior parte delle implementazioni non ha bisogno di definire questa variabile. [Ulteriori informazioni](../implement/vars/config-vars/decodelinkparameters.md) |  | 17 luglio 2023 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

AN-307816; AN-318111; AN-318584; AN-318828; AN-320440; AN-320568; AN-320616; AN-321013; AN-321513; AN-321520; AN-321757; AN-321820; AN-321917; AN-322034; AN-322135; AN-322140; AN-322142; AN-322251; AN-322353; AN-322378; AN-322383; AN-322427; AN-322458; AN-322543; AN-322630; AN-322637; AN-322638; AN-322647; AN-322728; AN-322732; AN-322777; AN-322817; AN-322957; AN-322958; AN-323035; AN-323074; AN-323150; AN-323196; AN-323197; AN-323205; AN-323206; AN-323217; AN-323224; AN-323225; AN-323244; AN-323257; AN-323277; AN-323280; AN-323293; AN-323309; AN-323318; AN-323468; AN-323476; AN-323514; AN-323572; AN-323592; AN-323782; AN-323835

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza a 37 mesi degli ID acquisto e degli ID evento (serializzazione degli eventi)** | Luglio 10,2023 | Una prossima versione del motore di elaborazione degli hit di Analytics, destinata al rilascio il **13 luglio 2023**, inizierà ad applicare di una scadenza a 37 mesi agli ID acquisto e agli ID evento (serializzazione degli eventi). Attualmente, in Adobe Analytics, gli ID acquisto e gli ID evento non scadono mai. Una volta visualizzato/utilizzato un ID acquisto o un ID evento, qualsiasi hit futuro, indipendentemente da quando, avrà tale acquisto o evento contrassegnato come duplicato. Con la nuova versione del motore di elaborazione:<ul><li>gli ID acquisto e gli ID evento scadono sempre dopo 37 mesi.</li><li>Se sono trascorsi 37 mesi dalla visualizzazione dell’ID acquisto o dell’ID evento, questo non viene più considerato un acquisto o un evento duplicato.</li><li> Se si stanno “riutilizzando” gli ID acquisto o gli ID evento da più di 37 mesi, questi non vengono più considerati duplicati.</li></ul> |
| **Migrazione alle credenziali server-to-server AdobeIO OAuth** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di Adobe I/O devono effettuare la migrazione alle credenziali server-to-server di Adobe I/O OAuth entro il **1° gennaio 2025**. Per ulteriori dettagli e tempistiche, consulta l’avviso di fine del ciclo di vita nella tabella seguente. |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fine del ciclo di vita per[!DNL Reports & Analytics]** | 7 marzo 2023 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita.<p>Il 31 dicembre 2023 termineremo molte delle funzioni associate a Reports &amp; Analytics, tra cui, a titolo esemplificativo: rapporti pianificati, estratti di dati e rapporti DL. Dopo il 31 dicembre 2023, tutti i rapporti pianificati non verranno più inviati. In **Aprile 2023**, tutti i rapporti la cui scadenza era prevista dopo il 31 dicembre 2023 verranno automaticamente aggiornati con scadenza il 31 dicembre 2023. Inoltre, non è più possibile pianificare rapporti futuri oltre il 31 dicembre 2023. |
| **Fine del ciclo di vita della [!UICONTROL Publishing Lists] caratteristica** | 29 settembre 2022 | Come parte della fine del ciclo di vita di Reports &amp; Analytics, gli [!UICONTROL Publishing Lists] sono destinati a raggiungere la fine del ciclo di vita a **dicembre 2023**. Non sarà possibile creare nuovi [!UICONTROL Publishing Lists] o accedere a quelli esistenti per inviare o pianificare progetti di [!UICONTROL Analysis Workspace]. |
| **Fine del ciclo di vita per Data Workbench** | 14 settembre 2022 | Adobe intende terminare il ciclo di vita di Data Workbench a partire dal **31 dicembre 2023**. Vedi [Annuncio della fine del ciclo di vita di Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=it) per i dettagli. Per qualsiasi domanda, contatta l’Adobe Account Manager della tua organizzazione. |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.24.0), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
