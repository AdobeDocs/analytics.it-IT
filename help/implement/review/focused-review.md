---
title: Revisione mirata (dopo ogni rilascio del sito web)
description: Segui questi passaggi per garantire che l’implementazione rimanga priva di errori e in linea con i KPI.
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
role: Admin, Leader
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 68%

---

# Revisione mirata (dopo ogni rilascio del sito web)

Perché dovresti rivedere la tua implementazione ogni mese? È quindi possibile risolvere qualsiasi problema relativo alla qualità dei dati mentre sono ancora contenuti. Se esegui regolarmente questa revisione incentrata dopo ogni versione del sito web, scoprirai che le tue [revisioni complete](/help/implement/review/full-review.md) semestrali saranno molto più facili. Eviterai inoltre che i problemi di piccole dimensioni si trasformino in problemi di dati di grandi dimensioni che potrebbero erodere la fiducia delle parti interessate.

## 1. Inizia con i primi 5 KPI

Conoscere i primi 5 indicatori di prestazioni chiave (KPI, Key Performance Indicators) ti aiuterà a determinare le metriche e le dimensioni associate che devi esaminare. Se non hai aggiornato i KPI negli ultimi 6 mesi o se la tua azienda non ha ancora creato i KPI, segui [queste istruzioni](/help/implement/review/define-kpis.md).

## 2. Assicurati che le metriche e le variabili KPI continuino a funzionare bene

Gli aggiornamenti del codice nel tempo possono avere ramificazioni non desiderate. Assicurati che tutte le metriche e le dimensioni associate ai tuoi [primi 5 KPI](/help/implement/review/define-kpis.md) funzionino ancora correttamente. Idealmente, questo viene fatto subito dopo il rilascio di un sito Web; se non lo hai fatto negli ultimi mesi, fallo *ora*. Per eseguire questa operazione:

* Crea dashboard per visualizzare le visualizzazioni con tendenze orarie di queste metriche e variabili critiche (o configura [avvisi](https://experienceleague.adobe.com/docs/analytics/components/alerts/intellligent-alerts.html?lang=it) per ogni metrica). Poi monitorali per uno o due giorni per assicurarti di ottenere i dati previsti e corretti. Cerca i punti di flesso. Preparati a risolvere immediatamente eventuali problemi critici. Se riscontri delle discrepanze, cerca nel livello dati, nelle regole di gestione dei tag e nelle regole di elaborazione per scoprirne il motivo.
* Esegui nuovamente [Analytics Health Dashboard](https://express.adobe.com/page/tnNQGNlfzta3b/) per monitorare le tendenze generali delle metriche e delle variabili KPI.

*Per ulteriori dettagli su come verificare che le metriche e le variabili funzionino correttamente, [leggi questi suggerimenti](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) da Sarah Owen, Champion Adobe Analytics.*

## 3. Esamina accuratamente i dati della sezione aggiornata del tuo sito

Assicurati che la versione più recente del sito non abbia avuto un impatto negativo sulla raccolta dati per quella sezione del sito: controlla tutti i codici e le variabili corrispondenti a quella sezione per assicurarti che il nuovo tracciamento funzioni come previsto.

## 4. Aggiorna la documentazione

Se hai aggiunto o modificato metriche o variabili di recente, devi aggiornare il tuo documento sui requisiti aziendali (BRD) e Solution Design Reference (SDR).

Se non disponi di documentazione sull&#39;implementazione, esporta un elenco di variabili e crea il tuo BRD o SDR utilizzando [questo modello](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html#implementation).

## 5. Risolvi immediatamente eventuali lacune nella qualità dei dati

Valuta la situazione ed elabora un piano per correggere i dati. Quindi apporta le modifiche necessarie, aggiorna la documentazione e informa le parti interessate sulle modifiche apportate.

*Guarda questo video di 2 minuti di Sarah Owen, Adobe Analytics Champion, sui momenti naturali in cui puoi inserire le recensioni della tua implementazione alla tua fitta agenda:*


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Verifica dell&#39;implementazione](https://video.tv.adobe.com/v/328340?quality=12&learn=on){target="_blank"} per vedere un video dimostrativo.

>[!ENDSHADEBOX]


