---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 29%

---

# Note sulla versione corrente di Adobe Analytics (gennaio 2024)

**Ultimo aggiornamento**: giovedì 10 gennaio 2024

Queste note sulla versione coprono il periodo da gennaio 2024 al 13 febbraio 2024. I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzionalità | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Data Warehouse aggiornamenti** | Sono ora disponibili i seguenti miglioramenti alle Date Warehouse:<ul><li>Durante la creazione di una richiesta Data Warehouse, gli utenti possono ora rendere le richieste disponibili a tutti gli utenti dell’organizzazione abilitando il nuovo interruttore denominato [!UICONTROL **Rendi disponibile agli utenti della tua organizzazione**].<p>Per ulteriori informazioni, consulta [Data Warehouse impostazioni generali della richiesta](/help/export/data-warehouse/create-request/dw-general-settings.md).</p></li><li>Durante la creazione o la gestione delle destinazioni dei rapporti di Data Warehouse, gli amministratori di sistema possono ora visualizzare gli account e le posizioni creati dagli utenti dell’organizzazione attivando l’interruttore denominato [!UICONTROL **Mostra tutte le destinazioni**].<p>Per ulteriori informazioni, consulta [Configurare una destinazione di rapporto per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).</p></li> | N/D | giovedì 10 gennaio 2024 |
| **Aggiornamenti alla visualizzazione Riepilogo delle metriche chiave** | Quando si utilizza la visualizzazione Riepilogo delle metriche chiave, l’intervallo di date del confronto può ora essere aggiornato automaticamente, a seconda che l’opzione di intervallo di date del confronto scelta sia relativa all’intervallo di date principale o fissa. [Ulteriori informazioni](/help/analyze/analysis-workspace/visualizations/key-metric.md). | N/D | giovedì 17 gennaio 2024 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* Sono stati risolti i seguenti problemi relativi alle classificazioni: AN-314821; AN-326839; AN-332079; AN-332704; AN-332812; AN-332902; AN-332975; AN-333300; AN-333023; AN-333033; AN-333174; AN-333910; AN-334097; AN-334208; AN-334373; AN-334439; AN-334698; AN-334838; AN-334848; AN-334987; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-AN; AN-S; AN; -; AN-335046 335082 335202 335203 335254 335322 335552 335591 335603 335610 335617 335699 335891 335901 336063 336072 336193 336479 336684 336801 337370 337398; AN-; AN-; AN-; AN-; AN-
* Sono stati risolti i seguenti problemi relativi al Generatore di regole di classificazione: AN-332390; AN-332573; AN-332718; AN-332927; AN-333248; AN-333953; AN-334647; AN-334736; AN-334910; AN-335642; AN-335683; AN-335811; AN-336033; AN-336569; AN-336852; AN-336875; AN-336902; AN-337190;
* Sono stati risolti i seguenti problemi di A4T: AN-334564; AN-336178;
* Sono stati risolti i seguenti problemi di utilizzo delle chiamate al server: AN-332568; AN-333105; AN-333167; AN-333983; AN-334209; AN-334278
* Sono stati risolti i seguenti problemi relativi alle Date Warehouse: AN-333010; AN-333076; AN-330227; AN-331580; AN-333350; AN-334291; AN-334283; AN-334287; AN-334301; AN-334385; AN-334453; AN-334977; AN-335079; AN-335171; AN-335245; AN-335426; AN-335680; AN-335818; AN-336087; AN-337308;
* Sono stati risolti i seguenti problemi relativi ai feed di dati: AN-332241; AN-332366; AN-332617; AN-332654; AN-332702; AN-332723; AN-333014; AN-333166; AN-334037; AN-334125; AN-334211; AN-334216; AN-334235; AN-334976; AN-335158; AN-335368; AN-335408; AN-335468; AN-335471; AN-335528; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; -; AN-335596 335662 335733 335883 335894 335968 336098 336192 336243 336659 336977 337117 337219 337262 337393 337462 337854
* Sono stati risolti i seguenti problemi di Report Builder: AN-335246; AN-336311;
* Sono stati risolti i seguenti problemi di Analysis Workspace: AN-323760; AN-324191; AN-324913; AN-330126; AN-332808; AN-333168; AN-333382; AN-334839; AN-336040; AN-337043;

### Altre correzioni

AN-323975; AN-325383; AN-325809; AN-326787; AN-331611; AN-331818; AN-332124; AN-332272; AN-332911; AN-333070; AN-333302; AN-333377; AN-333904; AN-333928; AN-333968; AN-334056; AN-334099; AN-334191; AN-334207; AN-334776 335206 335294 335320 335394 335443 335967 336099 337452 337463; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-; AN-

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| Adobe di aggiunte di membri oggetto API | giovedì 17 gennaio 2024 | Adobe può aggiungere membri di richiesta e risposta facoltativi (coppie nome/valore) agli oggetti API esistenti senza preavviso o modifiche nel controllo delle versioni. Tali aggiunte devono essere modifiche introduttive per l’implementazione. L’Adobe consiglia di fare riferimento alla documentazione API di qualsiasi strumento di terze parti integrato con le nostre API, in modo che tali aggiunte, se non comprese, vengano ignorate durante l’elaborazione. Adobe non rimuove parametri né aggiunge parametri richiesti senza prima fornire una notifica standard tramite le note sulla versione. |
| `getPageLoadTime` plug-in obsoleto | giovedì 10 gennaio 2024 | Questo plug-in non è più supportato. Il suo codice utilizza il metodo performance.timing, che (secondo MDN) è stato [obsoleto](https://developer.mozilla.org/en-US/docs/Web/API/PerformanceTiming). Il lavoro su un plug-in aggiornato è stato avviato. |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Fine del ciclo di vita per[!DNL Reports & Analytics]** | giovedì 10 gennaio 2024 | Effettivo **17 gennaio 2024**, Adobe interrotto [!DNL Reports & Analytics] e i relativi rapporti e funzioni. Rapporti, visualizzazioni e tecnologia di base utilizzati [!DNL Reports & Analytics] non soddisfa più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita.<p>Il 17 gennaio 2024 sono state terminate molte delle funzioni di Reports &amp; Analytics associate, tra cui, a titolo esemplificativo: rapporti pianificati, estratti di dati e rapporti DL. Dopo il 17 gennaio 2024, tutti i rapporti pianificati non sono più stati inviati. Inoltre, non è più possibile pianificare rapporti futuri a partire dal 17 gennaio 2024. |
| **Fine del ciclo di vita della [!UICONTROL Publishing Lists] caratteristica** | giovedì 10 gennaio 2024 | Come parte della fine del ciclo di vita di Reports &amp; Analytics, [!UICONTROL Publishing Lists] ha raggiunto la fine del ciclo di vita il **17 gennaio 2024**. Non puoi più creare nuovi utenti o accedere a quelli esistenti [!UICONTROL Publishing Lists] per inviare o pianificare [!UICONTROL Analysis Workspace] progetti. |
| **Fine del ciclo di vita per Data Workbench** | mercoledì 2 gennaio 2024 | Adobe fine del ciclo di Data Workbench effettivo **31 dicembre 2023**. Vedi [Annuncio della fine del ciclo di vita di Data Workbench](https://express.adobe.com/page/GSu6oKOD88GAj/) per i dettagli. Per qualsiasi domanda, contatta l’Adobe Account Manager della tua organizzazione. |
| **Migrazione alle credenziali server-to-server OAuth di Adobe I/O** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server OAuth di AdobeIO entro il **1° gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.25.0), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2023](/help/release-notes/2023.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
