---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 903139cdc11770f035ca36911c0d5dbf778c62be
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 100%

---

# Note sulla versione corrente di Adobe Analytics (agosto 2022)

**Ultimo aggiornamento**: 12 agosto 2022

## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it) 
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)

## Funzioni nuove o aggiornate in Adobe Analytics

| Funzione | Descrizione | [Data definita](releases.md) |
| ----------- | ---------- | ------- |
| Nessuna nuova funzionalità questo mese |  |  |

{style=&quot;table-layout:auto&quot;}

## Correzioni in Adobe Analytics

* Sono stati risolti diversi problemi relativi ai feed di dati. (AN-297264, AN-297295, AN-297449)

**Correzioni per singoli clienti**:

AN-274281; AN-280956; AN-285670; AN-288176; AN-289221; AN-289665; AN-289768; AN-294632; AN-294970; AN-295078; AN-295233; AN-295482; AN-295549; AN-295633; AN-295712; AN-295749; AN-295963; AN-295977; AN-296094; AN-296153; AN-296167; AN-296177; AN-296297; AN-296383; AN-296394; AN-296414; AN-296431; AN-296459; AN-296486; AN-296510; AN-296514; AN-296540; AN-296734; AN-296840; AN-296841; AN-296977; AN-296987; AN-297002; AN-297141; AN-297158; AN-297267; AN-297396; AN-297397; AN-297522; AN-297704; AN-297705; AN-297829; AN-297895;

## Avvisi importanti per gli amministratori di Adobe Analytics

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Aggiornamento SFTP** | 12 agosto 2022 | In precedenza, avevamo comunicato che Adobe avrebbe aggiornato i servizi SFTP (Secure File Transfer Protocol) nel maggio 2022 per garantire una maggiore sicurezza nel trasferimento di file. Questo aggiornamento è stato posticipato al **7 settembre 2022**. Quando questa modifica verrà implementata, alcune configurazioni client SFTP non saranno più supportate. Questo influisce solo sui dati inviati o recuperati da Adobe Analytics tramite SFTP. Il protocollo FTP non è interessato. Per evitare interruzioni del servizio, assicurati che i client SFTP (codice, strumenti, servizi) siano in linea con le modifiche descritte [qui](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/sftp-upgrade.html?lang=it). |
| **Aggiornamento al nuovo database di gestori NetAcuity** | 11 luglio 2022 | **A partire da ottobre 2022**, cambieranno le informazioni relative al gestore memorizzate nel campo `carrier` in Adobe Analytics Data Warehouse e nei feed di dati di Analytics. Storicamente, il formato dei dati di tale colonna era `<domain>:<ISP>`. Adobe ha mantenuto una tabella di ricerca interna per mappare questi valori `<domain>:<ISP>` sui nomi dei gestori a scopo di reporting negli strumenti di reporting di Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API di reporting, data warehouse, LiveStream, ecc.). Il file di ricerca (`carrier.tsv`) viene fornito anche con feed di dati in modo che chi utilizza i feed di dati possa usare le stesse mappature.<p>Questo aggiornamento migliora le mappature dei gestori utilizzando un database più accurato da NetAcuity. Il formato dei dati nella colonna dei gestori nei feed di dati cambierà in futuro. Invece di `<domain>:<ISP>`, conterrà un nome di gestore. Adobe continuerà a utilizzare la tabella di ricerca per mantenere la massima continuità possibile con il precedente reporting. Gli strumenti di reporting in cui le ricerche vengono applicate da Adobe (Analysis Workspace, Reports &amp; Analytics, API di reporting, data warehouse, LiveStream, ecc.) trarranno vantaggio da mappature più precise. Alcune mappature, soprattutto per i domini internazionali e gli ISP, cambieranno più di altre quando adotteremo il nuovo database. Nel file di ricerca dei gestori dei feed di dati (`carrier.tsv`) verranno mantenute le vecchie mappature e verranno aggiunte nuove mappature.<p>Il connettore di origine di Analytics non mappa attualmente il campo del gestore (carrier), pertanto il reporting sui gestori non è attualmente disponibile in AEP, CJA, ecc. L’utilizzo del nuovo database di gestori non avrà quindi alcun impatto in AEP in quanto si basa sui dati forniti dal connettore di origine di Analytics. |
| **Mappatura IP-geolocalizzazione migliorata** | 11 luglio 2022 | Il nostro fornitore di ricerche IP, Digital Element, sta effettuando l’aggiornamento a un nuovo set di dati migliorato (NetAcuity Pulse) per la mappatura IP-geolocalizzazione. Adobe Analytics adotterà questo nuovo set di dati nel periodo di **ottobre 2022**. Il nuovo database sarà più accurato delle versioni precedenti. Quando il nuovo database verrà adottato, alcune mappature IP-geolocalizzazione verranno modificate/migliorate.<p>Tutti gli strumenti di Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API di reporting, data warehouse, LiveStream, feed di dati, ecc.) sfrutteranno automaticamente le nuove mappature migliorate. Non vi saranno modifiche nel formato dei dati nei feed di dati. Anche i dati CJA forniti tramite il connettore di origine di Analytics sfrutteranno automaticamente le nuove mappature. |
| **Sospensione dei rapporti pianificati in Reports &amp; Analytics** | 8 giugno 2022 | Il 21 aprile 2022 è stata annunciata la rimozione di diverse funzioni specifiche dei rapporti pianificati in preparazione della scadenza del ciclo di vita di Reports &amp; Analytics, precedentemente annunciata. Queste funzionalità includevano la possibilità di pianificare nuovi rapporti e nuovi estratti di dati.<p>In risposta alle richieste dei clienti che richiedono un’estensione e per facilitare la transizione da Reports and Analytics, abbiamo deciso di estendere l’accesso a queste funzioni fino al **31 gennaio 2023**. Si prega di notare che le scadenze per i rapporti e gli estratti dei dati continueranno a essere limitate a nove mesi; la consegna del report e dell’estrazione dei dati verrà sospesa alla fine di questo periodo, a meno che la pianificazione non venga riattivata.<p>Per ribadire questo punto, queste funzioni verranno rese obsolete il 31 gennaio 2023. Prima di questa data, devi migrare i rapporti pianificati in uno degli altri meccanismi disponibili in Adobe Analytics. Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe. [Ulteriori informazioni](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Sospensione delle attività pianificate nel Report Builder** | 8 giugno 2022 | Il 21 aprile 2022 sono state implementate modifiche alle attività pianificate in Report Builder nell’ambito delle attività di ottimizzazione delle prestazioni e della consegna. Tali modifiche includevano la rimozione della possibilità che le consegne pianificate avessero “termine dopo x occorrenze”. In risposta a diverse richieste dei clienti che necessitano di più tempo per esplorare e implementare alternative, abbiamo deciso di ripristinare questa opzione in modo limitato fino al **31 gennaio 2023**.<p>È possibile continuare a pianificare attività orarie in Report Builder e farle terminare dopo un massimo di 99 occorrenze. Si prega di notare che il ripristino della funzione si applica solo alle attività orarie; il “termine dopo x occorrenze” rimarrà non disponibile per tutti gli altri intervalli di consegna (giornalieri, settimanali, mensili e annuali). Tieni presente che questa opzione diventerà obsoleta il 31 gennaio 2023. Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe. [Ulteriori informazioni](/help/analyze/report-builder/r-arb-scheduled-reports.md) |
| **Fine del ciclo di vita per [!DNL Reports & Analytics]** | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende terminare [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia su cui si basa [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.22.4), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).

