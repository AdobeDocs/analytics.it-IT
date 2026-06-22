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
source-git-commit: 8bfb44d4eeb1812ec9b91a68bd37c2b660eae76e
workflow-type: tm+mt
source-wordcount: 573
ht-degree: 91%

---

# Note sulla versione corrente di Adobe Analytics (maggio 2026)

**Ultimo aggiornamento**: 22 giugno 2026

Queste note sulla versione coprono il periodo di rilascio di giugno 2026. Le versioni di Adobe Analytics funzionano su un [modello di distribuzione continua](releases.md) che consente un approccio più scalabile e graduale all’implementazione delle funzioni. Di conseguenza, queste note sulla versione vengono aggiornate diverse volte al mese. Consultale regolarmente.

## Nuove funzioni o miglioramenti {#features}

| Funzione e descrizione | [Avvio del rollout](releases.md) | [Disponibilità generale](releases.md) |
| ----------- | ---------- | ---- |
| **Area di lavoro del percorso in Adobe Analytics** <br/>L’area di lavoro è una visualizzazione in Analysis Workspace che consente di approfondire insight su un percorso utente definito analizzando il modo in cui le persone proseguono o abbandonano il percorso. Consente di creare un grafico flessibile di nodi e frecce che rappresentano qualsiasi combinazione di eventi, elementi dimensionali e segmenti inclusi nel percorso. I dati vengono aggiornati in modo da trascinare i nodi nell’area di lavoro o riorganizzare gli eventi e le condizioni del percorso.<p>In precedenza, l’area di lavoro del percorso era disponibile solo per Customer Journey Analytics.</p><p>Per ulteriori informazioni sull’area di lavoro del percorso in Adobe Analytics, consulta la [Panoramica sull’area di lavoro del percorso](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md). </p><p>Per informazioni su come creare una visualizzazione dell’area di lavoro del percorso in Adobe Analytics, consulta [Configurare l’area di di lavoro del percorso](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).</p> | 18 maggio 2026 | 5 giugno 2026 |

### Correzioni in Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-452009, AN-450375, AN-449870, AN-450814, AN-450698
**Classificazioni**:
**Feed dati e Data Warehouse**:
**Migrazione**:
**Esportazioni**:
**Report Builder**: 440912
**Generazione rapporti**: AN-423516
**Suite di rapporti**: AN-455684
**Rapporti pianificati**:
**Segmentazione**:
**Altro**:


### Avvisi sulla fine del ciclo di vita (EOL) {#eol}

| Fine del ciclo di vita del prodotto o della funzione | Data di aggiunta o aggiornamento | Descrizione |
| --- | --- | --- |
| **Report Builder legacy** | 18 giugno 2025 | Il componente aggiuntivo precedente di Report Builder sarà ritirato a giugno 2026. Tutti gli utenti devono iniziare a eseguire l’aggiornamento delle cartelle di lavoro precedenti al [nuovo Report Builder](/help/analyze/report-builder/rb-overview.md). Il nuovo Report Builder è disponibile sia per i clienti di Adobe Analytics che di Customer Journey Analytics. Offre [quasi le stesse funzioni](/help/analyze/report-builder/convert-workbooks.md#unsupported), oltre a numerose nuove funzioni utili e miglioramenti dell’interfaccia utente. Per agevolare il processo di aggiornamento, il nuovo Report Builder include una facile funzione di conversione della cartella di lavoro. Il nuovo Report Builder è disponibile solo come componente aggiuntivo tramite Microsoft Store. Molte organizzazioni richiedono un processo di approvazione interno prima di rendere il componente aggiuntivo disponibile per gli utenti. Attendi il tempo necessario per questo processo e inizia a cooperare subito con la tua organizzazione per assicurarti di disporre del tempo sufficiente per eseguire l’aggiornamento delle cartelle di lavoro prima della data di fine del ciclo di vita. |
| **API di Adobe Analytics (versione 1.4)** | 17 luglio 2024 | Il **12 agosto 2026**, i seguenti servizi API legacy di Analytics raggiungeranno la fine del ciclo di vita e verranno disattivati; le integrazioni correnti, create utilizzando questi servizi, cesseranno di funzionare:<ul><li>API Adobe Analytics (versione 1.4)</li><li>Autenticazione WSSE di Adobe Analytics</li></ul><p>Le integrazioni che utilizzano l’API di Adobe Analytics (versione 1.4) devono migrare all’API di [Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mentre le integrazioni WSSE devono migrare a un protocollo di autenticazione basato su OAuth in [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Per risposte alle domande comuni e ulteriori indicazioni, consulta le [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/).</p> |


## AppMeasurement

Per gli ultimi aggiornamenti sulle versioni di AppMeasurement, consulta le [note sulla versione di AppMeasurement](https://github.com/adobe/appmeasurement/releases).


>[!MORELIKETHIS]
>
>* [Note sulle versioni precedenti per il 2026](/help/release-notes/2026.md)
>* [Note sulla versione di Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=it)
>* [Note sulla versione dei servizi multimediali in streaming &#x200B;](https://experienceleague.adobe.com/it/docs/media-analytics/using/release-notes/release-notes)
>* Ultimi aggiornamenti sulle versioni dei [prodotti Adobe CX Enterprise](https://business.adobe.com/products/adobe-experience-cloud-products.html)
