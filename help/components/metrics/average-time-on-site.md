---
title: Tempo medio sul sito
description: Il tempo medio in cui un dato valore di dimensione esisteva tra gli hit.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---


# Tempo medio sul sito

La metrica &quot;Tempo medio sul sito&quot; mostra il tempo passato tra gli hit per un dato valore di dimensione. Questa metrica è utile per visualizzare il tempo medio impiegato per valori di dimensione specifici. Puoi anche attribuire una tendenza a questa metrica nel tempo per vedere come cambia il tempo trascorso. Questa metrica viene visualizzata in `HH:MM:SS` formato.

Questa metrica è correlata alla dimensione [Tempo trascorso per visita](../dimensions/time-spent-per-visit.md) .

## Modalità di calcolo di questa metrica

Per un dato valore di dimensione, prendere la marca temporale di ogni hit in cui esiste tale valore. Confrontatelo con la marca temporale dell’hit successivo nella visita. Se l’hit non ha un hit successivo, non includetelo in questa metrica. Tra tutto il tempo trascorso per il valore della dimensione, dividerli tutti per il numero di &quot;sequenze&quot; per il valore della dimensione. Per &quot;sequenza&quot; si intende un valore di dimensione identico per uno o più hit consecutivi. Questo numero risultante è la metrica visualizzata nei report.

Ad esempio, considera quanto segue:

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


Se desiderate un tempo medio sul sito per il valore della dimensione, prendete prima il tempo trascorso tra gli hit per quella dimensione: `Product page A`

* **12:04:20 - 12:05:30** - 1 minuto 10 secondi
* **12:05:30 - 12:07:00** - 1 minuto 30 secondi
* **12:07:40 - 12:08:10** - 30 secondi
* **12:25:40 - ?** - Non incluso

Il tempo totale impiegato per `Product page A` è `00:03:10`. Questa visita ha avuto due conseguenze; la prima sequenza per i due valori consecutivi e la seconda prima del checkout. L&#39;ultimo hit della visita non è una sequenza, in quanto non è presente alcuna marca temporale di fine.

Il tempo medio sul sito per `Product page A` è `00:01:35`.

## Tempo medio trascorso sul sito (secondi)

La metrica &#39;Tempo medio trascorso sul sito (secondi)&#39; mostra gli stessi dati presentati come un numero intero invece che in `HH:MM:SS` formato. Questa metrica è particolarmente utile come componente nelle metriche calcolate.

## I totali di suddivisione non corrispondono all&#39;elemento della riga padre

La metrica &quot;Tempo medio sul sito&quot; utilizza sequenze non interrotte di una data dimensione. La dimensione di suddivisione non dipende dalla dimensione padre quando si calcolano queste sequenze. Ad esempio, considera quanto segue:

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

Per calcolare il tempo medio sul sito per il valore della dimensione `Home` viene utilizzato il seguente calcolo:

```text
(30 + 10) / 2 = 20 seconds average time on site
```

Se si applica una suddivisione utilizzando la dimensione sezioni [](../dimensions/site-section.md) Sito, verrà utilizzato il seguente calcolo:

```text
(30 + 10) / 1 = 40 seconds average time on site
```

Poiché nella dimensione di suddivisione era presente una singola sequenza, utilizza un denominatore diverso da quello della dimensione padre. Queste metriche forniscono in genere risultati simili a livello di visita, ma possono essere diverse a livello di hit.

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo medio sul sito dell&#39;intera dimensione e il numeratore è il tempo medio sul sito del valore della dimensione. Se il tempo medio sul sito dell&#39;intera dimensione è inferiore al tempo medio sul sito di un dato valore di dimensione, vengono visualizzate percentuali superiori al 100%. L&#39;ordinamento di report con classifica in base a questa metrica mostra il tempo medio anomalo sui valori del sito, che in genere non è prezioso. Adobe consiglia di ordinare i dati in base a un’altra metrica, ad esempio [Visite](visits.md), nei rapporti con classifica.

Consultate Panoramica sul [tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
