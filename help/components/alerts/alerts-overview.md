---
description: Scopri come utilizzare gli avvisi per consentire un controllo granulare sulle notifiche e l’integrazione con il rilevamento delle anomalie.
title: Panoramica sugli avvisi
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 30%

---

# Panoramica sugli avvisi

Gli avvisi in Adobe Analytics ti consentono di ricevere notifiche in base alle percentuali modificate o a punti dati specifici.

A seconda del pacchetto Adobe Analytics, puoi anche utilizzare gli avvisi da attivare in base alle soglie delle anomalie. Questi avvisi (noti anche come *Avvisi intelligenti*) forniscono controlli granulari che si integrano con [Rilevamento anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md), attivandosi quando sono più necessari.

Gli avvisi permettono di:

* Visualizzare in anteprima la frequenza di attivazione di un avviso.
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente.
* Crea avvisi *in pila* che acquisiscono più metriche in un singolo avviso.
* Creare avvisi in base a:
   * Le anomalie nelle metriche esistenti sono superiori o inferiori ai valori di soglia previsti.

     [Il rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) genera un valore previsto più un limite superiore e inferiore utilizzando i dati storici. Se il valore della metrica effettiva supera il limite superiore o inferiore al limite inferiore definito come valore di soglia, tale evento viene considerato un’anomalia al livello di affidabilità della soglia e attiva l’avviso. Una soglia più elevata (ad esempio, 99% o 99,9%) implica una banda più ampia e comporta un minor numero di avvisi causati da anomalie più estreme. Una soglia più bassa (ad esempio, 90%) implica una banda più stretta, il che si traduce in un maggior numero di avvisi causati da anomalie meno estreme.
   * Modifiche nelle metriche di una percentuale specifica.
   * Metriche superiori, inferiori o uguali a un valore specifico. (disponibile solo per i clienti Adobe Analytics con un pacchetto Select, Prime o Ultimate)

Questa [esercitazione video](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/data-science/intelligent-alerts) fornisce una panoramica di base degli avvisi.


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
