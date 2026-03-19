---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 0900b9adb801bec4d433c57d83ac117efbe78168
workflow-type: tm+mt
source-wordcount: '1291'
ht-degree: 25%

---

# Note sulla versione corrente di Adobe Analytics (marzo 2026)

**Ultimo aggiornamento**: giovedì 11 marzo 2026

Queste note sulla versione coprono il periodo di rilascio di marzo 2026. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ---- |
| **Ordina le tabelle per più colonne** <br/>È ora possibile ordinare i dati di una tabella a forma libera per più colonne in Analysis Workspace, sia che si tratti di dimensioni che di metriche.<p>Quando si ordinano dati per più colonne, i dati vengono ordinati in base alla priorità assegnata a ciascuna colonna. Accanto all’icona di ordinamento viene visualizzata la numerazione delle priorità.</p><p>Per ulteriori informazioni, vedere [Filtrare e ordinare tabelle a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).</p> | giovedì 28 gennaio 2026 | giovedì 4 marzo 2026 <p>(Originariamente pianificato per il 18 febbraio 2026)</p> |
| **Report Builder: visibilità dell&#39;amministratore per tutte le cartelle di lavoro pianificate**<br/> Il componente aggiuntivo Report Builder Excel include una nuova opzione di filtro che consente agli amministratori di visualizzare tutte le cartelle di lavoro pianificate per una determinata organizzazione, indipendentemente da chi le ha pianificate. Questa opzione di filtro è disponibile solo per gli amministratori di Analytics. È disponibile sia nella scheda Cartella di lavoro che nella scheda Legacy quando si visualizzano le cartelle di lavoro pianificate.<p>La possibilità di visualizzare tutte le cartelle di lavoro pianificate è particolarmente utile durante la migrazione delle cartelle di lavoro tra team distribuiti, in quanto consente agli amministratori di individuare facilmente tutte le cartelle di lavoro legacy prima di eseguirne la migrazione.</p><p>In precedenza, gli amministratori potevano visualizzare solo le cartelle di lavoro pianificate, non quelle pianificate da altri utenti.</p><p>Per ulteriori informazioni, vedere [Cartelle di lavoro pianificate gestite](/help/analyze/report-builder/manage-schedules-reportbuilder.md).</p> | | mercoledì 10 marzo 2026 |
| **Aggiornamento della funzione Approximate Count Distinct**<br/> L&#39;algoritmo probabilistico HLL utilizzato nella funzione Approximate Count Distinct verrà presto aggiornato. L’output risultante per i numeri che utilizzano questa funzione potrebbe cambiare leggermente rispetto ai numeri storici, come segue:</p><ul><li>Quando si contano quantità molto piccole di valori univoci, i risultati saranno migliorati per utilizzare conteggi esatti anziché stime.</li><li>Quando si contano dati più grandi, le stime di conteggio manterranno la stessa precisione di prima di questo aggiornamento (le stime sono accurate entro il 5% del numero esatto, il 95% del tempo).</li></ul><p>Per ulteriori informazioni sulla funzione Approximate Count Distinct, vedere [Approximate Count Distinct](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md#approximate-count-distinct) in [Funzioni avanzate](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)</p> | | mercoledì 10 marzo 2026 |
| **Esercitazione pratica per Analysis Workspace**<br/>&#x200B;È ora disponibile una nuova esercitazione pratica per guidare i nuovi utenti nelle nozioni di base sull&#39;utilizzo di pannelli, visualizzazioni e componenti in Analysis Workspace. <p>Per ulteriori informazioni, vedere [Pagina di destinazione di Adobe Analytics](/help/analyze/landing.md).</p> | | giovedì 18 marzo 2026 |
| **Applica un raggruppamento a un pannello**<br/> Ora puoi applicare un raggruppamento a un pannello. Quando si applica un raggruppamento a livello di pannello, il raggruppamento viene applicato a tutte le colonne di tutte le tabelle a forma libera all’interno del pannello. | Marzo 2026 | Maggio 2026 |
| **Servizi multimediali in streaming: supporto dei dati di pianificazione** <br/>È ora possibile caricare dati pianificati di contenuti multimediali in streaming passati per tenere traccia in modo più semplice e preciso del pubblico.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 ottobre 2025 | Prima metà del 2026<p>Rilascio originariamente pianificato per il 29 ottobre 2025</p> |

## Correzioni in Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-440336, AN-440216, AN-440121, AN-438445, AN-438216, AN-437856, AN-437776, AN-437765, AN-437365, AN-432793, AN-432094, AN-431557, AN-431200, AN-429621, AN-429424, AN-427973, AN-426089, AN-425883, AN-424359
**Classificazioni**: AN-440143, AN-439891, AN-439844, AN-438994, AN-438057, AN-438052, AN-437986, AN-437896, AN-435387, AN-435335, AN-435150, AN-433050, AN-432062, AN-431873, AN-429642
**Feed dati e Data Warehouse**: AN-439441, AN-437086, AN-433064, AN-432121, AN-431755, AN-428239, AN-427049, AN-425036, AN-424972, AN-423509, AN-335417, AN-283958, AN-256948
**Migrazione**:
**Esportazioni**: AN-432030
**Report Builder**: AN-437895, AN-437083, AN-434288, AN-434209, AN-433224, AN-430622
**Generazione rapporti**: AN-434545, AN-431206, AN-428043
**Report pianificati**:
**Segmentazione**:
**Altro**: AN-440076, AN-434783, AN-434542, AN-434233, AN-433368, AN-432138, AN-431322, AN-431012, AN-429067, AN-423285


## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Miglioramenti all&#39;elaborazione Livestream** | giovedì 14 gennaio 2026 | Adobe prevede di apportare miglioramenti e modifiche alla formattazione dei payload LiveStream. Questi aggiornamenti forniscono una migliore parità tra LiveStream e altre funzioni di Adobe Analytics, come Analysis Workspace. È disponibile un endpoint di anteprima che consente di verificare le modifiche pianificate. Consulta le [Note sulla versione di LiveStream](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/livestream/release-notes/) per l&#39;elenco completo delle modifiche e l&#39;anteprima dei dettagli dell&#39;endpoint. Il 13 aprile 2026, Adobe pianifica un passaggio definitivo al formato del payload aggiornato. |
| **Rimozione suite di cifratura TLS 1.2** | giovedì 11 febbraio 2026 | Avviso agli amministratori: il 27 maggio 2026 Adobe pianifica di rimuovere il supporto per le seguenti suite di cifratura TLS 1.2 dai server di raccolta dati di Adobe.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_GCM_SHA256`</li><li>`TLS_RSA_WITH_AES_256_GCM_SHA384`</li></ul><p>Per la maggior parte delle implementazioni non è richiesta alcuna azione da parte del cliente. Questa modifica interessa principalmente i dati di Analytics inviati da applicazioni native legacy che utilizzano librerie TLS obsolete e un numero limitato di visitatori web su browser o sistemi operativi obsoleti. La rimozione del supporto per queste suite di crittografia migliora la sicurezza e allinea Adobe ai moderni standard di crittografia. Meno dello 0,1% del traffico di raccolta dati si basa attualmente su queste suite di cifratura.</p> |
| **Report Builder legacy** | 18 giugno 2025 | Il componente aggiuntivo legacy di Report Builder verrà ritirato a giugno 2026. Tutti gli utenti devono iniziare ad aggiornare le cartelle di lavoro legacy al [nuovo Report Builder](/help/analyze/report-builder/rb-overview.md). Il nuovo Report Builder è disponibile per i clienti di Adobe Analytics e Customer Journey Analytics. Ha [parità di funzionalità](/help/analyze/report-builder/convert-workbooks.md#unsupported) oltre a numerose nuove funzioni convenienti e miglioramenti all&#39;interfaccia utente. Per facilitare il processo di aggiornamento, il nuovo Report Builder include una funzione di conversione della cartella di lavoro semplice. Il nuovo Report Builder è disponibile solo come componente aggiuntivo tramite Microsoft Store. Molte organizzazioni richiedono un processo di approvazione interno prima che il componente aggiuntivo possa essere reso disponibile agli utenti. Attendi l’ora per questo processo e inizia a lavorare con la tua organizzazione ora per assicurarti di disporre del tempo sufficiente per aggiornare le cartelle di lavoro prima della data di fine del ciclo di vita. |
| **Accesso tramite domini legacy o tramite SSO legacy** | venerdì 10 aprile 2025 | Adobe prevede di aggiornare il modo in cui gli utenti accedono ad Adobe Analytics per migliorare la sicurezza e semplificare l’esperienza di accesso. Come parte di questo impegno, l&#39;accesso tramite domini legacy o tramite SSO legacy, incluso `my.omniture.com`, verrà interrotto definitivamente il **2 gennaio 2026**. Dopo questa data, le credenziali di accesso legacy e l’SSO legacy non funzioneranno più. Tutti gli utenti dovranno effettuare l&#39;accesso tramite `experience.adobe.com` utilizzando i propri ID Adobe Experience Cloud. Se hai bisogno di assistenza con il tuo Experience Cloud ID, contatta l&#39;amministratore Adobe Analytics della tua organizzazione o l&#39;[Assistenza clienti Adobe](https://helpx.adobe.com/it/contact.html). |
| **API Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |


## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, fai riferimento alle [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).


## Risorse correlate

* [Note sulle versioni precedenti 2025](/help/release-notes/2025.md)
* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
* [Note sulla versione di Streaming Media Services](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=it)
* Scopri gli ultimi aggiornamenti sulle versioni dei [prodotti Adobe Experience Cloud](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)
