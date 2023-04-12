---
title: Note sulla versione più recente di Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics.
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 611477ef794464de0b05b45e8445ed8fdd32b154
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 62%

---

# Note sulla versione corrente di Adobe Analytics (aprile 2023)

**Ultimo aggiornamento**: 12 aprile 2023

I rilasci di Adobe Analytics funzionano secondo un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Funzioni nuove o aggiornate in Adobe Analytics {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Filtro riga/colonna per lo streaming del connettore di origine di Analytics** | Il connettore di origine di Analytics in Adobe Experience Platform ora consente di filtrare i dati di Analytics che vengono utilizzati per popolare i profili nel [Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it). Il filtro a livello di riga consente di ridurre il numero di eventi associati ai profili. Il filtro a livello di colonna consente di ridurre la rilevanza degli eventi stessi, consentendoti in tal modo di ottimizzare l’utiizzo delle adesioni al profilo. Questo filtro si applica solo ai dati inviati al profilo cliente in tempo reale e al [servizio Identity](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=it). **Il filtro non influisce sui dati inviati al Data Lake per l’utilizzo in applicazioni come Customer Journey Analytics**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=it#filtering-for-profile) | N/D | 29 marzo 2023 |
| **Supporto parziale per Activity Map con SDK per web** | A partire dalla versione 2.15.0 dell’SDK per web, abbiamo iniziato a popolare i dati di Activity Map quando è abilitato il tracciamento dei collegamenti. Questo consente agli utenti dell’SDK per web di ottenere la generazione di rapporti di Activity Map se il tracciamento dei collegamenti è abilitato con l’SDK per web e Activity Map configurati in Analytics.<p>L&#39;abilitazione del tracciamento dei collegamenti con SDK per web invia attualmente eventi di collegamento quando un cliente passa da una pagina all&#39;altra. Questo è diverso dal funzionamento di AppMeasurement e può potenzialmente causare hit fatturabili aggiuntivi inviati ad Adobe. Ulteriori informazioni [qui](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) e [qui](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) | N/D | 31 marzo 2023 |
| **Offuscamento IP per Experience Edge** | Experience Edge supporta l’offuscamento dell’IP per i dati inviati direttamente a Adobe Experience Platform. Questo offre vantaggi ai clienti che inviano dati direttamente a Platform per l’utilizzo in CJA o in altre soluzioni Platform. L’offuscamento dell’IP è configurato a livello di flusso di dati. Supporta la rimozione dell&#39;ultimo ottetto o dell&#39;intero indirizzo IP.<p>**Nota**: L’offuscamento NON si applica ai dati inviati ad Adobe Analytics. Analytics continua a ricevere l’IP completo. L’elaborazione IP continua a essere eseguita separatamente in Analytics. In futuro, prevediamo di consentire l’offuscamento dei dati di Analytics sul server Edge di . | N/D | Rilascio di AEP il 26 aprile 2023 |
| **Dizionario dati in Analysis Workspace** | Il dizionario dati consente sia agli utenti che agli amministratori di tenere traccia dei componenti (dimensioni, metriche) nel proprio ambiente Analytics, nonché di gestirli e comprenderli meglio. [Ulteriori informazioni](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) | 15 marzo 2023 | 29 marzo 2023 |
| **Condivisione dei collegamenti per i progetti (accesso non richiesto)** - Accesso solo alle Private Beta | <p>Ora puoi condividere collegamenti di sola lettura ai progetti Analysis Workspace con persone che non hanno accesso ad Adobe Analytics. Puoi condividere i collegamenti dei progetti con persone esterne all’organizzazione o con persone all’interno dell’organizzazione che non dispongono del provisioning per Adobe Analytics. [Ulteriori informazioni](/help/analyze/analysis-workspace/curate-share/share-projects.md)</p> <p>Per iscriverti alle Private Beta, contatta il team del tuo account Adobe.</p> | 26 aprile 2023 | Giugno 2023 |

{style="table-layout:auto"}

## Correzioni in Adobe Analytics

* È stato risolto un problema relativo ai file di ricerca Sistema operativo.tsv in Feed dati.
* È stato risolto un problema relativo ai valori delle metriche che variano tra Reporting e analisi e Workspace (AN-315965).
* È stato risolto un problema che impediva l’importazione di classificazioni parziali. (AN-315854)
* È stato risolto un problema relativo all’API Analytics 1.4. (AN-316475)
* È stato risolto un problema che impediva ad alcuni clienti di ottenere classificazioni per la dimensione Pagina tramite Report Builder e Report &amp; Analytics. (AN-314445)
* È stato risolto un problema che impediva il trasferimento degli avvisi. (AN-306457)

### Altre correzioni

AN-288373; AN-305144; AN-309023; AN-310466; AN-311686; AN-311705; AN-312018; AN-312105; AN-312116; AN-312191; AN-312502; AN-312737; AN-312854; AN-312991; AN-313253; AN-313275; AN-313278; AN-313282; AN-313365; AN-313390; AN-313547; AN-313549; AN-313818; AN-313986; AN-314080; AN-314248; AN-314251; AN-314262; AN-314300; AN-314309; AN-314448; AN-314643; AN-314564; AN-314645; AN-314705; AN-314761; AN-314831; AN-314919; AN-314948; AN-315032; AN-315115; AN-315154; AN-315158; AN-315321; AN-315375; AN-315379; AN-315392; AN-315407; AN-315427; AN-315582; AN-315591; AN-315699; AN-315700; AN-315704; AN-315705; AN-315777; AN-315923; AN-316237; AN-316243; AN-316324; AN-316415; AN-316474; AN-316493; AN-316596; AN-316864;

## Avvisi importanti per gli amministratori di Adobe Analytics {#admin}

| Avviso | Data di aggiunta o aggiornamento | Descrizione |
| ----------- | ---------- | ---------- |
| **I processi di ricerca dei dispositivi ora utilizzano una terza parte per tutte le ricerche dei dispositivi** | 3 marzo 2023 | Il 2 marzo 2023, come parte del rollout del supporto per i suggerimenti dei clienti, abbiamo aggiornato i nostri processi di ricerca dei dispositivi per utilizzare una terza parte per tutte le ricerche dei dispositivi. Precedentemente, avevamo usato le terze parti solo per la ricerca di dispositivi mobili. Come parte del rollout, alcuni sistemi operativi desktop erano etichettati in modo errato con il testo &quot;mobile&quot; (ad esempio &quot;Sistema operativo mobile X 10.15.7&quot; invece di &quot;OS X 10.15.7&quot;).<p>Durante la versione di aprile dell’Adobe verranno corretti questi nomi. I rapporti di Analytics e CJA verranno aggiornati retroattivamente, poiché il loro reporting cerca il nome del sistema operativo in base a un ID registrato come parte dei dati dell’evento. Una volta aggiornato il valore di ricerca corrispondente a un ID, tutti i rapporti verranno corretti, compresi i dati storici. Per [!UICONTROL Data Feeds] clienti, la modifica è retroattiva se utilizzi un processo di ricerca simile al momento del reporting. Tuttavia, se archivi il valore del sistema operativo nei dati dell&#39;evento, il reporting verrà aggiornato solo in futuro. Vedi [Sistema operativo](/help/components/dimensions/operating-systems.md) per ulteriori dettagli. |
| **Aggiornamento delle ricerche dei dispositivi a causa di suggerimenti client Google** | 27 febbraio 2023 | L’utilizzo degli hint client, pianificati per il 16 febbraio 2023, è stato posticipato al fine di garantire al meglio la qualità delle ricerche del dispositivo tramite hint. Si è proceduto con la prima fase della versione per il supporto degli hint client il 27 febbraio 2023. La seconda e ultima fase del rilascio è stata completata giovedì 2 marzo 2023. [Ulteriori informazioni](/help/technotes/client-hints.md) |
| **Migrazione automatica all’architettura del set di classificazione** | 8 febbraio 2023 | Nei prossimi mesi, Adobe pianifica di migrare tutte le classificazioni in tutte le organizzazioni all’architettura di classificazione più recente. Si stima che la migrazione degli ultimi clienti avverrà a maggio 2023. Non è richiesta alcuna azione da parte del cliente e non è previsto alcun tempo di inattività. Questa nuova architettura offre numerosi vantaggi, tra cui:<ul><li>Tempo di elaborazione notevolmente ridotto (72 ore → 24 ore)</li><li>Possibilità di utilizzare l’interfaccia dei [set di classificazione](/help/components/classifications/sets/overview.md)</li><li>Opzione per utilizzare in futuro i dati di classificazione in Adobe Experience Platform tramite il [Connettore di origine di Adobe Analytics per i dati di classificazione](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=it)</li></ul>Nota le seguenti modifiche che possono potenzialmente influire sul flusso di lavoro dell’organizzazione:<ul><li>Quando si utilizza il browser o l’importazione FTP, “[!UICONTROL Overwrite on conflict]” è sempre abilitato.</li><li>Quando si utilizza il browser o l’importazione FTP, l’opzione per esportare immediatamente dopo l’importazione non è più supportata.</li><li>L’endpoint `GetDimensions` dell’API di Analytics 2.0 ora restituisce identificatori stringa per le classificazioni anziché identificatori numerici. È comunque possibile utilizzare gli identificatori numerici, ma Adobe consiglia di utilizzare i nuovi identificatori stringa laddove possibile. Gli identificatori numerici possono essere recuperati utilizzando il parametro `?expansion=hidden` della stringa di query.</li></ul>Se desideri una pianificazione di migrazione più specifica per la tua organizzazione o se hai domande/dubbi su questa migrazione, contatta l’assistenza clienti di Adobe. [Ulteriori informazioni](/help/components/classifications/sets/overview.md) |

{style="table-layout:auto"}

## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data aggiunta o aggiornata | Descrizione |
| --- | --- | --- |
| **Fine del ciclo vita del servizio giapponese di tracciamento dei telefoni a funzioni** | 21 marzo 2023 | Solo per i nostri clienti giapponesi: Alla **fine maggio 2023**, il servizio di tracciamento dei Feature Phone giapponese (mod_ktrack) verrà interrotto. Ci scusiamo per l&#39;inconveniente, ma ti chiediamo di disinstallare o disabilitare i moduli installati sul tuo server Apache. Vedere le pagine 27 e 28 in [presente documento](/help/release-notes/mod_ktrackforSiteCatalyst_ver1.40.pdf) di riferimento. |
| **Fine del ciclo di vita per[!DNL Reports & Analytics]** | 7 marzo 2023 | A partire dal **31 dicembre 2023**, Adobe intende interrompere [!DNL Reports & Analytics] e i relativi rapporti e funzioni. I rapporti, le visualizzazioni e la tecnologia soggiacente [!DNL Reports & Analytics] non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di [!DNL Reports & Analytics] sono disponibili in [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it). A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di [!DNL Reports & Analytics] sono state trasferite ad Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. [Questo avviso](https://spark.adobe.com/page/6WnF8JK6IRDhf/) spiega il processo di fine del ciclo di vita.<p>Il 31 dicembre 2023 termineremo molte delle funzioni associate a Reports &amp; Analytics, tra cui, a titolo esemplificativo: rapporti pianificati, estratti di dati e rapporti DL. Dopo il 31 dicembre 2023, tutti i rapporti pianificati non verranno più inviati. In **Aprile 2023**, tutti i rapporti la cui scadenza era prevista dopo il 31 dicembre 2023 verranno automaticamente aggiornati con scadenza il 31 dicembre 2023. Inoltre, non è più possibile pianificare rapporti futuri oltre il 31 dicembre 2023. |
| **Fine del ciclo di vita della metrica [!UICONTROL People]** | 9 marzo 2023 | Con l’obsolescenza di [[!DNL Device Co-op]](https://experienceleague.adobe.com/docs/discontinued/using/device-co-op.html?lang=it), la metrica Persone relativa a Device Co-op non è più rilevante. L’8 maggio 2023 verrà rimossa la funzione [!UICONTROL People] metrica. A questo punto, i dati verranno reindirizzati alla metrica [!UICONTROL Unique Visitor] per evitare che progetti, segmenti e metriche calcolate si interrompano.<p>**Nota**: la metrica [[!UICONTROL People] associata a Cross-Device Analytics](/help/components/metrics/people.md) non è interessata da questo annuncio. |
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
