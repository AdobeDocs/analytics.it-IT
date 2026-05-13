---
title: Revisione completa
description: Rivedi l’implementazione ogni 6 mesi per garantire un continuo allineamento con le esigenze di business e i KPI.
feature: Implementation Basics
exl-id: 235fc86e-e1b0-4b1a-a270-0dfba457a832
role: Admin, Leader
TQID: https://experienceleague.adobe.com/YQL-V84ZWAr8NqRp1snYZBgl7-3iIhhxWkWh6KTFKNM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 69%

---

# Revisione completa (per rivedere l’implementazione due volte all’anno)

Perché dovresti rivedere la tua implementazione ogni 6 mesi? Perché è necessario assicurarsi che l’implementazione sia ancora in linea con le esigenze di business. Inoltre, è utile affrontare eventuali problemi di qualità dei dati quando sono di piccole dimensioni e prima che diventino questioni importanti che potrebbero erodere la fiducia delle parti interessate. Oltre a queste revisioni complete ogni 6 mesi, dovresti eseguire anche [revisioni mirate](/help/implement/review/focused-review.md) dopo ogni aggiornamento del sito web.

## &#x200B;1. Assicurati che l’implementazione sia ancora completamente allineata alle esigenze aziendali

Esamina eventuali cambiamenti nelle esigenze di business insieme al responsabile business e/o agli analisti. Se vengono rilevate esigenze o opportunità di misurazione che non sono attualmente soddisfatte dalla tua implementazione, determina come aggiornare i KPI e i piani di misurazione. Ricorda di registrare le modifiche nei documenti [BRD e SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html#implementation).

## &#x200B;2. Assicurati che le metriche e le variabili funzionino ancora bene

Rivedi brevemente tutte le metriche e le variabili, in ordine di importanza per l’azienda, per assicurarti che i dati vengano raccolti correttamente. Inizia con le metriche e le variabili più importanti: quelle associate ai tuoi [primi 5 KPI](/help/implement/review/define-kpis.md#review). Per eseguire questa operazione:

* Crea delle dashboard per visualizzare le visualizzazioni con tendenze mensili delle metriche e delle variabili (o configura [avvisi](/help/components/alerts/alerts-overview.md) per ognuna di esse), in modo da assicurarti di ottenere i dati previsti e che i dati siano corretti. Se riscontri delle discrepanze, esamina il livello dati, le regole di gestione dei tag e le regole di elaborazione per scoprirne il motivo.
* Esegui nuovamente [Analytics Health Dashboard](https://assets.adobe.com/public/8ff304bb-18e0-434b-54d1-39199422ba1c) per monitorare le tendenze generali delle metriche e delle variabili.

Evita che l’implementazione si gonfi di metriche e variabili di cui non hai bisogno. Disabilita le metriche o le variabili che l’azienda non utilizza più o di cui non ha più bisogno. Potrai eliminarle o riutilizzarle in un secondo momento.

## &#x200B;3. Aggiorna i KPI

Ora che hai una visione aggiornata degli obiettivi aziendali, riconsidera se hai effettivamente scelto i 5 indicatori di prestazioni chiave (KPI, Key Performance Indicators) *più* importanti. Puoi averne solo 5. Questi KPI possono essere metriche (come ricavi) oppure metriche calcolate (come ricavi per visita) che possono avere anche delle variabili. Per ulteriori informazioni, consulta [Definire i primi 5 KPI](/help/implement/review/define-kpis.md).
