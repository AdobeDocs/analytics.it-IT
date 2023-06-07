---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 1d98d711c17d3c7ca487b8f5bd4e918a9a399ea7
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 52%

---

# Note sulla versione corrente di Adobe Analytics (giugno 2023)

**Ultimo aggiornamento**: 1 giugno 2023

I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Punti salienti della versione {#highlights}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** | Ora puoi condividere collegamenti di sola lettura per i progetti Analysis Workspace con chi non ha accesso ad Adobe Analytics. Ad esempio, puoi condividerli con persone esterne all’organizzazione o con persone all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=it#share-public-link)<p>Questa funzionalità è abilitata per impostazione predefinita e può essere disabilitata dall’amministratore di sistema. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=it#company-preferences)</p> | 3 maggio 2023 | 7 giugno 2023 |
| **Set di classificazione - consolidamento** | Combina le classificazioni da diverse suite di rapporti in un set di dati consolidato. Il set di dati consolidato può essere utilizzato nei set di classificazione o come set di dati di ricerca in CJA. Ulteriori informazioni (disponibili a breve) |  | 7 giugno 2023 |
| **Set di classificazione: generatore di regole** | Utilizza il generatore di regole di classificazione nell’architettura del set di classificazione corrente. Ulteriori informazioni (disponibili a breve) |  | 7 giugno 2023 |
| **Set di classificazione: importazione automatizzata** | Ora puoi importare automaticamente i dati del set di classificazione dalle destinazioni dell’archiviazione cloud. Ulteriori informazioni (disponibili a breve) |  | 7 giugno 2023 |
| **Nuova variabile AppMeasurement** | La variabile `doubleEncodeLinkParameters` gestisce i casi edge in cui le implementazioni codificano caratteri multibyte nelle variabili di tracciamento dei collegamenti. La maggior parte delle implementazioni non deve definire questa variabile. Ulteriori informazioni (disponibili a breve) |  | 7 giugno 2023 |
| **Destinazioni sicure per l’esportazione di feed di dati** | I feed di dati ora possono essere inviati alle seguenti destinazioni di archiviazione cloud:<ul><li>Amazon S3</li><li>RBAC di Azure</li><li>SAS di Azure</li><li>Piattaforma Google Cloud</li></ul>Le destinazioni precedentemente disponibili (FTP, SFTP, S3 e Azure Blob) non sono più consigliate. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=it) |  | 12 giugno 2023 |
| **Generazione di rapporti sui bot in Workspace** | Il reporting sui bot è ora disponibile in Analysis Workspace. Questa funzione è dotata di diverse aggiunte:<ul><li>Una nuova dimensione: [Nome bot](/help/components/dimensions/bot-name.md)</li><li>Due nuove metriche: [Visualizzazioni di pagina bot](/help/components/metrics/bot-page-views.md) e [Occorrenze bot](/help/components/metrics/bot-occurrences.md).</li><li>Un nuovo modello di metrica calcolata: [Proporzione di visualizzazioni pagina bot](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>Un nuovo rapporto Workspace: rapporti bot</li></ul>La nuova dimensione e le nuove metriche contengono dati precedenti a partire da marzo 2023. |  | Giugno 7,2023 |

{style="table-layout:auto"}

## Altre funzioni nuove o aggiornate {#other}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Eliminare righe contenenti dimensioni dinamiche da una tabella a forma libera** | In una tabella a forma libera di Analysis Workspace, ora è possibile utilizzare l’icona X per eliminare rapidamente righe specifiche contenenti dimensioni dinamiche. In questo caso, viene applicata automaticamente una regola di filtro &quot;Escludi sempre elementi&quot;.<p>In precedenza, per eliminare le righe contenenti dimensioni dinamiche era necessario creare manualmente una regola nella finestra di dialogo Filtro. [Ulteriori informazioni](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/D | 17 maggio 2023 |
| **Nuovo pulsante per aggiungere una visualizzazione all’interno di un pannello** | Nella parte inferiore di ciascun pannello di Analysis Workspace è ora disponibile un nuovo pulsante che consente di aggiungere rapidamente una visualizzazione. <p>In precedenza, per aggiungere una visualizzazione a un pannello eano disponibili solo i seguenti metodi: trascinare una visualizzazione dalla barra a sinistra, duplicare o copiare una visualizzazione esistente, oppure creare un pannello vuoto. [Ulteriori informazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/D | 17 maggio 2023 |
| **Deep Linking (app mobile)** | Consente agli utenti di inviare collegamenti alle scorecard che li porteranno direttamente al progetto della scorecard nell’app. Questo agevola ulteriormente la condivisione dei progetti e il coinvolgimento di un pubblico meno tecnico. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html#share-scorecards-using-a-shareable-link) | N/D | 17 maggio 2023 |
| **Filtri a discesa dinamici** | Stiamo introducendo un nuovo tipo di filtro a discesa che determina i valori disponibili in base ai dati all’interno dell’intervallo di reporting del pannello e ai valori in altri filtri a discesa. Puoi utilizzare filtri a discesa dinamici trascinando una dimensione nella zona di rilascio del pannello mentre tieni premuto [!UICONTROL Shift]. I filtri a discesa statici rimangono invariati trascinando un gruppo di elementi dimensionali nella zona di rilascio del pannello mentre si tiene premuto [!UICONTROL Shift]. [Ulteriori informazioni](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 14 giugno 2023 |
| **Pagina di apprendimento di Analytics aggiornata** | La scheda Apprendimento nella pagina di destinazione di Adobe Analytics ora contiene i seguenti miglioramenti:<ul><li>Design migliorato che mostra più contenuti di apprendimento in una singola pagina con una navigazione migliorata</li><li>Possibilità di personalizzare i contenuti di apprendimento per livello di esperienza (principiante, intermedio e avanzato)</li></ul>[Ulteriori informazioni](/help/analyze/landing.md) |  | Giugno 30,2023 |
| **Ordinare i componenti in Analysis Workspace** | È ora disponibile una nuova opzione Ordina quando si visualizzano i componenti nella barra a sinistra o nel dizionario dei dati in Analysis Workspace. I componenti possono essere elencati a partire da quelli consigliati (utilizzati più spesso), in ordine alfabetico oppure per categoria (o tipo).<p>In precedenza era possibile solo cercare o filtrare i componenti. [Ulteriori informazioni](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | N/D | Da definire |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

-311878; -313968; AN-314130; AN-315701; AN-315761; AN-316613; AN-317563; AN-318829; AN-319009; AN-319043; AN-319066; AN-; AN-; AN-319166; AN-319245; AN-319271; AN-319381; AN-319391; AN-319482; AN-319621; AN-319637; AN-319676; AN-320176; AN-320221; AN-320225; AN-320286; AN-320312; AN-320316; AN-320449; AN-320477; AN-320492; AN-320538; AN-320556; AN-320569; AN-320679; AN-320684; AN-320786; AN-320802; AN-320811; AN-320812; AN-320815; AN-321032; AN-321033; AN-321070; AN-321096; AN-321105; AN-321122; AN-321337;

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza di 37 mesi degli ID acquisto e degli ID evento (serializzazione degli eventi)** | Maggio 25,2023 | Una prossima versione del motore di elaborazione degli hit di Analytics, destinata al rilascio in **fine giugno 2023 o inizio luglio 2023**, inizierà ad applicare una scadenza di 37 mesi degli ID acquisto e degli ID evento (serializzazione degli eventi). Attualmente, gli ID acquisto e gli ID evento non scadono mai in Adobe Analytics. Una volta visualizzato/utilizzato un ID acquisto o un ID evento, qualsiasi hit futuro, indipendentemente da quando, avrà tale acquisto o evento contrassegnato come duplicato. Con il nuovo rilascio del motore di elaborazione:<ul><li>Gli ID acquisto e gli ID evento scadono sempre dopo 37 mesi.</li><li>Se sono trascorsi 37 mesi dalla visualizzazione dell’ID acquisto o dell’ID evento, non viene più considerato un acquisto o un evento duplicato.</li><li> Se stai &quot;riutilizzando&quot; gli ID acquisto o gli ID evento di più di 37 mesi fa, non vengono più considerati duplicati.</li></ul> |
| **Migrazione alle credenziali server-to-server AdobeIO OAuth** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server di AdobeIO tramite **1 gennaio 2025**. Per ulteriori dettagli e tempistiche, consulta l’avviso di fine del ciclo di vita nella tabella seguente. |
| **Nuovi IP utilizzati dai feed di dati di Adobe Analytics e dall’uscita di Data Warehouse nel datacenter di Londra** | 27 aprile 2023 | Questo riguarda i clienti del datacenter di Londra che ricevono richieste di feed di dati e/o rapporti sulle Date Warehouse a un servizio FTP/SFTP. Per consentire l&#39;accesso, è necessario aggiungere alla configurazione del firewall i seguenti intervalli di indirizzi IP: <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Migrazione alle credenziali server-to-server AdobeIO OAuth** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di AdobeIO devono effettuare la migrazione alle credenziali server-to-server di AdobeIO tramite **1 gennaio 2025**. AdobeIO non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale da server a server OAuth o migrare le credenziali JWT esistenti a una credenziale da server a server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
| **Fine del ciclo di vita per[!DNL Reports & Analytics]** | 7 marzo 2023 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita.<p>Il 31 dicembre 2023 termineremo molte delle funzioni associate a Reports &amp; Analytics, tra cui, a titolo esemplificativo: rapporti pianificati, estratti di dati e rapporti DL. Dopo il 31 dicembre 2023, tutti i rapporti pianificati non verranno più inviati. In **Aprile 2023**, tutti i rapporti la cui scadenza era prevista dopo il 31 dicembre 2023 verranno automaticamente aggiornati con scadenza il 31 dicembre 2023. Inoltre, non è più possibile pianificare rapporti futuri oltre il 31 dicembre 2023. |
| **Fine del ciclo di vita della [!UICONTROL Publishing Lists] caratteristica** | 29 settembre 2022 | Come parte della fine del ciclo di vita di Reports &amp; Analytics, gli [!UICONTROL Publishing Lists] sono destinati a raggiungere la fine del ciclo di vita a **dicembre 2023**. Non sarà possibile creare nuovi [!UICONTROL Publishing Lists] o accedere a quelli esistenti per inviare o pianificare progetti di [!UICONTROL Analysis Workspace]. |
| **Fine del ciclo di vita per Data Workbench** | 14 settembre 2022 | Adobe intende terminare il ciclo di vita di Data Workbench a partire dal **31 dicembre 2023**. Vedi [Annuncio della fine del ciclo di vita di Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/eol.html?lang=it) per i dettagli. Per qualsiasi domanda, contatta l’Adobe Account Manager della tua organizzazione. |

{style="table-layout:auto"}

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement (versione 2.23.0), fai riferimento alle [note sulla versione di AppMeasurement per JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/appmeasurement-updates.html?lang=it).


## Risorse correlate

* [Note sulle versioni precedenti 2022](/help/release-notes/2022.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
