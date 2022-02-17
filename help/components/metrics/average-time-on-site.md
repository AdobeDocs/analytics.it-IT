---
title: Tempo medio sul sito
description: Il tempo medio in cui un dato elemento dimensione esisteva tra i risultati.
feature: Metrics
exl-id: bf9056e2-4f6d-4c4f-b641-d3146ce269ff
source-git-commit: 7966c7d9add0011831c97fbe0dfcca2acd8afb58
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 2%

---

# Tempo medio sul sito

La metrica &quot;Tempo medio sul sito&quot; mostra la quantità di tempo trascorso tra gli hit per un dato elemento dimensione. Questa metrica è utile quando desideri visualizzare il tempo medio trascorso per specifici elementi dimensionali. Puoi anche eseguire una tendenza di questa metrica nel tempo per vedere come cambia il tempo trascorso complessivo. Questa metrica viene visualizzata in `HH:MM:SS` formato.

Questa metrica è correlata al [Tempo trascorso per visita](../dimensions/time-spent-per-visit.md) dimensione.

## Calcolo di questa metrica

Per un dato elemento dimensionale, prendere la marca temporale di ogni hit in cui esiste tale elemento dimensione. Confrontatelo con la marca temporale dell’hit successivo nella visita. Se l&#39;hit non ha un hit successivo, non includerlo in questa metrica. Di tutto il tempo trascorso per l’elemento dimensione, dividerli tutti per il numero di &quot;sequenze&quot; per l’elemento dimensione. Una &quot;sequenza&quot; è il punto in cui un elemento dimensione è lo stesso per uno o più hit consecutivi. Questo numero risultante è la metrica visualizzata nei rapporti.

Ad esempio, considera la seguente visita:

| `Timestamp` | `Page` |
| --- | --- |
| `12:03:00` | `Home page` |
| `12:04:20` | `Product page A` |
| `12:05:30` | `Product page A` |
| `12:07:00` | `Product page B` |
| `12:07:40` | `Product page A` |
| `12:08:10` | `Checkout` |
| `12:10:00` | `Purchase` |
| `12:25:00` | `Home page` |
| `12:25:40` | `Product page A` |


Se si desidera un tempo medio sul sito per l’elemento dimensione `Product page A`, considera innanzitutto la quantità di tempo trascorso tra gli hit per quella dimensione:

* **12:04:20 - 12:05:30** - 1 minuto 10 secondi
* **12:05:30 - 12:07:00** - 1 minuto 30 secondi
* **12:07:40 - 12:08:10** - 30 secondi
* **12:25:40 - ?** - Non incluso

Quantità totale di tempo trascorso per `Product page A` è `00:03:10`. Ci sono state due sequenze in questa visita; la prima sequenza per i due valori consecutivi e la seconda prima del pagamento. L’ultimo hit della visita non è una sequenza, in quanto non esiste una marca temporale di fine.

Tempo medio sul sito per `Product page A` è `00:01:35`.

>[!NOTE]
>
>Questa metrica mostra un valore di `"Invalid"` se l’elemento dimensionale contiene solo gli hit dell’ultima visita. Questa metrica richiede un hit successivo per tenere traccia del tempo trascorso.

## Tempo medio trascorso sul sito (secondi)

La metrica &quot;Tempo medio trascorso sul sito (secondi)&quot; mostra gli stessi dati presentati come un numero intero anziché in `HH:MM:SS` formato. Questa metrica è più preziosa come componente all’interno delle metriche calcolate.

## I totali di suddivisione non corrispondono alla voce della riga padre

La metrica &quot;Tempo medio sul sito&quot; utilizza sequenze non interrotte di una data dimensione. La dimensione di suddivisione non dipende dalla dimensione padre quando si calcolano queste sequenze. Ad esempio, considera la seguente visita:

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

Calcolo del tempo medio sul sito per l’elemento dimensione `Home` utilizza il seguente calcolo:

```text
(30 + 10) / 2 = 20 seconds average time on site
```

Se hai applicato un raggruppamento utilizzando [Sezioni del sito](../dimensions/site-section.md) utilizza il seguente calcolo:

```text
(30 + 10) / 1 = 40 seconds average time on site
```

Poiché nella dimensione di suddivisione era presente una singola sequenza, utilizza un denominatore diverso da quello della dimensione padre. Queste metriche solitamente forniscono risultati simili a livello di visita, ma possono essere diverse a livello di hit.

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo medio sul sito dell’intera dimensione e il numeratore è il tempo medio sul sito dell’elemento dimensionale. Se il tempo medio sul sito dell’intera dimensione è inferiore al tempo medio sul sito di un dato elemento dimensione, le percentuali saranno superiori al 100%. L’ordinamento dei rapporti con classifica in base a questa metrica mostra un tempo medio anomalo sui valori del sito, che in genere non è prezioso. L’Adobe consiglia l’ordinamento in base a un’altra metrica, ad esempio [Visite](visits.md), in rapporti con classifica.

Vedi [Panoramica del tempo trascorso](time-spent.md) informazioni più generali sul tempo trascorso.
