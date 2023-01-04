---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: be32a2278ac3686d814b25d8a4a857b9f0ddc771
workflow-type: tm+mt
source-wordcount: '1443'
ht-degree: 97%

---

# Note sulla versione corrente di Adobe Analytics

**Ultimo aggiornamento**: 4 gennaio 2023

I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate in Adobe Analytics

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| Visualizzazione **[!UICONTROL Key metric summary]** | La visualizzazione [!UICONTROL Key metric summary] ti consente di vedere come si presenta una metrica importante in un singolo arco temporale. Consente inoltre di confrontare le prestazioni delle metriche in due intervalli di tempo. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/key-metric.html?lang=it) | 5 ottobre 2022 | 19 ottobre 2023 |
| **Variabili con più valori senza distinzione tra maiuscole e minuscole** | Per le variabili multivalore senza distinzione tra maiuscole e minuscole, i valori memorizzati in `mvvar1 - mvvar3` e `post_mvvar1 - post_mvvar3` nei feed di dati non verranno più convertiti in minuscolo automaticamente. Al contrario, i feed di dati (e i dati trasmessi tramite il connettore di origine di Analytics ad Adobe Experience Platform e CJA) rifletteranno il carattere originale trasmesso dalla pagina. | N/D | 24 ottobre 2022 |

{style=&quot;table-layout:auto&quot;}

## Correzioni in Adobe Analytics

* È stato risolto un problema a causa del quale le versioni recenti di macOS venivano erroneamente denominate “Macintosh”. Con questa correzione, la dimensione del sistema operativo inizierà a utilizzare la numerazione delle versioni “macOS”, a partire da macOS 11. (AN-301834)
* È stato risolto un problema relativo all’intervallo di date “fisse” in Report Builder. (AN-303684)
* Sono stati risolti dei problemi a causa dei quali l’interfaccia utente Feed dati non veniva caricata. (AN-303803, AN-303784)

### Altre correzioni

-295574; AN-296354; AN-297143; AN-299501; AN-301755; AN-302054; AN-302304; AN-302631; AN-302811; AN-303090; AN-303372; AN-; AN-303428; AN-303429; AN-303432; AN-303434; AN-303437; AN-303438; AN-303519; AN-303610; AN-303656; AN-303659; AN-303663; AN-303664; AN-303818; AN-303823; AN-303837; AN-304036; AN-304195; AN-304321; AN-304325; AN-304339; AN-304356; AN-304435; AN-304457; AN-304509; AN-304519; AN-304534

## Avvisi importanti per gli amministratori di Adobe Analytics

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Mappatura IP-geolocalizzazione migliorata** | 4 gennaio 2023 | Il nostro fornitore di ricerche IP, Digital Element, sta effettuando l’aggiornamento a un nuovo set di dati migliorato (NetAcuity Pulse) per la mappatura IP-geolocalizzazione. Inizialmente pianificato per ottobre 2022, Adobe Analytics adotterà questo nuovo set di dati su **11 gennaio 2023**. Il nuovo database sarà più accurato delle versioni precedenti. Quando il nuovo database verrà adottato, alcune mappature IP-geolocalizzazione verranno modificate/migliorate.<p>Tutti gli strumenti di Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API di reporting, Data Warehouse, LiveStream, feed di dati, ecc.) sfrutteranno automaticamente le nuove mappature migliorate. Non vi saranno modifiche nel formato dei dati nei feed di dati. Anche i dati CJA forniti tramite il connettore di origine di Analytics sfrutteranno automaticamente le nuove mappature. |
| **Aggiornamento al nuovo database di gestori NetAcuity** | 4 gennaio 2023 | Questo aggiornamento, originariamente pianificato per il 5 ottobre 2022, verrà ora eseguito **11 gennaio 2023**. Le informazioni relative al gestore memorizzate nel campo `carrier` in Adobe Analytics Data Warehouse e nei feed di dati di Analytics cambieranno. Storicamente, il formato dei dati di tale colonna era `<domain>:<ISP>`. Adobe ha mantenuto una tabella di ricerca interna per mappare questi valori `<domain>:<ISP>` sui nomi dei gestori a scopo di reporting negli strumenti di reporting di Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, API di reportistica, Data Warehouse, LiveStream, ecc.). Il file di ricerca (`carrier.tsv`) viene fornito anche con feed di dati in modo che chi utilizza i feed di dati possa usare le stesse mappature.<p>Questo aggiornamento migliora le mappature dei gestori utilizzando un database più accurato da NetAcuity. Il formato dei dati nella colonna dei gestori nei feed di dati cambierà in futuro. Invece di `<domain>:<ISP>`, conterrà un nome di gestore. Adobe continuerà a utilizzare la tabella di ricerca per mantenere la massima continuità possibile con il precedente reporting. Gli strumenti di reporting in cui le ricerche vengono applicate da Adobe (Analysis Workspace, Reports &amp; Analytics, API di reporting, Data Warehouse, LiveStream, ecc.) trarranno vantaggio da mappature più precise. Alcune mappature, soprattutto per i domini internazionali e gli ISP, cambieranno più di altre quando Adobe adotterà il nuovo database. Nel file di ricerca dei gestori dei feed di dati (`carrier.tsv`) verranno mantenute le vecchie mappature e verranno aggiunte nuove mappature.<p>Il connettore di origine di Analytics non mappa attualmente il campo del gestore (carrier), pertanto il reporting sui gestori non è attualmente disponibile in Experience Platform, CJA, ecc. L’utilizzo del nuovo database di gestori non avrà quindi alcun impatto in Experience Platform in quanto si basa sui dati forniti dal connettore di origine di Analytics. |
| **Linee guida aggiornate per le notifiche con picchi di traffico** | 18 novembre 2022 | Le precedenti linee guida si basavano rigorosamente sui volumi di hit. La [nuove linee guida](https://experienceleague.adobe.com/docs/analytics/admin/traffic-management/traffic-lead-time.html?lang=it) si basano su una combinazione di dimensioni della suite di rapporti e aumento della percentuale. |
| **Aggiornamento delle ricerche dei dispositivi a causa di suggerimenti client Google** | 14 ottobre 2022 | L’utilizzo degli hint client nella ricerca del dispositivo, originariamente pianificati per il 26 ottobre 2022, è stato posticipato a **gennaio 2023**. <p> <p>Da ottobre 2022 è possibile raccogliere gli hint client con le librerie Web SDK o AppMeasurement per JavaScript. Tuttavia, gli hint client non saranno incorporati nella ricerca del dispositivo fino a gennaio 2023. In tale data, Adobe inizierà a utilizzare gli hint client in aggiunta all’agente utente per ricavare determinate informazioni sul dispositivo per gli hit provenienti dai browser Chromium, come Google Chrome e Microsoft Edge. Ciò risponde al piano di Google volto a ridurre gradualmente le informazioni presentate dalla stringa dell’agente utente al posto dei dati trasmessi tramite gli hint client. <p> <p>Come parte di questa modifica, Adobe utilizzerà Device Atlas per tutte le ricerche di informazioni sui dispositivi relative all’agente utente. [Ulteriori informazioni](/help/technotes/client-hints.md) |
| **Pagina di destinazione predefinita** | 29 settembre 2022 | La [nuova pagina di destinazione](/help/analyze/landing.md) introdotta all&#39;inizio di quest&#39;anno diventerà l&#39;esperienza predefinita per tutti gli utenti a **gennaio 2023**. La pagina corrente diventerà obsoleta e tutti dovranno utilizzare la nuova esperienza. |
| Condizioni per l’esecuzione automatica di **[!UICONTROL Anomaly detection]** | 29 settembre 2022 | Oggi, [!UICONTROL Anomaly detection] viene eseguito automaticamente su tutte le colonne delle tabelle a forma libera con serie temporale. Affinché i dati possano essere rapidamente disponibili per l’analisi e per velocizzare il caricamento dei progetti, Adobe cambierà il modo in cui funziona l’esecuzione automatica del Rilevamento delle anomalie. A partire dal **26 ottobre 2022**, [!UICONTROL Anomaly detection] viene eseguito automaticamente solo sulla prima colonna di metriche di una tabella. Se necessario, puoi configurare le impostazioni delle colonne per eseguire il rilevamento delle anomalie su altre colonne. |
| **Sospensione dei rapporti pianificati in Reports &amp; Analytics** | 8 giugno 2022 | Il 21 aprile 2022 Adobe ha annunciato la rimozione di diverse funzioni specifiche dei rapporti pianificati in preparazione dell’annunciata fine del ciclo di vita di Reports &amp; Analytics. Queste funzionalità includevano la possibilità di pianificare nuovi rapporti e nuovi estratti di dati.<p>In risposta alle richieste dei clienti che necessitano di un’estensione e per facilitare la transizione da Reports &amp; Analytics, Adobe ha deciso di estendere l’accesso a queste funzioni fino al **31 gennaio 2023**. Si prega di notare che le scadenze per i rapporti e gli estratti dei dati continueranno a essere limitate a nove mesi; la consegna del report e dell’estrazione dei dati verrà sospesa alla fine di questo periodo, a meno che la pianificazione non venga riattivata.<p>Per ribadire questo punto, queste funzioni verranno rese obsolete il 31 gennaio 2023. Prima di questa data, devi migrare i rapporti pianificati in uno degli altri meccanismi disponibili in Adobe Analytics. Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe. [Ulteriori informazioni](/help/analyze/reports-analytics/scheduled-reports-eol.md) |
| **Sospensione delle attività pianificate nel Report Builder** | 8 giugno 2022 | Il 21 aprile 2022 Adobe ha implementato modifiche alle attività pianificate in Report Builder nell’ambito delle attività di ottimizzazione delle prestazioni e della consegna. Tali modifiche includevano l’eliminazione della possibilità che le consegne pianificate avessero “termine dopo x occorrenze”. In risposta a diverse richieste dei clienti che necessitano di più tempo per esplorare e implementare alternative, Adobe ha deciso di ripristinare questa opzione in modo limitato fino al **31 gennaio 2023**.<p>È possibile continuare a pianificare attività orarie in Report Builder e farle terminare dopo un massimo di 99 occorrenze. Tieni presente che il ripristino della funzione si applica solo alle attività orarie; l’opzione “termina dopo x eventi” rimarrà non disponibile per tutti gli altri intervalli di consegna (giornalieri, settimanali, mensili e annuali). Tieni presente che questa opzione diventerà obsoleta il 31 gennaio 2023. Per ulteriori domande o supporto, contatta l’Assistenza clienti di Adobe. [Ulteriori informazioni](/help/analyze/report-builder/r-arb-scheduled-reports.md) |

{style=&quot;table-layout:auto&quot;}

## Avvisi sulla fine del ciclo di vita

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Fine del ciclo di vita della [!UICONTROL Publishing Lists] caratteristica** | 29 settembre 2022 | Come parte della fine del ciclo di vita di Reports &amp; Analytics, gli elenchi di pubblicazione sono destinati a raggiungere la fine del ciclo di vita a **dicembre 2023**. Non sarà possibile creare nuovi elenchi di pubblicazione o accedere a quelli esistenti per inviare o pianificare progetti di Analysis Workspace. |
| **Fine del ciclo di vita per Data Workbench** | 14 settembre 2022 | Adobe intende terminare il ciclo di vita di Data Workbench a partire dal **31 dicembre 2023**. Vedi [Annuncio della fine del ciclo di vita di Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=it) per i dettagli. Per qualsiasi domanda, contatta l’Adobe Account Manager della tua organizzazione. |
| **Fine del ciclo di vita per [!DNL Reports & Analytics]** | 4 gennaio 2022 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita. |

{style=&quot;table-layout:auto&quot;}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.23.0), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).

## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
