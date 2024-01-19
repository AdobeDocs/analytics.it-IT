---
description: Il nuovo sistema intelligente di avvisi offre un controllo più granulare sugli avvisi e integra il rilevamento delle anomalie con il sistema di avvisi.
title: Panoramica degli avvisi intelligenti
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 73%

---

# Panoramica degli avvisi intelligenti

Il sistema intelligente di avvisi offre un controllo più granulare sugli avvisi e integra il rilevamento delle anomalie con il sistema di avvisi.

Questo è un tutorial video sugli [avvisi intelligenti](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=it) (5:34)

## Panoramica

La funzione Avvisi intelligenti permette di:

* Creare avvisi basati su anomalie (soglie del 90%, 95%, 99%, 99,75% e 99,9%; modifica della percentuale; superiore/inferiore)
* Visualizzare in anteprima la frequenza di attivazione degli avvisi
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso

Esistono tre modi per accedere al generatore di avvisi:

| Metodo | Dettagli |
| --- | --- |
| Vai direttamente al Generatore di avvisi | **[!UICONTROL Components]** > **[!UICONTROL Alerts]** |
| Utilizzare i tasti di scelta rapida in Workspace | `Ctrl + Shift + A` (Windows) o `Cmd + Shift + A` (Mac) |
| Seleziona una o più voci di tabella a forma libera | Fai clic con il pulsante destro del mouse e seleziona (Copia negli Appunti) **[!UICONTROL Create Alert from Selection]**. Verrà aperto il [!UICONTROL Alert Builder] e precompila le metriche e i filtri appropriati applicati dalla tabella. Se necessario, puoi modificare l’avviso. ![Crea avviso da selezione](assets/create-alert-from-selection.png) |

Le soglie espresse in % rappresentano le deviazioni standard. Ad esempio, 95% = 2 deviazioni standard e 99% = 3 deviazioni standard. A seconda della granularità temporale scelta, [diversi modelli](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) vengono utilizzati per calcolare lo scarto (ossia il numero di deviazioni standard) tra ciascun punto dati e il valore di norma. Impostando un valore di soglia basso (ad esempio 90%), si ottengono più anomalie rispetto a quando si imposta un valore superiore (99,75%).

>[!IMPORTANT]
>
>L’utilizzo di dati con marcatura temporale per la creazione di avvisi potrebbe causarne l’attivazione in modo errato. Per gli avvisi intelligenti, Adobe consiglia di utilizzare dati privi di marcatura temporale.

## Ricerca delle anomalie per gli avvisi

Se un avviso utilizza il rilevamento delle anomalie, il periodo di formazione varia in base alla granularità selezionata per l’avviso.

* Granularità mensile: 15 mesi + lo stesso intervallo relativo allo scorso anno
* Granularità settimanale: 15 settimane + lo stesso intervallo relativo allo scorso anno
* Granularità giornaliera: 35 giorni + lo stesso intervallo relativo allo scorso anno
* Granularità oraria: 336 ore

Per ulteriori informazioni, vedi [Tecniche di statistica utilizzate nel rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md).
