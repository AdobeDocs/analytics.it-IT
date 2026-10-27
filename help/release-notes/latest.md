---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 809c87dcabb2026a994ee06d4f0cf9fbaefc936b
workflow-type: tm+mt
source-wordcount: '1394'
ht-degree: 36%
---
# Note sulla versione corrente di Adobe Analytics (ottobre 2026)

**Ultimo aggiornamento**: 27 ottobre 2026

Queste note sulla versione coprono il periodo di rilascio di ottobre 2026. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ---- |
| **Autorizzazione di sola lettura per il server Adobe Analytics MCP**<br/> Gli amministratori ora possono concedere agli utenti l&#39;accesso in sola lettura al server Adobe Analytics MCP. Il nuovo elemento di autorizzazione [!UICONTROL MCP Read-only Access] consente agli utenti di accedere a tutti gli strumenti di sola lettura, senza consentire loro di creare progetti, segmenti o metriche calcolate.<p>L&#39;elemento di autorizzazione [!UICONTROL MCP Access] esistente è stato rinominato in [!UICONTROL MCP Full Access]. Gli utenti con questa autorizzazione possono accedere a tutti gli strumenti, compresi quelli che creano, modificano o eliminano componenti.</p><p>Per ulteriori informazioni, consulta [Impostare le autorizzazioni](https://developer.adobe.com/analytics-mcp/docs/guides/permissions) nella documentazione del server Adobe Analytics MCP.</p> | | 6 ottobre 2026 |
| **Area di lavoro Percorsi: confrontare le percentuali**<br/> Quando si confronta un percorso con un periodo precedente, è ora possibile abilitare la nuova opzione [!UICONTROL Compare percentages] per visualizzare la modifica in punti percentuali per ciascun nodo, freccia e abbandono. Questo è utile quando si confrontano le percentuali, ad esempio la fidelizzazione tra nodi o l’abbandono, perché il confronto rimane accurato anche quando il numero di persone nel percorso differisce tra intervalli di date.<p>Per ulteriori informazioni, vedere &quot;Confrontare le percentuali&quot; in [Configurare una visualizzazione dell&#39;area di lavoro del Percorso](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#configure-visualization-settings).</p> | | 19 ottobre 2026 |
| **Genera automaticamente le descrizioni dei componenti** <br/>Ora puoi generare automaticamente le descrizioni per dimensioni, metriche, metriche calcolate, segmenti e intervalli di date. Questo aiuta gli utenti di Workspace a capire quali componenti utilizzare, soprattutto nelle organizzazioni con librerie di componenti di grandi dimensioni. <p>È possibile generare una descrizione per un singolo componente o per più componenti contemporaneamente.</p> <p>Il link alla documentazione seguirà a breve.<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 28 ottobre 2026 |
| **Miglioramenti ai dati di classificazione nei report di Data Warehouse**<br/> I dati di classificazione sono ora più precisi nei report di Data Warehouse. Con questi miglioramenti, potresti notare le seguenti differenze nei rapporti di Data Warehouse:<ul><li>**Valori vuoti in cui sono stati precedentemente visualizzati i valori di classificazione**: quando un valore di classificazione viene eliminato da un set di classificazione, in Data Warehouse viene visualizzato correttamente un valore vuoto. In precedenza, un valore di classificazione eliminato poteva continuare a essere visualizzato nei rapporti successivi.</li><li>**Altri valori di classificazione completi**: in alcuni casi, Data Warehouse mostrava in precedenza solo uno dei diversi valori di classificazione. Data Warehouse ora mostra ogni valore.</li><li>**I valori di classificazione possono essere rappresentati in modo diverso in Analysis Workspace (non comune)**: Data Warehouse può visualizzare tutti i valori di classificazione associati, mentre Analysis Workspace presenta un singolo valore. Di conseguenza, i valori di classificazione possono occasionalmente differire tra Data Warehouse e Analysis Workspace.</li></ul><p>Per ulteriori informazioni, vedere [Dimensioni di classificazione in Data Warehouse](/help/export/data-warehouse/component-support.md#classifications).</p> | 14 ottobre 2026 | Gennaio 2027 |
| **Integrazione di Adobe Brand Visibility**<br/> Connetti Adobe Brand Visibility con i dati Adobe Analytics della tua organizzazione in modo da poter misurare in che modo l&#39;individuazione basata sull&#39;intelligenza artificiale si traduce in un coinvolgimento reale del sito Web e in risultati di business.<p>Il collegamento alla documentazione seguirà a breve.</p> | | TBD <br/> (originariamente pianificato per ottobre 2026) |
| **CX Enterprise Coworker: l&#39;analisi della causa principale per i dati di Adobe Analytics**<br/> Chat con collaboratori ora può indagare il motivo per cui una metrica è cambiata nelle suite di rapporti di Adobe Analytics, invece di segnalare solo la modifica. Chiedi di una modifica in una metrica nota in un periodo noto, ad esempio &quot;Perché il picco dei ricavi è avvenuto martedì?&quot; e la Chat collaborativa mette in evidenza le dimensioni e i segmenti che hanno contribuito alla modifica.<p>Per ulteriori informazioni, consulta [Panoramica delle prestazioni aziendali](https://experienceleague.adobe.com/it/docs/coworker/content/chat/use-cases/data-insights/business-performance/business-performance) nella documentazione di Adobe CX Enterprise Coworker.</p> | 13 ottobre 2026 | 29 ottobre 2026 |
| **CX Enterprise Coworker: apri visualizzazioni in Analysis Workspace**<br/> Quando Chat con coworking crea una visualizzazione dai dati di Adobe Analytics, ora puoi aprirla in un nuovo progetto Analysis Workspace per un&#39;analisi più approfondita e un controllo più granulare. <p>Per ulteriori informazioni, consulta [Aprire una visualizzazione in Analysis Workspace](https://experienceleague.adobe.com/it/docs/coworker/content/chat/use-cases/data-insights/analytics-chat#open-a-visualization-in-analysis-workspace) nella documentazione di Adobe CX Enterprise Coworker.</p> | 13 ottobre 2026 | 29 ottobre 2026 |
| **CX Enterprise Coworker: Analizza i dati di Adobe Analytics in Chat con Coworker** <br/>Adobe CX Enterprise Coworker Chat ora può eseguire un&#39;analisi avanzata dei dati che in precedenza era possibile solo in Analysis Workspace. Chat con collaboratori accede ai dati dalle suite di rapporti di Adobe Analytics, consentendoti di esplorarli e ottenere risposte ai prompt in linguaggio naturale.<p>Per ulteriori informazioni, consulta [Analizzare i dati con Chat di Coworker](https://experienceleague.adobe.com/it/docs/coworker/content/chat/use-cases/data-insights/analytics-overview) nella documentazione di Adobe CX Enterprise Coworker.</p> | 2 ottobre 2026 | 29 ottobre 2026<p>(Originariamente pianificato per il 25 settembre 2026)</p> |

### Correzioni in Adobe Analytics

**Activity Map**: AN-494609, AN-493182
**Analysis Workspace**: AN-495340, AN-494789, AN-493307, AN-468900
**Classificazioni**: AN-498043, AN-496619, AN-496468, AN-496217, AN-496133, AN-495567, AN-494651, AN-494345, AN-494312, AN-494261, AN-493645, AN-493507, AN-493336, AN-492869, AN-492812, AN-492751, AN-492750, AN-492741, AN-491032, AN-490802 490796 467849, AN-, AN-, AN-
**Feed dati e Data Warehouse**: AN-494937, AN-493065, AN-489796, AN-479109
**Migrazione**: AN-489850, AN-468014
**Esportazioni**: AN-494337, AN-486563
**Report Builder**: AN-496602, AN-494224, AN-493737, AN-493508, AN-493505, AN-492806, AN-468981, AN-454376
**Generazione rapporti**: AN-493637, AN-461260
**Suite di rapporti**: AN-496773, AN-495227, AN-494981, AN-494372, AN-494370, AN-493629
**Rapporti pianificati**: AN-491103
**Segmentazione**:
**Altro**: AN-496398, AN-494453, AN-492494

### Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Report Builder legacy** | 18 giugno 2025 | Il componente aggiuntivo legacy di Report Builder è stato ritirato a giugno 2026. Tutti gli utenti devono iniziare a eseguire l’aggiornamento delle cartelle di lavoro precedenti al [nuovo Report Builder](/help/analyze/report-builder/rb-overview.md). Il nuovo Report Builder è disponibile sia per i clienti di Adobe Analytics che di Customer Journey Analytics. Offre [quasi le stesse funzioni](/help/analyze/report-builder/convert-workbooks.md#unsupported), oltre a numerose nuove funzioni utili e miglioramenti dell’interfaccia utente. Per agevolare il processo di aggiornamento, il nuovo Report Builder include una facile funzione di conversione della cartella di lavoro. Il nuovo Report Builder è disponibile solo come componente aggiuntivo tramite Microsoft Store. Molte organizzazioni richiedono un processo di approvazione interno prima di rendere il componente aggiuntivo disponibile per gli utenti. Attendi il tempo necessario per questo processo e inizia a cooperare subito con la tua organizzazione per assicurarti di disporre del tempo sufficiente per eseguire l’aggiornamento delle cartelle di lavoro prima della data di fine del ciclo di vita. |
| **API di Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **31 agosto 2026**, i seguenti servizi API legacy di Analytics hanno raggiunto la fine del ciclo di vita e sono stati chiusi e le integrazioni create utilizzando questi servizi non funzioneranno più:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, consulta le [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).

## Funzioni posticipate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Servizi multimediali in streaming: supporto dei dati di pianificazione** <br/>Ora puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data).</p> | 29 ottobre 2025 | Da definire<p>(Originariamente previsto per il 29 ottobre 2025)</p> |


>[!MORELIKETHIS]
>
>* [Note sulle versioni precedenti per il 2026](/help/release-notes/2026.md)
>* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
>* [Note sulla versione dei servizi multimediali in streaming &#x200B;](https://experienceleague.adobe.com/it/docs/media-analytics/using/release-notes/release-notes)
>* Ultimi aggiornamenti sulle versioni dei [prodotti Adobe CX Enterprise](https://business.adobe.com/it/products/adobe-experience-cloud-products.html)

