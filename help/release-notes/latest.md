---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: e07f51764c6eeaccb56ce44df4a102e43fd44384
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 76%

---

# Note sulla versione corrente di Adobe Analytics (febbraio 2022)

**Ultimo aggiornamento**: 2 marzo 2022

Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html). Ottieni la documentazione, i tutorial e i corsi di supporto autonomo più recenti su Experience League.

## Nuove funzioni di Adobe Analytics {#aa-features}

| Funzione | Descrizione | [Data definita](releases.md) |
| ----------- | ---------- | ------- |
| Modalità anteprima dei progetti scorecard per dispositivi mobili | Avvia un’anteprima per vedere come si presenterà la scorecard per dispositivi mobili nell’app delle dashboard di Analytics, direttamente dal generatore di scorecard. La modalità di anteprima consente agli utenti di interagire con filtri e grafici nello stesso modo in cui farebbero nell’app, fornendo un’anteprima dell’esperienza prima di salvare e condividere la scorecard. Gli utenti possono inoltre utilizzare il selettore dispositivi in modalità anteprima per vedere come si presenterà la scorecard sui diversi dispositivi. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=it#preview) | 16 febbraio 2022 |
| Endpoint di progetti API | Aggiungi, modifica o elimina progetti Analysis Workspace utilizzando l’API. [Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/projects/) | 1° febbraio 2022 |

{style=&quot;table-layout:auto&quot;}

## Correzioni in Adobe Analytics

* Sono stati risolti diversi problemi relativi a [!UICONTROL Server call usage]. (AN-279134, AN-279878, AN-280802, AN-279097, AN-191284, AN-269720)
* È stato risolto un problema a causa del quale Data Warehouse esportava file .csv vuoti. (AN-280291)
* È stato risolto un problema che impediva il popolamento dei nomi dei tipi di pubblico per i segmenti recenti. (AN-279715)
* È stato risolto un problema relativo a tempi di reporting lenti. (AN-280055)
* Sono stati risolti dei problemi a causa dei quali le classificazioni non consideravano tutti gli elementi dimensionali. (AN-280031)

### Ulteriori correzioni in Adobe Analytics

AN-268093, AN-273820, AN-274435, AN-274904, AN-275356, AN-275947, AN-276160, AN-276258, AN-276705, AN-277051, AN-277957, AN-278693, AN-278882, AN-279000, AN-279046, AN-279362, AN-279460, AN-279488, AN-279554, AN-279572, AN-279663, AN-279755, AN-279825, AN-280002, AN-280013, AN-280019, AN-280033, AN-280086, AN-280232, AN-280264, AN-280288, AN-280342, AN-280347, AN-280360, AN-280370, AN-280724, AN-280830, AN-280941, AN-281353, AN-281424, AN-281533

## Avvisi importanti per [!DNL Analytics] amministratori

**Aggiornato il 2 marzo 2022**

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| Modifica del modo in cui Analytics gestisce i dati A4T raccolti tramite Experience Edge | 25 febbraio 2022 | On **7 marzo 2022**, verrà modificato il modo in cui vengono gestiti alcuni dati relativi a Target inviati ad Adobe Analytics tramite Experience Edge. Quando si utilizza Adobe Experience Platform Web SDK con Analytics e Target, sono stati conteggiati alcuni eventi di personalizzazione in [!DNL Adobe Analytics] come [!UICONTROL Page Views]. Ciò portava a conteggi gonfiati di visualizzazioni di pagina e chiamate server aggiuntive. Con il cambiamento, le chiamate di personalizzazione prive di contenuto Analytics verranno ignorate. Le chiamate di personalizzazione con dati A4T registreranno i dati A4T, ma non saranno registrate come chiamate al server fatturabili, né influiranno sulle visualizzazioni di pagina o sulle metriche degli eventi di collegamento. |
| Sospensione delle attività di Report Builder pianificate precedenti | 24 febbraio 2022 | **Attive dal 15 aprile 2022**, Adobe intende mettere in pausa tutte le attività di Report Builder pianificate create più di due anni fa. In particolare, questa pausa si applica alle attività create prima del 31 gennaio 2020. Non verranno eliminate attività, cartelle di lavoro o dati. Tuttavia, le attività identificate come più vecchie di due anni verranno messe in pausa e non verranno inviate altre attività pianificate. [Ulteriori informazioni](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Scadenza dell’estensione per inserire nell’elenco Consentiti EOL le integrazioni legacy di Analytics OAuth/JWT | 14 gennaio 2022 | Il **25 maggio 2022** scadrà l’estensione per l’elenco Consentiti di [API di Analytics 1.3, API SOAP 1.4 e del servizio obsoleto Legacy OAuth/JWT di Analytics](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md). Questo offriva ai clienti che utilizzano le credenziali OAuth/JWT legacy di [!DNL Adobe Analytics] ulteriore tempo per migrare le integrazioni client alle [credenziali Adobe IMS](https://developer.adobe.com/console). Questa scadenza riguarda (ma non è limitata a) i clienti [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] che non hanno completato le migrazioni IMS richieste. I clienti che attualmente utilizzano versioni precedenti delle credenziali OAuth/JWT [!DNL Analytics] tramite l’estensione per inserire nell’elenco Consentiti e che non completano la migrazione alle credenziali IMS entro il 25 maggio 2022 perderanno l’accesso ai servizi Adobe. I clienti di Livestream possono fare riferimento a queste [istruzioni](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) durante la migrazione delle applicazioni client alle credenziali IMS. I clienti [!DNL Campaign] possono contattare il proprio account team Adobe per informazioni sull’aggiornamento alla versione più recente di [!DNL Campaign]. |
| Fine del ciclo di vita per [!DNL Reports & Analytics] | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende terminare [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia su cui si basa [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |
| Aggiornamento dei servizi SFTP (Secure File Transfer Protocol) | 13 gennaio 2022 | Il **2 maggio 2022**, in [!DNL Adobe Analytics] verranno aggiornati i servizi SFTP (Secure File Transfer Protocol) per migliorare ulteriormente la sicurezza dei trasferimenti di file. Con questa modifica, alcune configurazioni client SFTP non saranno più supportate. Stiamo anche aggiungendo alcune opzioni di connessione che saranno disponibili entro il **1° marzo 2022**. Questo influisce solo sui dati inviati o recuperati da Adobe Analytics tramite SFTP. Il protocollo FTP non è interessato. Per evitare interruzioni del servizio, assicurati che i client SFTP (codice, strumenti, servizi) siano in linea con le modifiche descritte [qui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=it). |

## AppMeasurement {#appm}

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.22.4), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] note sulla versione](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
