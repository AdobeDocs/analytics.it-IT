---
description: Il numero di volte in cui un valore specifico viene acquisito, più il numero di visualizzazioni di pagina per cui il valore specificato è persistente. In altre parole, le occorrenze sono una somma delle visualizzazioni di pagina e degli eventi di pagina. Le occorrenze sono disponibili in Analysis Workspace e in Analisi ad hoc.
seo-description: Il numero di volte in cui un valore specifico viene acquisito, più il numero di visualizzazioni di pagina per cui il valore specificato è persistente. In altre parole, le occorrenze sono una somma delle visualizzazioni di pagina e degli eventi di pagina. Le occorrenze sono disponibili in Analysis Workspace e in Analisi ad hoc.
seo-title: Occorrenze
solution: Analytics
title: Occorrenze
topic: Metriche
uuid: ff999fba-fcb7-4b16-9446-001facd0f15d
translation-type: tm+mt
source-git-commit: ed22e0520bf1c7427ead039fb1d0391f2f1e567f

---


# Occorrenze

Il numero di volte in cui un valore specifico viene acquisito, più il numero di visualizzazioni di pagina per cui il valore specificato è persistente. In altre parole, le occorrenze sono una somma delle visualizzazioni di pagina e degli eventi di pagina. Le occorrenze sono disponibili in Analysis Workspace e in Analisi ad hoc.

## Confronto di istanze e occorrenze {#section_4B0741AC1A78456E98AE0D4D28D70D29}

Vengono elencate due metriche che appaiono simili:

**[Istanze](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)**: Il numero di volte in cui un valore è stato impostato per una variabile.

**Occorrenze**: Il numero totale di volte in cui un valore è stato impostato o persistente.

| Situazione | Descrizione |
|---|---|
| Occorrenze superiori alle istanze | Questo è previsto per le variabili di conversione, in quanto le occorrenze includono anche il numero di volte in cui la variabile è stata definita (istanze). |
| Istanze superiori alle occorrenze | Ciò non è possibile nel reporting, in quanto tutte le istanze vengono registrate anche come occorrenze. |
| Istanze uguali alle occorrenze | Questo è il più comune per le variabili di traffico, poiché per loro natura non persistono oltre la richiesta di immagine. |

>[!MORELIKETHIS]
>
>* [Istanze](/help/components/c-variables/c-metrics/metrics-instance.md)

