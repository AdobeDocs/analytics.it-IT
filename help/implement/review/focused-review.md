---
title: Revisione mirata (dopo ogni rilascio del sito web)
description: Segui questi passaggi per garantire che l’implementazione rimanga priva di errori e in linea con i KPI.
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 2%

---

# Revisione mirata (dopo ogni rilascio del sito web)

Perché dovresti rivedere la tua implementazione ogni qualche mese? È quindi possibile risolvere qualsiasi problema relativo alla qualità dei dati mentre sono ancora piccoli. Se esegui regolarmente questa revisione incentrata dopo ogni versione del sito web, scoprirai che la tua relazione biennale [Recensioni complete](/help/implement/review/full-review.md) Sono molto più facili. Impedisci inoltre che i problemi di piccole dimensioni si trasformino in problemi di big data che potrebbero erodere la fiducia delle parti interessate.

## 1. Inizia con i primi 5 KPI

Conoscere i primi 5 indicatori di prestazioni chiave (KPI, Key Performance Indicators) ti aiuterà a determinare le metriche e le dimensioni associate che devi esaminare. Se non hai aggiornato i KPI negli ultimi 6 mesi o se la tua azienda non ha ancora creato i KPI, segui [queste istruzioni](/help/implement/review/define-kpis.md).

## 2. Assicurati che le metriche e le variabili KPI funzionino ancora bene

Gli aggiornamenti del codice nel tempo possono avere ramificazioni non desiderate. Assicurati che tutte le metriche e le dimensioni associate al tuo [primi 5 KPI](/help/implement/review/define-kpis.md) funzionano ancora correttamente. Idealmente, questo dovrebbe essere fatto subito dopo il rilascio di un sito web; se non lo hai fatto negli ultimi mesi, fallo *now*. Per eseguire questa operazione:

* Crea dashboard per visualizzare le visualizzazioni con tendenze orarie di queste metriche e variabili critiche (o configura) [avvisi intelligenti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace) per ogni metrica). Poi monitorali per uno o due giorni per assicurarti di ottenere i dati previsti e i dati sono corretti. Cercare i punti di flesso. Preparati a risolvere immediatamente eventuali problemi critici. Se riscontri delle discrepanze, cerca nel livello dati, nelle regole di gestione dei tag e nelle regole di elaborazione per scoprirne il motivo.
* Esegui nuovamente il [Dashboard di stato di Analytics](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) per monitorare le tendenze generali delle metriche e delle variabili KPI.

*Per ulteriori dettagli su come verificare che le metriche e le variabili funzionino correttamente, [leggi questi suggerimenti](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) dalla Champion Adobe Analytics Sarah Owen.*

## 3. Esamina accuratamente i dati della sezione aggiornata del tuo sito

Assicurati che la versione più recente del sito non abbia avuto un impatto negativo sulla raccolta dati per quella sezione del sito: controlla tutti i codici e le variabili corrispondenti a quella sezione per assicurarti che il nuovo tracciamento funzioni come previsto.

## 4. Aggiornare la documentazione

Se hai aggiunto o modificato metriche o variabili di recente, devi aggiornare il tuo documento per i requisiti aziendali (BRD) e il riferimento per la progettazione della soluzione (SDR).

Se non disponi di documentazione sull’implementazione, esporta un elenco di variabili e crea il tuo BRD o SDR utilizzando [questo modello](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 5. Risolvere immediatamente eventuali lacune nella qualità dei dati

Valutare la situazione ed elaborare un piano per correggere i dati. Quindi apporta le modifiche necessarie, aggiorna la documentazione e informa le parti interessate sulle modifiche apportate.

*Guarda questo video di 2 minuti da Adobe Analytics Champion Sarah Owen sui momenti naturali in cui puoi inserire le recensioni della tua implementazione nella tua programmazione impegnata:*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
