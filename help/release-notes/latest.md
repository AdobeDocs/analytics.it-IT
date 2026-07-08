---
title: Note sulla versione corrente di Adobe Analytics
description: Consulta le note sulla versione corrente di Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 13d4b15d7069a52f4953a49aa0f1f5b7cb16ae77
workflow-type: tm+mt
source-wordcount: 890
ht-degree: 63%

---

# Note sulla versione corrente di Adobe Analytics (luglio 2026)

**Ultimo aggiornamento**: 8 luglio 2026

Queste note sulla versione coprono il periodo di rilascio di luglio 2026. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ---- |
| **Analisi sub-hit** <br/>L&#39;analisi sub-hit consente di analizzare i dati del prodotto a un livello più granulare rispetto al livello hit. Invece di filtrare gli hit interi, puoi segmentare i singoli prodotti all’interno degli hit. <p>Ad esempio, puoi creare segmenti per una categoria di prodotti specifica senza includere tutti gli altri prodotti acquistati nello stesso ordine.</p><p>Per ulteriori informazioni, vedere [Analisi degli hit secondari](/help/components/segmentation/sub-hit.md).</p> | 8 luglio | Fine di luglio 2026 |
| **Guida alle funzionalità di ricerca API di AA 2.0** <br/>Utilizza le funzionalità di ricerca per [restituire un sottoinsieme di elementi dimensionali nei report](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters).<p>Per ulteriori informazioni, consulta [Funzioni di ricerca](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters) nella guida dell&#39;endpoint Reports in Adobe Developer. | | 1 luglio 2026 |
| **Automatizzazione dei rapporti ricorrenti con API AA** <br/>Impostazione di rapporti Adobe Analytics ricorrenti e automatici per la pipeline dei dati con nuove metriche secondo una pianificazione con API dei rapporti. <p>Per ulteriori informazioni, consulta la [guida dell&#39;endpoint per l&#39;automazione dei report ricorrenti di Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/recurring) su Adobe Developer.</p> | | 1 luglio 2026 |
| **Nuovi parametri di espansione per AA** <br/>Utilizza i nuovi parametri di espansione dell&#39;API Dimension per recuperare i campi di configurazione eVar per tipi di allocazione, scadenze, tipi di dati e merchandising. <p>Per ulteriori informazioni, consulta la [guida di riferimento API](https://developer.adobe.com/analytics-apis/docs/2.0/apis/#operation/dimensions_getDimensions) e la [guida dell&#39;endpoint Dimensions](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/) su Adobe Developer.</p> | | 1 luglio 2026 |

### Correzioni in Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-449890, AN-457527, AN-451161, AN-459034, AN-458071, AN-458398
**Classificazioni**: AN-453318, AN-456739, AN-455828, AN-455270, AN-460272, AN-459367, AN-459239, AN-458418, AN-458417
**Feed dati e Data Warehouse**: AN-456945, AN-460700
**Migrazione**:
**Esportazioni**:
**Report Builder**: AN-457533, AN-453683
**Generazione rapporti**: AN-447692, AN-451259, AN-455713
**Suite di rapporti**:
**Rapporti pianificati**: AN-450715
**Segmentazione**:
**Altro**: AN-453982, AN-455771

### Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Report Builder legacy** | 18 giugno 2025 | Il componente aggiuntivo precedente di Report Builder sarà ritirato a giugno 2026. Tutti gli utenti devono iniziare a eseguire l’aggiornamento delle cartelle di lavoro precedenti al [nuovo Report Builder](/help/analyze/report-builder/rb-overview.md). Il nuovo Report Builder è disponibile sia per i clienti di Adobe Analytics che di Customer Journey Analytics. Offre [quasi le stesse funzioni](/help/analyze/report-builder/convert-workbooks.md#unsupported), oltre a numerose nuove funzioni utili e miglioramenti dell’interfaccia utente. Per agevolare il processo di aggiornamento, il nuovo Report Builder include una facile funzione di conversione della cartella di lavoro. Il nuovo Report Builder è disponibile solo come componente aggiuntivo tramite Microsoft Store. Molte organizzazioni richiedono un processo di approvazione interno prima di rendere il componente aggiuntivo disponibile per gli utenti. Attendi il tempo necessario per questo processo e inizia a cooperare subito con la tua organizzazione per assicurarti di disporre del tempo sufficiente per eseguire l’aggiornamento delle cartelle di lavoro prima della data di fine del ciclo di vita. |
| **API di Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |

## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, consulta le [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).

## Funzioni posticipate

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| -----------|-----------|-----------|
| **Servizi multimediali in streaming: supporto dei dati di pianificazione** <br/>Ora puoi caricare dati di pianificazione di precedenti contenuti live multimediali in streaming per monitorare l’audience con maggiore facilità e precisione.<p>Di seguito sono riportati alcuni esempi di contenuti live supportati con il caricamento dei dati di pianificazione:</p><ul><li>Piattaforme FAST (Free Ad Supported TV)</li><li>Flussi locali</li><li>Sport live</li></ul><p>Il caricamento dei dati di pianificazione ti consente di tenere traccia dei dati sul pubblico per i singoli programmi eseguiti durante il periodo di tempo indicato nel file di caricamento. Puoi anche raccogliere i dati sul pubblico per argomenti o segmenti di programma specifici.</p><p>Queste funzionalità sono disponibili indipendentemente da come hai implementato Streaming Media Collection.</p><p>In precedenza, era difficile collegare con precisione una determinata sessione a programmi specifici durante l’analisi di contenuti live, a singoli argomenti o a segmenti di programma.</p><p>Per ulteriori informazioni, consulta [Caricare i dati di pianificazione per tenere traccia del contenuto live](https://experienceleague.adobe.com/it/docs/media-analytics/using/media-use-cases/track-schedule-data) | 29 ottobre 2025 | Da definire<p>(Originariamente previsto per il 29 ottobre 2025)</p> |


>[!MORELIKETHIS]
>
>* [Note sulle versioni precedenti per il 2026](/help/release-notes/2026.md)
>* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
>* [Note sulla versione dei servizi multimediali in streaming &#x200B;](https://experienceleague.adobe.com/it/docs/media-analytics/using/release-notes/release-notes)
>* Ultimi aggiornamenti sulle versioni dei [prodotti Adobe CX Enterprise](https://business.adobe.com/products/adobe-experience-cloud-products.html)

