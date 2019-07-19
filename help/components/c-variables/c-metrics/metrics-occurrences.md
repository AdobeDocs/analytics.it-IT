---
description: Il numero di volte in cui viene acquisito un valore specifico, più il numero di visualizzazioni di pagina per le quali il valore specificato viene mantenuto. In altre parole, Occorrenze sono somma di visualizzazioni di pagina e eventi di pagina. Occorrenze sono disponibili in Analysis Workspace e in Analisi ad hoc.
seo-description: Il numero di volte in cui viene acquisito un valore specifico, più il numero di visualizzazioni di pagina per le quali il valore specificato viene mantenuto. In altre parole, Occorrenze sono somma di visualizzazioni di pagina e eventi di pagina. Occorrenze sono disponibili in Analysis Workspace e in Analisi ad hoc.
seo-title: Occorrenze
solution: Analytics
title: Occorrenze
topic: Metrics (Metriche)
uuid: ff 999 fba-fcb 7-4 b 16-9446-001 facd 0 f 15 d
translation-type: tm+mt
source-git-commit: ecc762f73f9a303cebf48668b807fef9a2f055c5

---


# Occorrenze

Il numero di volte in cui viene acquisito un valore specifico, più il numero di visualizzazioni di pagina per le quali il valore specificato viene mantenuto. In altre parole, Occorrenze sono somma di visualizzazioni di pagina e eventi di pagina. Occorrenze sono disponibili in Analysis Workspace e in Analisi ad hoc.

## Comparing Instances and Occurrences {#section_4B0741AC1A78456E98AE0D4D28D70D29}

Sono elencate due metriche che risultano simili:

**[Istanze](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)**: Il numero di volte in cui è stato impostato un valore per una variabile.

**Occorrenze**: Il numero totale di volte in cui un valore è stato impostato o persistente.

| Situazione | Descrizione |
|---|---|
| Occorrenze superiori alle istanze | Ciò è previsto per le variabili di conversione, poiché le occorrenze includono anche quante volte è stata definita la variabile (istanze). |
| Istanze più alte di Occorrenze | Ciò non è possibile nei rapporti, poiché tutte le istanze vengono registrate anche come occorrenze. |
| Istanze uguali ad Occorrenze | Ciò è più comune per le variabili di traffico, in quanto per natura non persistono oltre la richiesta di immagine. |

>[!MORE_ LIKE_ THIS]
>
>* [Istanze](/help/components/c-variables/c-metrics/metrics-instance.md)

