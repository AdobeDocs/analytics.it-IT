---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: d1fd0aa0312b8fb6112cde22a53c58eb3be791a2
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 59%

---

# Note sulla versione corrente di Adobe Analytics (maggio 2023)

**Ultimo aggiornamento**: 8 maggio 2023

I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate in Adobe Analytics {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Backfill per sandbox non di produzione** | Quando crei un flusso di dati del connettore di origine di Analytics in una sandbox non di produzione, il backfill nelle sandbox non di produzione sarà limitato a 3 mesi. Rimarrà a 13 mesi per le sandbox di produzione. | N/D | 26 aprile 2023 |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** | Ora puoi condividere collegamenti di sola lettura ai progetti Analysis Workspace con persone che non hanno accesso ad Adobe Analytics. Ciò include la condivisione con persone esterne all’organizzazione o all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link)<p>Questa funzionalità è abilitata per impostazione predefinita e può essere disabilitata dall’amministratore di sistema. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 maggio 2023 | Giugno 2023 |
| **Schermata iniziale aggiornata per l’app delle dashboard di Analytics (app mobile)** | La nuova schermata Home aggiornata consente di visualizzare tutte le scorecard in un unico elenco di scorecard consolidato.  Se hai accesso a più organizzazioni con un solo accesso, tutte le scorecard delle organizzazioni saranno disponibili in un unico elenco. | N/D | 10 maggio 2023 |
| **Ordinare i componenti in Analysis Workspace** | È ora disponibile una nuova opzione Ordina quando visualizzi i componenti nella barra a sinistra o nel dizionario dati in Analysis Workspace. Puoi ordinare i componenti per tipo Consigliato (quelli più comunemente utilizzati), Alfabetico o Categorico.<p>In precedenza era possibile cercare o filtrare solo i componenti. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=en)</p> | N/D | 10 maggio 2023 |
| **Eliminare righe contenenti dimensioni dinamiche da una tabella a forma libera** | In una tabella a forma libera in Analysis Workspace, è ora possibile eliminare rapidamente righe specifiche contenenti dimensioni dinamiche utilizzando l’icona x. In questo modo, viene applicata automaticamente una regola di filtro &quot;È diverso da&quot;.<p>In precedenza, l’unico modo per eliminare le righe contenenti dimensioni dinamiche era creare manualmente una regola nella finestra di dialogo Filtro. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=en)</p> | N/D | 10 maggio 2023 |
| **Nuovo pulsante per aggiungere una visualizzazione all’interno di un pannello** | È ora disponibile un nuovo pulsante nella parte inferiore di ciascun pannello in Analysis Workspace, che consente di aggiungere rapidamente una visualizzazione. <p>In precedenza, gli unici metodi per aggiungere una visualizzazione a un pannello consistevano nel trascinare una visualizzazione dalla barra a sinistra, duplicare o copiare una visualizzazione esistente o creare un pannello vuoto. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#quick-viz)</p> | N/D | 10 maggio 2023 |
| **Collegamenti profondi (app mobile)** | Consente agli utenti di inviare collegamenti alle scorecard che li porteranno direttamente al progetto della scorecard nell’app. Questo rende ancora più facile condividere i progetti e aumentare l&#39;impegno da parte di un pubblico meno tecnico. | Da definire | Da definire |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

AN-312098; AN-318309; AN-316675; AN-318173; AN-310359; AN-317613; AN-318836; AN-315744; AN-311772; AN-318719; AN-314074; AN-316651<!--"Verified" status-->; AN-318602; AN-315961; AN-317534; AN-318607; AN-316498; AN-316648; AN-318244; AN-317747; AN-318432; AN-318231; AN-317590; AN-318415; AN-318154; AN-316647; N-314417; AN-317614; AN-317725; AN-318114; AN-317876; AN-318052; AN-317966; AN-316477; AN-318036; AN-317931; AN-318045; AN-316246; AN-317281; AN-317879; AN-308077; AN-317708; AN-316115; AN-315963

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **Avviso: Nuovi IP utilizzati da Adobe Analytics Data Feeds e Data Warehouse in uscita nel datacenter di Londra** | 27 aprile 2023 | Per i clienti del datacenter di Londra che hanno richieste di feed di dati e/o rapporti di Data Warehouse inviati a un servizio FTP/SFTP, i seguenti intervalli di indirizzi IP devono essere aggiunti alla configurazione del firewall per consentire l’accesso: <ul><li>130.248.244.32/29</li><li>130.248.244.40/29</li></ul> |
| **I processi di ricerca dei dispositivi ora utilizzano terze parti per tutte le ricerche dei dispositivi** | 3 marzo 2023 | Il 2 marzo 2023, come parte del rollout del supporto degli hint client, abbiamo aggiornato i nostri processi di ricerca dei dispositivi in modo da utilizzare terze parti per questi processi. Precedentemente, avevamo usato terze parti solo per la ricerca di dispositivi mobili. Come parte del rollout, alcuni sistemi operativi desktop erano etichettati in modo errato con il testo “mobile” (ad esempio “Mobile OS X 10.15.7” invece di “OS X 10.15.7”).<p>Durante il rilascio di aprile di Adobe questi nomi verranno corretti. I rapporti di Analytics e CJA verranno aggiornati retroattivamente, poiché il loro reporting cerca il nome del sistema operativo in base a un ID registrato come parte dei dati dell’evento. Una volta aggiornato il valore di ricerca corrispondente a un ID, tutti i rapporti verranno corretti, compresi i dati storici. Per i clienti [!UICONTROL Data Feeds], la modifica è retroattiva se si utilizza un processo di ricerca simile a quello che avviene durante il reporting. Tuttavia, se archivi il valore del sistema operativo nei dati dell’evento, il reporting verrà aggiornato solo per gli eventi futuri. Per ulteriori dettagli consulta [Sistema operativo](/help/components/dimensions/operating-systems.md). |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Fine del ciclo di vita del servizio giapponese di tracciamento dei feature phone** | 21 marzo 2023 | Solo per i nostri clienti giapponesi: alla **fine di maggio 2023**, il servizio giapponese di tracciamento dei feature phone (mod_ktrack) verrà interrotto. Ci scusiamo per l’inconveniente, ma ti chiediamo di disinstallare o disabilitare i moduli installati sul tuo server Apache. Consulta le pagine 27 e 28 in [questo documento](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) per riferimento. |
| **Fine del ciclo di vita per[!DNL Reports & Analytics]** | 7 marzo 2023 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita.<p>Il 31 dicembre 2023 termineremo molte delle funzioni associate a Reports &amp; Analytics, tra cui, a titolo esemplificativo: rapporti pianificati, estratti di dati e rapporti DL. Dopo il 31 dicembre 2023, tutti i rapporti pianificati non verranno più inviati. In **Aprile 2023**, tutti i rapporti la cui scadenza era prevista dopo il 31 dicembre 2023 verranno automaticamente aggiornati con scadenza il 31 dicembre 2023. Inoltre, non è più possibile pianificare rapporti futuri oltre il 31 dicembre 2023. |
| **Fine del ciclo di vita della metrica [!UICONTROL People]** | 9 marzo 2023 | Con l’obsolescenza di [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html?lang=it), la metrica Persone relativa a Device Co-op non è più rilevante. L’8 maggio 2023 verrà rimossa la metrica [!UICONTROL People]. A questo punto, i dati verranno reindirizzati alla metrica [!UICONTROL Unique Visitor] per evitare che progetti, segmenti e metriche calcolate si interrompano.<p>**Nota**: la metrica [[!UICONTROL People] associata a Cross-Device Analytics](/help/components/metrics/people.md) non è interessata da questo annuncio. |
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
