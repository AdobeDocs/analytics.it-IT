---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 84f6bf068f56b9502a53ab17e71dca00356804d9
workflow-type: tm+mt
source-wordcount: '1122'
ht-degree: 64%

---

# Note sulla versione corrente di Adobe Analytics (ottobre/novembre 2023)

**Ultimo aggiornamento**: 25 ottobre 2023

Queste note sulla versione coprono il periodo di rilascio dal 23 ottobre 2023 alla fine di novembre 2023. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzionalità | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Miglioramenti di Reporting Activity Manager** | Il Reporting Activity Manager ti consente di visualizzare la capacità di reporting per ogni suite di rapporti della tua organizzazione.  Offre agli amministratori una visibilità dettagliata sul consumo di reporting per diagnosticare e risolvere facilmente i problemi di capacità durante i periodi in cui si verificano picchi di reporting. Di seguito sono riportati alcuni miglioramenti disponibili in Reporting Activity Manager: <ul><li>Limita richieste successive: oltre ad annullare le richieste correnti, gli amministratori possono ora limitare le richieste per un periodo di tempo definito. Gli amministratori possono limitare le richieste per richiesta, progetto e utente.</li><li>Oltre alle metriche Utilizzo e Capacità, Reporting Activity Manager ora include più dati sull&#39;attività di reporting: colonna Complessità, colonna Utente e colonna Connessione.</li><li>Tutte le cancellazioni e le restrizioni effettuate nel Reporting Activity Manager sono ora visibili nel Registro di controllo. Gli amministratori possono utilizzare il registro di controllo per visualizzare ciò che è attualmente annullato. Gli annullamenti non possono essere annullati nel Reporting Activity Manager o nel Registro di controllo.</li></ul><p>Per ulteriori informazioni, consulta [Panoramica di Reporting Activity Manager](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md)</p> | 17 ottobre 2023 | 24 ottobre 2023 |
| **Miglioramenti a Data Warehouse** | Durante la creazione di una richiesta Data Warehouse, ora puoi configurare un account cloud da utilizzare come destinazione del rapporto. Per l’invio dei dati sono disponibili i seguenti tipi di account cloud:<ul><li>Amazon S3</li><li>Piattaforma Google Cloud</li><li>SAS di Azure</li><li>RBAC di Azure</li><li>E-mail (opzione già disponibile in precedenza)</li></ul>FTP, SFTP, Azure Blob e S3 sono ancora disponibili come destinazioni di rapporti, ma non sono più consigliati.<p>È stata migliorata anche l’esperienza utente durante la creazione e la gestione delle richieste Data Warehouse. Per ulteriori informazioni, consulta [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md) e [Gestire le richieste Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-requests-manage.html?lang=it). | 12 settembre 2023 | Fino all’8 novembre 2023 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* Le modifiche al motore di elaborazione e reporting di Analytics verranno distribuite nell’ultima settimana di ottobre: verrà corretto un problema a causa del quale le etichette per le dimensioni Pagina o Collegamento non venivano visualizzate correttamente come `Unknown`. Prima della correzione, il `Unknown` Le etichette potrebbero non essere visualizzate correttamente quando un Nome pagina o un Nome collegamento non è stato trasmesso in un hit, impostazione predefinita [!UICONTROL Page URL] e [!UICONTROL Link URL], rispettivamente. Queste dimensioni sono state configurate per non fare distinzione tra maiuscole e minuscole. Con questa correzione, i rapporti in futuro saranno corretti. Tuttavia, per le segnalazioni di dati storici, alcuni risultati potrebbero ancora essere erroneamente etichettati come `Unknown`. (AN-328030)

### Altre correzioni

-315676; AN-; AN-323398; AN-326209; AN-328178; AN-328261; AN-328395; AN-328671; AN-329282; AN-329330; AN-329355; AN-329506; AN-329516; AN-329738; AN-329769; AN-329771; AN-329816; AN-329877; AN-329928; AN-329957; AN-329962; AN-329966; AN-330023; AN-330081; AN-330083; AN-330105; AN-330138; AN-330140; AN-330165; AN-330241; AN-330359; AN-330366; AN-330427; AN-330438; AN-330442; AN-330534; AN-330616; AN-330654; AN-330783; AN-330879; AN-330881; AN-330883; AN-330887; AN-330888; AN-330955; AN-330979; AN-331031; AN-331053; AN-331068; AN-331071; AN-331074; AN-331075; AN-331076; AN-331078; AN-331085; AN-331093; AN-331167; AN-331171; AN-331181; AN-331196; AN-331226; AN-331258; AN-331260; AN-331279; AN-331286; AN-331290; AN-331365; AN-331375; AN-331376; AN-331454; AN-331519; AN-331570; AN-331590; AN-331593; AN-331603; AN-331751; AN-331816; AN-331897; AN-331900; AN-331906; AN-331926; AN-331929; AN-332031; AN-332067; AN-332101; AN-332114; AN-332156; AN-332201; AN-332225; AN-332253; AN-332277; AN-332361; AN-332370; AN-332386

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Offuscamento IP completo per gli hit di Adobe Experience Edge** | 27 settembre 2023 | L’offuscamento dell’IP per gli hit provenienti da Experience Edge verrà aggiornato più tardi nel mese di ottobre 2023. Ad aprile 2023, Experience Edge ha aggiunto la possibilità di offuscare gli indirizzi IP. A quel tempo, Adobe Analytics supportava solo l’offuscamento parziale degli IP, a causa del modo in cui Analytics elabora gli hit da Experience Edge. Quando i clienti hanno scelto l’offuscamento completo per Experience Edge, Analytics ha ricevuto solo IP parzialmente offuscati. Quando questa modifica viene implementata, Analytics riceverà l’IP completamente offuscato. |
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
