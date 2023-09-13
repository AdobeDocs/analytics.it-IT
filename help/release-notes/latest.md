---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 2adc2ba45fb7ce740ff9dc9e376b60da7a84ea4e
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 68%

---

# Note sulla versione corrente di Adobe Analytics (settembre 2023)

**Ultimo aggiornamento**: 13 settembre 2023

Le note sulla versione di settembre coprono il periodo di rilascio dal 13 settembre 2023 al 3 ottobre 2023. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzionalità | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Classificazioni in API 2.0** | Fornisce metodi API 2.0 di Adobe Analytics per salvare, eliminare, recuperare, importare ed esportare set di dati di classificazione. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/) | N/D | 13 settembre 2023 |
| **Supporto per nuovi `correlationID` campo per le classificazioni A4T** | Il `_experience.decisioning.propositions.scopeDetails.correlationID` è ora disponibile nello schema del connettore di origine di Adobe Analytics. Stiamo aggiungendo questo ID per unire facilmente i dati di classificazione per le attività e gli eventi di esperienza di Adobe Target. | N/D | 13 settembre 2023 |
| **Miglioramenti a Data Warehouse** | Durante la creazione di una richiesta Data Warehouse, ora puoi configurare un account cloud da utilizzare come destinazione del rapporto. Per l’invio dei dati sono disponibili i seguenti tipi di account cloud:<ul><li>Amazon S3</li><li>Piattaforma Google Cloud</li><li>SAS di Azure</li><li>RBAC di Azure</li><li>E-mail (opzione precedentemente disponibile)</li></ul>FTP, SFTP, Azure Blob e S3 sono ancora disponibili come destinazioni dei rapporti, ma non sono più consigliati.<p>È stata migliorata anche l’esperienza utente durante la creazione e la gestione delle richieste Data Warehouse. Per ulteriori informazioni, consulta [Creare una richiesta Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/create-request/t-dw-create-request.html) e [Gestire le richieste Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=it). | 13 settembre 2023 | 4 ottobre 2023 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* È stato risolto un problema che impediva la visualizzazione dei dati di classificazione in Workspace. (AN-326827)

## Altre correzioni

AN-314882; AN-315591; AN-318165; AN-318559; AN-319031; AN-319244; AN-321657; AN-321759; AN-323099; AN-323596; AN-323640; AN-324442; AN-324921; AN-324953; AN-324977; AN-324979; AN-325124; AN-325395; AN-325433; AN-325535; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-325693; AN-325720; 325835 325880 325957 325984 326054 326065 326136 326155 326162 326235 326317 326344 326357 326359 326433 326438 326440 326461 326464 326523 326553 326606 326635 326642 326652 326678 326769 326777 326830 326938 326949 327081 327082 327085 327103 327198 327225 327275 327358 327423 327561 327755 327896 327922 328128 328300 328428 328518 328554; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| N/D | N/D | N/D |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fine del ciclo di vita per[!DNL Reports & Analytics]** | 7 marzo 2023 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita.<p>Il 31 dicembre 2023 termineremo molte delle funzioni associate a Reports &amp; Analytics, tra cui, a titolo esemplificativo: rapporti pianificati, estratti di dati e rapporti DL. Dopo il 31 dicembre 2023, tutti i rapporti pianificati non verranno più inviati. In entrata **Aprile 2023**, tutti i rapporti che dovevano scadere oltre il 31 dicembre 2023 sono stati aggiornati automaticamente e sono tornati a scadere il 31 dicembre 2023. Inoltre, non è più possibile pianificare rapporti futuri oltre il 31 dicembre 2023. |
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
