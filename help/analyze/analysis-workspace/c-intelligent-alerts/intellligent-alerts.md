---
description: Il nuovo sistema intelligente di avvisi offre un controllo più granulare sugli avvisi e integra il rilevamento delle anomalie con il sistema di avvisi.
title: Panoramica degli avvisi intelligenti
feature: Alerts
role: User, Admin
exl-id: 49d47896-bf93-4960-b647-2765c935eb25
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 86%

---

# Panoramica degli avvisi intelligenti

Il sistema intelligente di avvisi offre un controllo più granulare sugli avvisi e integra il rilevamento delle anomalie con il sistema di avvisi.

Questo è un tutorial video sugli [avvisi intelligenti](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=it) (5:34)

## Panoramica

Le nuove funzioni Generatore di avvisi e Gestione avvisi di Analysis Workspace sostituiscono la funzione di avvisi di Reports &amp; Analytics. La funzione Avvisi intelligenti permette di:

* Creare avvisi basati su anomalie (soglie del 90%, 95%, 99%, 99,75% e 99,9%; modifica della percentuale; superiore/inferiore)
* Visualizzare in anteprima la frequenza di attivazione degli avvisi
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso

È possibile accedere al Generatore di avvisi in quattro modi:

| Metodo | Dettagli |
| --- | --- |
| Passa direttamente al Generatore di avvisi | **[!UICONTROL Components]** > **[!UICONTROL Alerts]** |
| Utilizzare le scelte rapide da tastiera in Workspace | `Ctrl + Shift + A` (Windows) o `Cmd + Shift + A` (Mac) |
| Seleziona una o più voci di tabella a forma libera | Fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Create Alert from Selection]**. Viene aperta la [!UICONTROL Alert Builder] precompila le metriche appropriate e i filtri applicati dalla tabella. Se necessario, puoi quindi modificare l’avviso. ![Crea avviso da selezione](assets/create-alert-from-selection.png) |
| Da un rapporto Reports &amp; Analytics | Vai a  **[!UICONTROL More]** > **[!UICONTROL Add Alert]** . Verrà aperto il Generatore di avvisi, precompilato con le metriche appropriate e i filtri applicati dal report. Se necessario, puoi quindi modificare l’avviso. ![Aggiungi avviso](assets/add-alert.png) |

Le soglie espresse in % rappresentano le deviazioni standard. Ad esempio, 95% = 2 deviazioni standard e 99% = 3 deviazioni standard. In funzione della granularità temporale scelta, vengono utilizzati [modelli differenti](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) per calcolare lo scarto (ossia il numero di deviazioni standard) tra ciascun punto dati e il valore di norma. Impostando un valore di soglia basso (ad esempio 90%), si ottengono più anomalie rispetto a quando si imposta un valore superiore (99,75%).

>[!IMPORTANT]
>
>L’utilizzo di dati con marcatura temporale per la creazione di avvisi potrebbe causarne l’attivazione in modo errato. Per gli avvisi intelligenti, Adobe consiglia di utilizzare dati privi di marcatura temporale.

## Ricerca delle anomalie per gli avvisi

Se un avviso utilizza il rilevamento delle anomalie, il periodo di formazione varia in base alla granularità selezionata per l’avviso.

* Granularità mensile: 15 mesi + lo stesso intervallo relativo allo scorso anno
* Granularità settimanale: 15 settimane + lo stesso intervallo relativo allo scorso anno
* Granularità giornaliera: 35 giorni + lo stesso intervallo relativo allo scorso anno
* Granularità oraria: 336 ore

Per ulteriori informazioni, vedi [Tecniche di statistica utilizzate nel rilevamento delle anomalie](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md).
