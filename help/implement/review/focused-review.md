---
title: Recensione focalizzata (dopo ogni rilascio del sito Web)
description: Segui questi passaggi per assicurarti che l’implementazione rimanga priva di errori e in linea con i tuoi KPI.
translation-type: tm+mt
source-git-commit: 912e5077889a02c3bf0dea9b079d213bb20f9424
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Recensione focalizzata (dopo ogni rilascio del sito Web)

Perché dovresti rivedere la tua implementazione ogni qualche mese? È quindi possibile risolvere qualsiasi problema con la qualità dei dati, mentre sono ancora piccoli. Se effettui questa revisione incentrata sulle attività successive a ogni versione del sito Web, troverai che le [revisioni complete](/help/implement/review/full-review.md) annuali sono molto più semplici. Inoltre, impedirete che le questioni minori diventino problematiche relative ai grandi dati, il che potrebbe erodere la fiducia dei soggetti interessati.

## 1. Inizia con i primi 5 KPI

Conoscere i primi 5 indicatori di prestazioni chiave (KPI) ti aiuterà a determinare le metriche e le dimensioni associate che devi esaminare. Se non hai aggiornato i KPI negli ultimi 6 mesi o se la tua azienda non ha ancora creato KPI, segui [le seguenti istruzioni](/help/implement/review/define-kpis.md).

## 2. Assicurati che le metriche e le variabili KPI continuino a funzionare correttamente

Gli aggiornamenti di codice nel tempo possono avere conseguenze indesiderate. Assicurarsi che tutte le metriche e le dimensioni associate ai [primi 5 KPI](/help/implement/review/define-kpis.md) funzionino ancora correttamente. Idealmente, ciò dovrebbe essere fatto subito dopo il rilascio di un sito web; se non lo avete fatto negli ultimi mesi, fatelo *now*. Per eseguire questa operazione:

* Crea dashboard per visualizzare le viste con tendenze orarie di queste metriche e variabili critiche (oppure configura [avvisi intelligenti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace) per ogni metrica). Quindi controllateli per uno o due giorni per assicurarvi di ottenere i dati previsti e che i dati siano corretti. Cercare punti di flessione. Preparati a risolvere immediatamente qualsiasi problema critico. Se riscontri delle discrepanze, consulta il livello dati, le regole di gestione tag e le regole di elaborazione per scoprire il perché.
* Eseguire nuovamente il [dashboard integrità Analytics](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) per monitorare le tendenze generali delle metriche e delle variabili KPI.

*Per ulteriori dettagli su come garantire il corretto funzionamento delle metriche e delle variabili,  [leggi questi ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) suggerimenti  campione Adobe Analytics Sarah Owen.*

## 3. Esaminate attentamente i dati dalla sezione aggiornata del sito

Assicurati che la versione del sito più recente non abbia avuto un impatto negativo sulla raccolta dei dati per quella sezione del sito: controlla tutti i codici e le variabili corrispondenti a tale sezione per verificare che il nuovo tracciamento funzioni correttamente.

## 4. Aggiornare la documentazione

Se hai aggiunto o modificato di recente metriche o variabili, devi aggiornare il tuo documento BRD (Business Requirement Document) e il documento di riferimento per la progettazione della soluzione (SDR).

Se non disponete della documentazione relativa all&#39;implementazione, esportate un elenco di variabili e create il BRD o il DSP utilizzando [questo modello](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 5. Risolvi immediatamente eventuali lacune riscontrate nella qualità dei dati

Valutare la situazione ed elaborare un piano per porre rimedio ai dati. Quindi apportate le modifiche necessarie, aggiornate la documentazione e informate le parti interessate sulle modifiche apportate.

*Guarda questo video di 2 minuti  Campione Adobe Analytics Sarah Owen sui momenti naturali in cui puoi adattare le recensioni della tua implementazione alla tua programmazione:*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
