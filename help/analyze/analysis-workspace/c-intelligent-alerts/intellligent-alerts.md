---
description: Il nuovo sistema intelligente di avvisi offre un controllo più granulare sugli avvisi e integra il rilevamento delle anomalie con il sistema di avvisi.
title: Panoramica degli avvisi intelligenti
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: 373a1ecffafdcefe3c7b60954f14c2f3a5ca386d
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 60%

---

# Panoramica degli avvisi intelligenti

Gli avvisi intelligenti (o semplicemente &quot;avvisi&quot;) in Adobe Analytics ti consentono di ricevere notifiche immediate quando si verificano eventi anomali nei tuoi dati.

Puoi impostare l’attivazione degli avvisi in base a soglie di anomalie, percentuali di modifica o punti dati specifici. Gli avvisi forniscono controlli granulari che si integrano con [Rilevamento anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md), attivandosi quando sono più necessari.

La funzione Avvisi intelligenti permette di:

* Creare avvisi basati su anomalie (soglie del 90%, 95%, 99%, 99,75% e 99,9%; modifica della percentuale; superiore/inferiore)
* Visualizzare in anteprima la frequenza di attivazione degli avvisi
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso

Il seguente tutorial video fornisce una panoramica di base degli avvisi: [Avvisi intelligenti](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=it) (5:34)

## Ricerca delle anomalie per gli avvisi

Se un avviso utilizza il rilevamento delle anomalie, il periodo di formazione varia in base alla granularità selezionata per l’avviso.

* Granularità mensile: 15 mesi + lo stesso intervallo relativo allo scorso anno
* Granularità settimanale: 15 settimane + lo stesso intervallo relativo allo scorso anno
* Granularità giornaliera: 35 giorni + lo stesso intervallo relativo allo scorso anno
* Granularità oraria: 336 ore

Per ulteriori informazioni, vedere [Tecniche di statistica utilizzate nel rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).

## Creare avvisi

Per informazioni sulla creazione di avvisi in Adobe Analytics, consulta [Creare avvisi](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md).

>[!IMPORTANT]
>
>L’utilizzo di dati con marcatura temporale per la creazione di avvisi potrebbe causarne l’attivazione in modo errato. Per gli avvisi intelligenti, Adobe consiglia di utilizzare dati privi di marcatura temporale.

## Gestire gli avvisi

È possibile gestire gli avvisi esistenti nella Gestione avvisi. È possibile eseguire varie attività di gestione sugli avvisi, ad esempio assegnare tag, rinominare, eliminare e altro ancora.

Per ulteriori informazioni su come gestire gli avvisi esistenti in Adobe Analytics, consulta [Gestire gli avvisi](/help/components/c-alerts/alert-manager.md).
