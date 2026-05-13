---
title: Revisione mirata (dopo ogni rilascio del sito web)
description: Segui questi passaggi per garantire che l’implementazione rimanga priva di errori e in linea con i KPI.
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
role: Admin, Leader
TQID: https://experienceleague.adobe.com/C57qRRa4-WDgJDgvtLebgy-0DAPvMUreSrGfuA67N4o
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 59%

---

# Revisione mirata (dopo ogni rilascio del sito web)

Perché dovresti rivedere la tua implementazione ogni mese? È quindi possibile risolvere qualsiasi problema relativo alla qualità dei dati mentre sono ancora contenuti. Se esegui regolarmente questa revisione incentrata dopo ogni versione del sito web, scoprirai che le tue [revisioni complete](/help/implement/review/full-review.md) semestrali saranno molto più facili. Eviterai inoltre che i problemi di piccole dimensioni si trasformino in problemi di dati di grandi dimensioni che potrebbero erodere la fiducia delle parti interessate.

## &#x200B;1. Inizia con i primi 5 KPI

Conoscere i primi 5 indicatori di prestazioni chiave (KPI, Key Performance Indicators) ti aiuterà a determinare le metriche e le dimensioni associate che devi esaminare. Se non hai aggiornato i KPI negli ultimi 6 mesi o se la tua azienda non ha ancora creato i KPI, segui [queste istruzioni](/help/implement/review/define-kpis.md).

## &#x200B;2. Assicurati che le metriche e le variabili KPI funzionino ancora bene

Gli aggiornamenti del codice nel tempo possono avere ramificazioni non desiderate. Assicurati che tutte le metriche e le dimensioni associate ai tuoi [primi 5 KPI](/help/implement/review/define-kpis.md) funzionino ancora correttamente. Idealmente, questo viene fatto subito dopo il rilascio di un sito Web; se non lo hai fatto negli ultimi mesi, fallo *ora*. Per eseguire questa operazione:

* Crea dashboard per visualizzare le visualizzazioni con tendenze orarie di queste metriche e variabili critiche (o configura [avvisi](/help/components/alerts/alerts-overview.md) per ogni metrica). Poi monitorali per uno o due giorni per assicurarti di ottenere i dati previsti e corretti. Cerca i punti di flesso. Preparati a risolvere immediatamente eventuali problemi critici. Se riscontri delle discrepanze, cerca nel livello dati, nelle regole di gestione dei tag e nelle regole di elaborazione per scoprirne il motivo.
* Esegui nuovamente [Analytics Health Dashboard](https://express.adobe.com/page/tnNQGNlfzta3b/) per monitorare le tendenze generali delle metriche e delle variabili KPI.

*Per ulteriori dettagli su come verificare che le metriche e le variabili funzionino correttamente, [leggi questi suggerimenti](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) da Sarah Owen, Champion Adobe Analytics.*

## &#x200B;3. Esamina attentamente i dati provenienti dalla sezione aggiornata del tuo sito

Assicurati che la versione più recente del sito non abbia avuto un impatto negativo sulla raccolta dati per quella sezione del sito: controlla tutti i codici e le variabili corrispondenti a quella sezione per assicurarti che il nuovo tracciamento funzioni come previsto.

## &#x200B;4. Aggiornare la documentazione

Se hai aggiunto o modificato metriche o variabili di recente, devi aggiornare il tuo documento sui requisiti aziendali (BRD) e Solution Design Reference (SDR).

Se non disponi di documentazione sull&#39;implementazione, esporta un elenco di variabili e crea il tuo BRD o SDR utilizzando [questo modello](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html#implementation).

## &#x200B;5. Risolvi immediatamente eventuali lacune nella qualità dei dati

Valuta la situazione ed elabora un piano per correggere i dati. Quindi apporta le modifiche necessarie, aggiorna la documentazione e informa le parti interessate sulle modifiche apportate.

*Guarda questo video di 2 minuti di Sarah Owen, Adobe Analytics Champion, sui momenti naturali in cui puoi inserire le recensioni della tua implementazione alla tua fitta agenda:*


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Verifica dell&#39;implementazione](https://video.tv.adobe.com/v/328340?quality=12&learn=on){target="_blank"} per vedere un video dimostrativo.

>[!ENDSHADEBOX]


