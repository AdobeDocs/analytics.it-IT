---
description: Il nuovo sistema intelligente di avvisi offre un controllo più granulare sugli avvisi e integra il rilevamento delle anomalie con il sistema di avvisi.
title: Panoramica degli avvisi intelligenti
uuid: b9bf75ad-bb6f-49fe-8c55-355ea3c50a71
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Panoramica degli avvisi intelligenti

La funzione Avvisi intelligenti consente un controllo più dettagliato degli avvisi e integra il rilevamento delle anomalie con il sistema di avvisi.

[Avvisi intelligenti su YouTube](https://www.youtube.com/watch?v=UVH9xr_2REA) (5:34)

## Panoramica

Le nuove funzioni Generatore di avvisi e Gestione avvisi di Analysis Workspace sostituiscono la funzione di avvisi di Reports &amp; Analytics. La funzione Avvisi intelligenti permette di::

* Creare avvisi basati su anomalie (soglie del 90%, 95%, 99%, 99,75% e 99,9%; modifica della percentuale; superiore/inferiore)
* Visualizzare in anteprima la frequenza di attivazione degli avvisi
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso

È possibile accedere al Generatore di avvisi in quattro modi:

* Passare direttamente al Generatore di avvisi:  **[!UICONTROL Components]** &gt; **[!UICONTROL Alerts]**
* Utilizzo della scelta rapida da tastiera in Workspace: `Ctrl + Shift + A` (Windows) o `Cmd + Shift + A` (Mac)
* Selezione di uno o più elementi di riga di una tabella a forma libera, clic con il pulsante destro del mouse e selezione **[!UICONTROL Create Alert from Selection]**. Viene aperto il Generatore di avvisi e precompilato le metriche appropriate e i filtri applicati dalla tabella. Se necessario, puoi modificare l’avviso.

   ![Creazione di un avviso da una selezione](assets/create-alert-from-selection.png)

* From within a Reports &amp; Analytics report, by going to  **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]** . Viene aperto il generatore di avvisi e precompilato le metriche appropriate e i filtri applicati dal rapporto. Se necessario, puoi modificare l’avviso.

   ![Aggiungi avviso](assets/add-alert.png)

Le soglie percentuali sono deviazioni standard. Ad esempio, 95% = 2 deviazioni standard e 99% = 3 deviazioni standard. In funzione della granularità temporale scelta, vengono utilizzati  [modelli differenti](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) per calcolare lo scarto (ossia il numero di deviazioni standard) tra ciascun punto dati e il valore di norma. Se si imposta una soglia inferiore (ad esempio 90%), si ottengono più anomalie rispetto a quando si imposta una soglia più elevata (99,75%).

> [!IMPORTANT] L’utilizzo di dati con marca temporale per creare avvisi può causare errori di attivazione degli avvisi. Adobe consiglia di utilizzare dati privi di marca temporale per gli avvisi intelligenti.

## Ricerca delle anomalie per gli avvisi

Se un avviso utilizza il rilevamento delle anomalie, il periodo di formazione varia in base alla granularità selezionata per l’avviso.

* Granularità mensile: 15 mesi + lo stesso intervallo dello scorso anno
* Granularità settimanale: 15 settimane + lo stesso intervallo dello scorso anno
* Granularità giornaliera: 35 giorni + lo stesso intervallo dello scorso anno
* Granularità oraria: 336 ore

Per ulteriori informazioni, consulta Tecniche [statistiche utilizzate in Rilevamento](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) anomalie.
