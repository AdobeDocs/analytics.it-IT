---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 991c46091d08a3efa8c1ff90d6ccc2a4e698f208
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 92%

---

# Note sulla versione corrente di Adobe Analytics (agosto 2023)

**Ultimo aggiornamento**: 29 agosto 2023

Queste note sulla versione coprono il periodo dal 9 agosto al 13 settembre 2023. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzionalità | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Set di classificazione nell’API 2.0** | Fornisce metodi API 2.0 di Adobe Analytics per salvare, eliminare, recuperare, importare ed esportare set di dati di classificazione. | N/D | 13 settembre 2023 |
| **Reporting Activity Manager** | Il Reporting Activity Manager offre agli amministratori una visibilità dettagliata sul consumo di reporting per ogni suite di rapporti, consentendo agli amministratori di diagnosticare e risolvere facilmente i problemi di capacità durante i periodi in cui si verificano picchi di reporting. [Ulteriori informazioni](/help/admin/admin/reporting-activity.md) | N/D | 12 settembre 2023 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* È stato risolto un problema che impediva il caricamento degli eventi personalizzati. (AN-324163)
* È stato risolto un problema che impediva la modifica delle etichette per le legende riportate in una visualizzazione. (AN-323246)

AN-315605; AN-316306; AN-317494; AN-317844; AN-320424; AN-320597; AN-320680; AN-320869; AN-321624; AN-321693; AN-322009; AN-322244; AN-322380; AN-322432; AN-322466; AN-322556; AN-322669; AN-322735; AN-323151; AN-323220; AN-323380; AN-323492; AN-323595; AN-323755; AN-323854; AN-323916; AN-324044; AN-324200; AN-324213; AN-324238; AN-324347; AN-323598; AN-323625; AN-323631; AN-323638; AN-323641; AN-323755; AN-323767; AN-323777; AN-323825; AN-323846; AN-323972; AN-324113; AN-324170; AN-324197; AN-324273; AN-324275; AN-324345; AN-324384; AN-324433; AN-324511; AN-324513; AN-324521; AN-324524; AN-324531; AN-324532; AN-324534; AN-324537; AN-324569; AN-324618; AN-324635; AN-324688; AN-324704; AN-324712; AN-324721; AN-324745; AN-324792; AN-324793; AN-324794; AN-324795; AN-324824; AN-324905; AN-324918; AN-324932; AN-324934; AN-324947; AN-325003; AN-325073; AN-325143; AN-325148; AN-325153; AN-325177; AN-325187; AN-325252; AN-325305; AN-325363; AN-325401; AN-325439; AN-325431; AN-325491; AN-325495; AN-325508; AN-325594; AN-325601; AN-325660; AN-325779; AN-325857; AN-325883; AN-325885; AN-325886


## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza a 37 mesi degli ID acquisto e degli ID evento (serializzazione degli eventi)** | Luglio 10,2023 | Ultima versione del motore di elaborazione degli hit di Analytics, rilasciata il **13 luglio 2023**, ha iniziato ad applicare una scadenza di 37 mesi per gli ID acquisto e gli ID evento (serializzazione degli eventi). In precedenza, gli ID acquisto e gli ID evento non scadevano mai in Adobe Analytics. Una volta visualizzato/utilizzato un ID acquisto o un ID evento, qualsiasi hit futuro, indipendentemente da quando, ha contrassegnato l’acquisto o l’evento come duplicato. Con la nuova versione del motore di elaborazione:<ul><li>gli ID acquisto e gli ID evento scadono sempre dopo 37 mesi.</li><li>Se sono trascorsi 37 mesi dalla visualizzazione dell’ID acquisto o dell’ID evento, questo non viene più considerato un acquisto o un evento duplicato.</li><li> Se si stanno “riutilizzando” gli ID acquisto o gli ID evento da più di 37 mesi, questi non vengono più considerati duplicati.</li></ul> |
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
