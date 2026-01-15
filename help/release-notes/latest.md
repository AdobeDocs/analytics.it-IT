---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
source-git-commit: 69aa42b1949944b59740222073635be72c4bd6ab
workflow-type: tm+mt
source-wordcount: '1225'
ht-degree: 30%

---

# Note sulla versione corrente di Adobe Analytics (gennaio 2026)

**Ultimo aggiornamento**: giovedì 14 gennaio 2026

Queste note sulla versione coprono il periodo di rilascio di gennaio 2026. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione | Descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Generatore regole set di classificazione** | La funzionalità del generatore di regole è ora disponibile nei set di classificazione. Puoi definire le regole nel contesto di un set di classificazione. Le regole vengono applicate (se attivate) a tutte le combinazioni di suite di rapporti e dimensioni chiave sottoscritte al set di classificazione.<p>Il collegamento alla documentazione seguirà a breve.</p> |  | sabato 30 gennaio 2026 |
| **Feed dati migliorati** | Sono ora disponibili i seguenti miglioramenti per i feed dati:<ul><li>Esperienza utente migliorata.</li><li>Nuova esperienza per la creazione e la gestione di modelli di colonna.</li><li>Ora puoi scegliere quando creare un modello di colonna da riutilizzare in feed di dati futuri. È inoltre possibile eliminare, modificare e copiare i modelli.<br/>In precedenza, ogni feed di dati creato generava un nuovo modello di colonna, che generava un numero elevato di modelli di colonna inutilizzati e non consentiva di eliminarli o gestirli.</li><li>Aggiungi e filtra per tag.</li><li>Visualizzare la cronologia dei processi di feed dati. (quando ha avuto inizio il periodo della richiesta, quando ha avuto inizio, quando ha finito e così via).</li><li>Inviare nuovamente o rielaborare i feed di dati. (Dalla pagina Job historyi)</li><li>Consenti hit in arrivo. Ora puoi includere i dati arrivati dopo che il processo di feed dati ha completato l’elaborazione dei dati all’interno della frequenza di reporting impostata.</li><li>Quando si sceglie una data di fine per un feed dati, la data di fine scelta viene inclusa come ultimo giorno del feed dati.<br/>In precedenza, la data di fine veniva esclusa dal feed di dati.</li><li>È ora possibile esportare la frequenza di 15 minuti, ma non è disponibile per impostazione predefinita. Affinché questa opzione sia disponibile nel tuo ambiente, devi prima contattare l&#39;Assistenza clienti Adobe e richiedere che la suite di rapporti sia configurata per supportare le esportazioni della durata di 15 minuti.</li></ul><p>**Nota:** con questi miglioramenti, vengono aggiornati anche gli URL delle pagine dei feed dati in Adobe Analytics. Aggiorna eventuali segnalibri esistenti per puntare alle nuove pagine di feed di dati entro il 30 aprile 2026.</p>Il collegamento alla documentazione seguirà a breve.</p> | mercoledì 20 gennaio 2026 | mercoledì 10 febbraio 2026 |
| **Ordinare le tabelle per più colonne** | Ora è possibile ordinare i dati di una tabella a forma libera in base a più colonne in Analysis Workspace, che si tratti di dimensioni o metriche.<p>Quando si ordinano dati per più colonne, i dati vengono ordinati in base alla priorità assegnata a ciascuna colonna. Accanto all’icona di ordinamento viene visualizzata la numerazione delle priorità.</p><p>Il link alla documentazione seguirà a breve.<!-- For more information, see "Filter and sort freeform tables". (need to move info to this article from "Include multiple dimension columns in a freeform table") --></p> | giovedì 28 gennaio 2026 | giovedì 18 febbraio 2026 |
| **Servizi di contenuti multimediali in streaming: supporto dei dati di pianificazione** | Ora puoi caricare dati pianificati di contenuti multimediali live in streaming precedenti per tracciare in modo più semplice e preciso il pubblico.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data)</p> | 29 ottobre 2025 | Prima metà del 2026<p>Rilascio originariamente pianificato per il 29 ottobre 2025</p> |

## Correzioni in Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-423389, AN-422636, AN-422482, AN-422027, AN-421134, AN-420187, AN-406271, AN-406188, AN-405997, AN-405983, AN-405796, AN-405033, AN-404893, AN-404871, AN-404842, AN-404713, AN-404502, AN-404353, AN-404352, AN-404048 402523 396149 390990 390728 390646 383484 376980 371729 347570, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-, AN-
**Classificazioni**: AN-423985, AN-423092, AN-423067, AN-422913, AN-422908, AN-422793, AN-422785, AN-422745, AN-422705, AN-422422, AN-422126, AN-422098, AN-422077, AN-422058, AN-421999, AN-421698, AN-421351, AN-406583, AN-406295, AN-406123 406052 404743 404372, AN-, AN-, AN-, AN-
**Raccolta dati**: AN-422488
**Feed di dati e Data Warehouse**: AN-423186, AN-422789, AN-422239, AN-421552, AN-421393, AN-421339, AN-421231, AN-420149, AN-406345, AN-406217, AN-405073, AN-404822, AN-404774, AN-389691
**Privacy**:
**Report Builder**: AN-422120, AN-421937, AN-406296, AN-402951, AN-399748
**Generazione rapporti**:
**Rapporti pianificati**: AN-423087, AN-422686
**Confronto segmenti**:
**Altro**: AN-423401, AN-422819, AN-422775, AN-422626, AN-422238, AN-422160, AN-422071, AN-421687, AN-420045, AN-404891, AN-404608, AN-390912


## Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Miglioramenti all&#39;elaborazione Livestream** | giovedì 14 gennaio 2026 | Adobe prevede di apportare miglioramenti e modifiche alla formattazione dei payload LiveStream. Questi aggiornamenti forniscono una migliore parità tra LiveStream e altre funzioni di Adobe Analytics, come Analysis Workspace. È disponibile un endpoint di anteprima che consente di verificare le modifiche pianificate. Consulta le [Note sulla versione di LiveStream] per l&#39;elenco completo delle modifiche e l&#39;anteprima dei dettagli dell&#39;endpoint. Il 13 aprile 2026, Adobe pianifica un passaggio definitivo al formato del payload aggiornato. |
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
