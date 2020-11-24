---
title: Revisione dell’implementazione secondaria (dopo ciascuna versione del sito Web)
description: Segui questi passaggi per assicurarti che l’implementazione rimanga priva di errori e in linea con i tuoi KPI.
translation-type: tm+mt
source-git-commit: 82064e267729b6995402bd122c6f71b3d38967a3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# Revisione dell’implementazione secondaria (dopo ciascuna versione del sito Web)

Perché rivedete la vostra implementazione dopo ogni versione del sito Web? Poiché devi essere certo che gli aggiornamenti di codice non abbiano conseguenze indesiderate e che ti consigliamo di risolvere eventuali problemi relativi alla qualità dei dati anche se sono ancora di piccole dimensioni. Se effettui questa revisione secondaria dopo ogni rilascio del sito Web, le tue revisioni [](/help/implement/review/major-review.md) principali (ogni 6 mesi) risulteranno molto più semplici. Inoltre, impedirete che le questioni minori diventino problematiche relative ai grandi dati, il che potrebbe erodere la fiducia dei soggetti interessati.

## 1. In che modo la release ha influito sui dati per quella sezione del sito?

Effettuare test di unità completi: Controlla tutti i codici e le variabili che corrispondono alla sezione del sito appena aggiornata per assicurarti che il nuovo tracciamento funzioni correttamente.

## 2. Aggiornare la documentazione

Aggiorna il documento di riferimento per il requisito aziendale (BRD) e la soluzione (SDR) con tutte le variabili aggiunte o modificate per consentire il lancio.

Non disponete della documentazione relativa alla vostra implementazione? Esportate un elenco di variabili e create il vostro BRD o SDR utilizzando [questo modello](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 3. Inizia con i primi 5 KPI

Conoscere i primi 5 indicatori di prestazioni chiave (KPI) ti aiuterà a determinare le metriche e le dimensioni associate che devi esaminare. Se non hai aggiornato i KPI negli ultimi 6 mesi o se la tua azienda non ha ancora creato KPI, segui [queste istruzioni](/help/implement/review/define-kpis.md).

## 4. Tutte le metriche e le variabili KPI funzionano ancora correttamente dopo il rilascio?

Tenete presente che qualsiasi aggiornamento del codice può avere delle ramificazioni non desiderate. Assicurati che tutte le metriche e le dimensioni associate ai [tuoi primi 5 KPI](/help/implement/review/define-kpis.md) funzionino ancora correttamente. Per eseguire questa operazione:

* **Crea dashboard** per visualizzare le viste con tendenze orarie di queste metriche e variabili critiche. Puoi anche impostare avvisi intelligenti per ogni metrica) e monitorarli per uno o due giorni dopo il rilascio, per assicurarti di ottenere i dati previsti e che i dati siano corretti. Cercare punti di flessione. Preparati a risolvere immediatamente qualsiasi problema critico. Se riscontri delle discrepanze che non sembrano corrette, osserva il livello dati, le regole di gestione dei tag e le regole di elaborazione per scoprire il perché.
* **Esegui di nuovo il Pannello** integrità di Analytics per monitorare le tendenze generali delle metriche e delle variabili KPI.
Per ulteriori dettagli su come garantire il corretto funzionamento delle metriche e delle variabili, leggete questi suggerimenti  campione Adobe Analytics Sarah Owen.

## 5. Ci sono lacune nella qualità dei dati?

Valutare la situazione ed elaborare un piano per porre rimedio ai dati. Quindi apportate le modifiche necessarie, aggiornate la documentazione e informate le parti interessate sulle modifiche apportate.

Guardate questo video  Campione Adobe Analytics Sarah Owen sui momenti naturali in cui è possibile adattare le recensioni della vostra implementazione al vostro programma impegnato:

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
