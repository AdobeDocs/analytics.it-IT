---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d9892291d5386c3faaec0da06084a1ce7695a78a
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 53%

---

# Note sulla versione corrente di Adobe Analytics (marzo 2022)

>[!IMPORTANT]
>
>Il contenuto seguente contiene informazioni precedenti al rilascio ed è soggetto a modifiche.

* For February 2022 release notes, go [here](/help/release-notes/2022.md).
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html). Ottieni la documentazione, i tutorial e i corsi di supporto autonomo più recenti su Experience League.

## Nuove funzioni di Adobe Analytics {#aa-features}

| Funzione | Descrizione | [Data definita](releases.md) |
| ----------- | ---------- | ------- |
| Annotazioni in Workspace | Annotations in Workspace enable you to effectively communicate contextual data nuances and insights to your organization. [Ulteriori informazioni](/help/analyze/analysis-workspace/components/annotations/overview.md) | 23 marzo 2022 |
| Aggiornamenti delle pagine di destinazione di Adobe Analytics | Aggiornamenti alla pagina di destinazione congiunta Workspace/Reports &amp; Analytics che migliorano l’usabilità e la facilità di navigazione. [Ulteriori informazioni](/help/analyze/landing.md) | Da definire |

{style=&quot;table-layout:auto&quot;}

## Correzioni in Adobe Analytics

* Fixed an issue that resulted in an error when trying to access Activity Map. (AN-267177)
* È stato risolto un problema relativo ai trasferimenti di risorse utente non riusciti. (AN-279813)
* Fixed issues with the A4T Workspace panel. (AN-281594; AN-282418)
* È stato risolto un problema che impediva ad alcuni utenti di accedere ad Adobe Analytics. (AN-282776)
* Sono stati risolti dei problemi a causa dei quali alcune suite di rapporti appena create non raccoglievano dati. (AN-283114, AN-283311)
* Sono stati risolti dei problemi che impedivano il rilevamento di Win11 utilizzando la dimensione Sistema operativo . (AN-275569, AN-275727; (AN-280335)
* Sono stati risolti i problemi relativi alle e-mail dei feed di dati inviate in modo errato. (AN-280255; AN-282051)


### Ulteriori correzioni in Adobe Analytics

AN-256929; AN-270937; AN-272158; AN-275130; AN-277830; AN-278635; AN-279066; AN-279683; AN-279899; AN-280504; AN-280617; AN-280663; AN-281423; AN-281523; AN-281608; AN-281671; AN-281963; AN-282027; AN-282218; AN-282593; AN-282605; AN-282632; AN-282654; AN-282694; AN-282744; AN-282756; AN-282804; AN-282838; AN-282862; AN-282903; AN-282937; AN-282892; AN-283315; AN-283338; AN-283388; AN-283417; AN-283474; AN-283511; AN-283691, AN-283895; AN-283943; AN-283957; AN-284030; AN-284100; AN-284142; AN-284162

## Important notices for Adobe Analytics administrators

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| Sospensione dei rapporti pianificati meno recenti | 11 marzo 2022 | Efficace **15 aprile 2022**, Adobe intende mettere in pausa tutti i rapporti pianificati con una data di creazione maggiore di due anni (creati prima del 31 gennaio 2020). Nessun rapporto o dato verrà eliminato. Verranno messi in pausa solo i rapporti identificati come più vecchi di due anni e non verranno inviati ulteriori rapporti pianificati. [Ulteriori informazioni](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| Aggiornamenti per l’area geografica ISO 2022 | 11 marzo 2021 | Adobe eseguirà gli aggiornamenti di 2022 per l’area ISO su **10 giugno 2022**. Dopo questa versione, sono previsti aggiornamenti meno frequenti. |
| Modifica del modo in cui Analytics gestisce i dati A4T raccolti tramite Experience Edge | 25 febbraio 2022 | On **March 7th, 2022**, we changed how we handle some Target-related data sent to Adobe Analytics via Experience Edge. When using the Adobe Experience Platform Web SDK with Analytics and Target, some personalization events were counted in [!DNL Adobe Analytics] as [!UICONTROL Page Views]. Ciò portava a conteggi gonfiati di visualizzazioni di pagina e chiamate server aggiuntive. Con questo cambiamento, le chiamate di personalizzazione senza contenuti di Analytics non vengono prese in considerazione. Le chiamate di personalizzazione con dati A4T registreranno i dati A4T, ma non saranno registrate come chiamate al server fatturabili, né influiranno sulle visualizzazioni di pagina o sulle metriche degli eventi di collegamento. |
| Sospensione delle attività di Report Builder pianificate precedenti | 24 febbraio 2022 | **Effective April 15, 2022**, Adobe intends to pause all scheduled Report Builder tasks that were created more than two years ago. In particolare, questa pausa si applica alle attività create prima del 31 gennaio 2020. Non verranno eliminate attività, cartelle di lavoro o dati. However, tasks identified as older than two years will be paused, and no additional scheduled tasks will be sent. [Ulteriori informazioni](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| Scadenza dell’estensione per inserire nell’elenco Consentiti EOL le integrazioni legacy di Analytics OAuth/JWT | 14 gennaio 2022 | Il **25 maggio 2022** scadrà l’estensione per l’elenco Consentiti di [API di Analytics 1.3, API SOAP 1.4 e del servizio obsoleto Legacy OAuth/JWT di Analytics](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/APIEOL.md). Questo offriva ai clienti che utilizzano le credenziali OAuth/JWT legacy di [!DNL Adobe Analytics] ulteriore tempo per migrare le integrazioni client alle [credenziali Adobe IMS](https://developer.adobe.com/console). Questa scadenza riguarda (ma non è limitata a) i clienti [!DNL Adobe Analytics Livestream] e [!DNL Adobe Campaign] che non hanno completato le migrazioni IMS richieste. I clienti che attualmente utilizzano versioni precedenti delle credenziali OAuth/JWT [!DNL Analytics] tramite l’estensione per inserire nell’elenco Consentiti e che non completano la migrazione alle credenziali IMS entro il 25 maggio 2022 perderanno l’accesso ai servizi Adobe. I clienti di Livestream possono fare riferimento a queste [istruzioni](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) durante la migrazione delle applicazioni client alle credenziali IMS. I clienti [!DNL Campaign] possono contattare il proprio account team Adobe per informazioni sull’aggiornamento alla versione più recente di [!DNL Campaign]. |
| Aggiornamento dei servizi SFTP (Secure File Transfer Protocol) | 3 marzo 2022 | Il **15 maggio 2022**, in [!DNL Adobe Analytics] verranno aggiornati i servizi SFTP (Secure File Transfer Protocol) per migliorare ulteriormente la sicurezza dei trasferimenti di file. Con questa modifica, alcune configurazioni client SFTP non saranno più supportate. Stiamo anche aggiungendo alcune opzioni di connessione che saranno disponibili entro il **1° marzo 2022**. Questo influisce solo sui dati inviati o recuperati da Adobe Analytics tramite SFTP. Il protocollo FTP non è interessato. Per evitare interruzioni del servizio, assicurati che i client SFTP (codice, strumenti, servizi) siano in linea con le modifiche descritte [qui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=it). |
| Fine del ciclo di vita per [!DNL Reports & Analytics] | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende terminare [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia su cui si basa [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

## AppMeasurement {#appm}

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.22.4), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).

>[!MORELIKETHIS]
>[[!DNL Customer Journey Analytics] note sulla versione](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
