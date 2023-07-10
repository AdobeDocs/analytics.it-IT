---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: b0c97e4f9d3243e233999cf80f1d742a676f4023
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 85%

---

# Note sulla versione corrente di Adobe Analytics (giugno 2023)

**Ultimo aggiornamento**: 10 luglio 2023

I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Punti salienti della versione {#highlights}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Configurare le posizioni di archiviazione dell’account cloud per l’acquisizione dei dati di classificazione** | Ora puoi gestire le posizioni di archiviazione dell’account cloud utilizzate per l’automazione dei set di classificazione.<p>[Ulteriori informazioni](/help/components/locations/configure-import-accounts.md)</p> |  | 10 luglio 2023 |
| **Miglioramenti al filtro Data Repair** | Sono stati aggiunti tre miglioramenti ai filtri per Data Repair:<ul><li>Filtra per una variabile per modificare una seconda variabile. Ad esempio, se `eVar2` contiene &quot;@&quot; ed elimina `eVar3`.</li><li>Filtro per valori numerici o non numerici</li><li>Applicare più filtri con un AND. Ad esempio, dove `eVar2="a"` E `eVar3="b"`</li></ul>[Ulteriori informazioni](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) | 21 giugno 2023 | 12 luglio 2023 |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** | Ora puoi condividere collegamenti di sola lettura per i progetti Analysis Workspace con chi non ha accesso ad Adobe Analytics. Ad esempio, puoi condividerli con persone esterne all’organizzazione o con persone all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](../analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)<p>Questa funzionalità è abilitata per impostazione predefinita e può essere disabilitata dall’amministratore di sistema. [Ulteriori informazioni](../analyze/analysis-workspace/user-preferences.md#company-preferences)</p> | 3 maggio 2023 | 7 giugno 2023 |
| **Nuove funzioni per i set di classificazione** | [Set di classificazione](/help/components/classifications/sets/overview.md) sono state aggiornate con diverse nuove funzioni:<ul><li>**Consolidamenti**: combina i set di classificazione in un singolo set di classificazione consolidato. Il set di classificazione consolidato può essere utilizzato come altri set di classificazione o come set di dati di ricerca in Customer Journey Analytics. [Ulteriori informazioni](../components/classifications/sets/consolidations/manage.md)</li><li>**Regole**: classifica automaticamente i valori in base alle regole nel set di classificazione. [Ulteriori informazioni](../components/classifications/sets/manage/rules.md)</li><li>**Importazione automatica**: importa automaticamente i dati di classificazione dalle destinazioni dell’archiviazione cloud. [Ulteriori informazioni](../components/classifications/sets/manage/schema.md)</li></ul> | | 7 giugno 2023 |
| **Nuova variabile AppMeasurement** | La variabile `doubleEncodeLinkParameters` gestisce i casi edge in cui le implementazioni codificano caratteri multibyte nelle variabili di tracciamento dei collegamenti. La maggior parte delle implementazioni non ha bisogno di definire questa variabile. [Ulteriori informazioni](../implement/vars/config-vars/doubleencodelinkparameters.md) |  | 7 giugno 2023 |
| **Destinazioni sicure per l’esportazione di feed di dati** | I feed di dati ora possono essere inviati alle seguenti destinazioni di archiviazione cloud:<ul><li>Amazon S3</li><li>RBAC di Azure</li><li>SAS di Azure</li><li>Piattaforma Google Cloud</li></ul>Le destinazioni precedentemente disponibili (FTP, SFTP, S3 e Azure Blob) non sono più consigliate. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/create-feed.html?lang=it) | 12 giugno 2023 | 15 luglio 2023 |
| **Generazione di rapporti sui bot in Workspace** | Il reporting sui bot è ora disponibile in Analysis Workspace. Questa funzione è dotata di diverse aggiunte:<ul><li>Una nuova dimensione: [Nome bot](/help/components/dimensions/bot-name.md)</li><li>Due nuove metriche: [Visualizzazioni pagina bot](/help/components/metrics/bot-page-views.md) e [Occorrenze bot](/help/components/metrics/bot-occurrences.md).</li><li>Un nuovo modello di metrica calcolata: [Proporzione di visualizzazioni pagina bot](/help/components/c-calcmetrics/cm-reference/default-calcmetrics.md)</li><li>Un nuovo rapporto Workspace: reportistica bot</li></ul>La nuova dimensione e le nuove metriche contengono dati precedenti a partire da marzo 2023. |  | 7 giugno 2023 |

{style="table-layout:auto"}

## Altre funzioni nuove o aggiornate {#other}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Eliminare righe contenenti dimensioni dinamiche da una tabella a forma libera** | In una tabella a forma libera di Analysis Workspace, ora è possibile utilizzare l’icona X per eliminare rapidamente righe specifiche contenenti dimensioni dinamiche. In questo modo, viene applicata automaticamente una regola di filtro “Escludi sempre gli elementi”.<p>In precedenza, per eliminare le righe contenenti dimensioni dinamiche era necessario creare manualmente una regola nella finestra di dialogo Filtro. [Ulteriori informazioni](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/D | 17 maggio 2023 |
| **Nuovo pulsante per aggiungere una visualizzazione all’interno di un pannello** | Nella parte inferiore di ciascun pannello di Analysis Workspace è ora disponibile un nuovo pulsante che consente di aggiungere rapidamente una visualizzazione. <p>In precedenza, per aggiungere una visualizzazione a un pannello eano disponibili solo i seguenti metodi: trascinare una visualizzazione dalla barra a sinistra, duplicare o copiare una visualizzazione esistente, oppure creare un pannello vuoto. [Ulteriori informazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/D | 17 maggio 2023 |
| **Deep Linking (app mobile)** | Consente agli utenti di inviare collegamenti alle scorecard che li porteranno direttamente al progetto della scorecard nell’app. Questo agevola ulteriormente la condivisione dei progetti e il coinvolgimento di un pubblico meno tecnico. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/create-scorecard.html?lang=it#share-scorecards-using-a-shareable-link) | N/D | 17 maggio 2023 |
| **Filtri a discesa dinamici** | Stiamo introducendo un nuovo tipo di filtro a discesa che determina i valori disponibili in base ai dati all’interno dell’intervallo di reporting del pannello e ai valori in altri filtri a discesa. Puoi utilizzare filtri a discesa dinamici trascinando una dimensione nella zona di rilascio del pannello mentre tieni premuto [!UICONTROL Shift]. I filtri a discesa statici rimangono invariati trascinando un gruppo di elementi dimensionali nella zona di rilascio del pannello mentre tieni premuto [!UICONTROL Shift]. [Ulteriori informazioni](/help/analyze/analysis-workspace/c-panels/panels.md) |  | 14 giugno 2023 |
| **Pagina di apprendimento di Analytics aggiornata** | La scheda Apprendimento nella pagina di destinazione di Adobe Analytics ora contiene i seguenti miglioramenti:<ul><li>Design migliorato che mostra più contenuti di apprendimento in una singola pagina con una navigazione ottimizzata</li><li>Possibilità di personalizzare i contenuti di apprendimento per livello di esperienza (principiante, intermedio e avanzato)</li></ul>[Ulteriori informazioni](/help/analyze/landing.md) | 27 giugno 2023 | 30 giugno 2023 |
| **Ordinare i componenti in Analysis Workspace** | È ora disponibile una nuova opzione Ordina quando si visualizzano i componenti nella barra a sinistra o nel dizionario dei dati in Analysis Workspace. I componenti possono essere elencati a partire da quelli consigliati (utilizzati più spesso), in ordine alfabetico oppure per categoria (o tipo).<p>In precedenza era possibile solo cercare o filtrare i componenti. [Ulteriori informazioni](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)</p> | N/D | 7 giugno 2023 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

AN-311878; AN-313968; AN-314130; AN-315701; AN-315761; AN-316613; AN-317563; AN-318829; AN-319009; AN-319043; AN-319066; AN-319166; AN-319245; AN-319271; AN-319381; AN-319391; AN-319482; AN-319621; AN-319637; AN-319676; AN-320176; AN-320221; AN-320225; AN-320286; AN-320312; AN-320316; AN-320449; AN-320477; AN-320492; AN-320538; AN-320556; AN-320569; AN-320679; AN-320684; AN-320786; AN-320802; AN-320811; AN-320812; AN-320815; AN-321032; AN-321033; AN-321070; AN-321096; AN-321105; AN-321122; AN-321337;

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Scadenza a 37 mesi degli ID acquisto e degli ID evento (serializzazione degli eventi)** | 25 maggio 2023 | In una prossima versione del motore di elaborazione degli hit di Analytics, prevista per **fine giugno 2023 o inizio luglio 2023**, comincerà ad essere applicata una scadenza a 37 mesi degli ID acquisto e degli ID evento (serializzazione degli eventi). Attualmente, in Adobe Analytics, gli ID acquisto e gli ID evento non scadono mai. Una volta visualizzato/utilizzato un ID acquisto o un ID evento, qualsiasi hit futuro, indipendentemente da quando, avrà tale acquisto o evento contrassegnato come duplicato. Con la nuova versione del motore di elaborazione:<ul><li>gli ID acquisto e gli ID evento scadono sempre dopo 37 mesi.</li><li>Se sono trascorsi 37 mesi dalla visualizzazione dell’ID acquisto o dell’ID evento, questo non viene più considerato un acquisto o un evento duplicato.</li><li> Se si stanno “riutilizzando” gli ID acquisto o gli ID evento da più di 37 mesi, questi non vengono più considerati duplicati.</li></ul> |
| **Migrazione ad Adobe I/O di credenziali server-to-server OAuth** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di Adobe I/O devono effettuare la migrazione alle credenziali server-to-server di Adobe I/O OAuth entro **1 gennaio 2025**. Per ulteriori dettagli e tempistiche, consulta l’avviso di fine del ciclo di vita nella tabella seguente. |
| **Nuovi IP utilizzati dal feed di dati di Adobe Analytics e Data Warehouse in uscita nel data center di Londra** | 27 aprile 2023 | Questo riguarda i clienti del data center di Londra che ricevono richieste di feed di dati e/o rapporti del Data Warehouse inviati a un servizio FTP/SFTP. Per consentire l’accesso, è necessario aggiungere alla configurazione del firewall i seguenti intervalli di indirizzi IP: <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Migrazione ad Adobe I/O di credenziali server-to-server OAuth** | 11 maggio 2023 | I clienti API e Livestream di Adobe Analytics che utilizzano le credenziali JWT di Adobe I/O devono effettuare la migrazione alle credenziali server-to-server di Adobe I/O OAuth entro **1 gennaio 2025**. Adobe I/O non consentirà la creazione di nuove credenziali JWT a partire dal 1° maggio 2024. I clienti che utilizzano JWT devono creare una nuova credenziale server-to-server OAuth o migrare le credenziali JWT esistenti a una server-to-server OAuth. I clienti devono inoltre aggiornare le applicazioni client per utilizzare le nuove credenziali server-to-server OAuth. <ul><li>[Migrazione dalle credenziali dell’account di servizio (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Guida all’implementazione per applicazioni nuove e precedenti con OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)<li>[Utilizzo delle nuove credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Domande frequenti](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |
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
