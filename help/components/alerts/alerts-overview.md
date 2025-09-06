---
description: Scopri come utilizzare gli avvisi per consentire un controllo granulare sulle notifiche e l’integrazione con il rilevamento delle anomalie.
title: Panoramica sugli avvisi
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 53%

---

# Panoramica sugli avvisi

Gli avvisi in Adobe Analytics ti consentono di ricevere notifiche in base alle percentuali modificate o a punti dati specifici.

A seconda del pacchetto Adobe Analytics, puoi anche utilizzare gli avvisi da attivare in base alle soglie delle anomalie. Questi avvisi (noti anche come “Avvisi intelligenti”) forniscono controlli granulari che si integrano con il [Rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md), attivandosi quando sono più necessari.

Gli avvisi permettono di:

* Visualizzare in anteprima la frequenza di attivazione degli avvisi
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso
* Creare avvisi basati su anomalie (soglie del 90%, 95%, 99%, 99,75% e 99,9%; modifica della percentuale; superiore/inferiore) (Disponibile solo per i clienti Adobe Analytics con un pacchetto Select, Prime o Ultimate)

Il seguente tutorial video fornisce una panoramica di base degli avvisi: [Avvisi](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=it) (5:34)

## Ricerca delle anomalie per gli avvisi

>[!NOTE]
>
>L&#39;utilizzo degli avvisi con rilevamento delle anomalie (noti anche come _avvisi intelligenti_) è disponibile solo per le organizzazioni con un pacchetto Adobe Analytics Prime o Ultimate.

Se un avviso utilizza il rilevamento delle anomalie, il periodo di formazione varia in base alla granularità selezionata per l’avviso.

* Granularità mensile: 15 mesi + lo stesso intervallo relativo allo scorso anno
* Granularità settimanale: 15 settimane + lo stesso intervallo relativo allo scorso anno
* Granularità giornaliera: 35 giorni + lo stesso intervallo relativo allo scorso anno
* Granularità oraria: 336 ore

Per ulteriori informazioni, consulta [Tecniche statistiche utilizzate nel rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Creare avvisi

Per informazioni sulla creazione di avvisi in Adobe Analytics, consulta [Creare avvisi](/help/components/alerts/alert-builder.md).

>[!IMPORTANT]
>
>L’utilizzo di dati con marcatura temporale per la creazione di avvisi potrebbe causarne l’attivazione in modo errato. Per gli avvisi, Adobe consiglia di utilizzare dati senza marca temporale.

## Gestire gli avvisi

Puoi gestire gli avvisi esistenti in Gestione avvisi. Puoi eseguire varie attività di gestione degli avvisi, ad esempio assegnare tag, rinominare, eliminare e altro ancora.

Per ulteriori informazioni su come gestire gli avvisi esistenti in Adobe Analytics, consulta [Gestire gli avvisi](/help/components/alerts/alert-manager.md).
