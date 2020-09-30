---
description: In Analysis Workspace è possibile visualizzare e analizzare le anomalie nei dati in modo contestuale.
title: Panoramica di Rilevamento delle anomalie
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 56ca9fa36db9d7dd126808280ba17f29f4b787d9
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 90%

---


# Panoramica di Rilevamento delle anomalie

In Analysis Workspace è possibile visualizzare e analizzare le anomalie nei dati in modo contestuale.

[Esercitazione](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html) video sul rilevamento delle anomalie (4:53)

[Esercitazione](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/data-science/contribution-analysis-workspace.html) video Analisi contributi (3:20)

>[!IMPORTANT]
>
>La funzione Rilevamento delle anomalie è stata rimossa da Reports &amp; Analytics ed è ora disponibile solo tramite Analysis Workspace. I clienti Select e Foundation di Adobe Analytics possono accedere solo alla funzione Rilevamento anomalie con granularità giornaliera in Workspace. Per ulteriori informazioni, consulta [Adesioni a Rilevamento delle anomalie e Analisi contributi](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A).

Il rilevamento anomalie fornisce un metodo statistico per determinare il cambiamento di una data metrica in relazione ai dati precedenti.

Consente di separare i “segnali effettivi” da quelli di “disturbo” e quindi di individuare i potenziali fattori che hanno contribuito al verificarsi di tali segnali o anomalie. In altre parole, permette di individuare le fluttuazioni statistiche rilevanti da quelle che non lo sono, e quindi di arrivare alla causa di fondo di una anomalia effettiva. Inoltre, è possibile ottenere previsioni di metriche affidabili (KPI).

Ecco alcuni esempi di anomalie da esaminare:

* Drastico calo nel valore medio degli ordini
* Picchi negli ordini con fatturato basso
* Picchi o calo nelle registrazioni di prova
* Calo nelle visualizzazioni della pagina di destinazione
* Picchi negli eventi di buffering video
* Picchi nei valori più bassi di bitrate video

[Rilevamento delle anomalie](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) e Analisi contributi sono flussi di lavoro principali in Analysis Workspace. Puoi eseguire Analisi contributi rispetto a qualsiasi anomalia giornaliera e incorporare il risultato nel progetto Analysis Workspace.

L’algoritmo di rilevazione delle anomalie di Analysis Workspace include:

* Supporto per la granularità oraria, settimanale e mensile, oltre a quella giornaliera già supportata
* Supporto per la stagionalità (ad esempio “Black Friday”) e le festività
