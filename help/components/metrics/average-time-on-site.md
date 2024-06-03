---
title: Tempo medio sul sito
description: Il tempo medio in cui un dato elemento della dimensione è esistito tra gli hit.
feature: Metrics
exl-id: bf9056e2-4f6d-4c4f-b641-d3146ce269ff
source-git-commit: 9e140a6be5ab151d7a4e88e317c59eafea4d6e1d
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 2%

---

# Tempo medio sul sito

Il &#39;tempo medio sul sito&#39; [metrica](overview.md) mostra il tempo trascorso tra gli hit per un dato elemento dimensione. Questa metrica è utile quando desideri visualizzare il tempo medio trascorso per elementi dimensionali specifici. Puoi anche impostare la tendenza di questa metrica nel tempo per vedere come cambia il tempo trascorso. Questa metrica viene visualizzata in `HH:MM:SS` formato.

Questa metrica è correlata al [Tempo trascorso per visita](../dimensions/time-spent-per-visit.md) dimensione.

## Come è calcolata questa metrica

Per un dato elemento dimensione, considera la marca temporale di ogni hit in cui esiste tale elemento dimensione. Confrontalo con la marca temporale dell’hit successivo nella visita. Se l’hit non ha un hit successivo, non includerlo in questa metrica. Del tempo trascorso per l’elemento dimensione, dividili tutti per il numero di &quot;sequenze&quot; per tale elemento dimensione. Per &quot;sequenza&quot; si intende un elemento dimensionale identico per uno o più hit consecutivi. Questo numero risultante è la metrica visualizzata nei rapporti.

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


Se desideri un tempo medio sul sito per l’elemento dimensione `Product page A`, considera innanzitutto il periodo di tempo trascorso tra gli hit per quella dimensione:

* **12:04:20 — 12:05:30** - 1 minuto e 10 secondi
* **12:05:30 — 12:07:00** - 1 minuto e 30 secondi
* **12:07:40 — 12:08:10** - 30 secondi
* **12:25:40 - ?** - Non incluso

La quantità totale di tempo trascorso per `Product page A` è `00:03:10`. In questa visita erano presenti due sequenze: la prima per i due valori consecutivi e la seconda prima del pagamento. L’ultimo hit della visita non è una sequenza, in quanto non esiste una marca temporale di fine.

Tempo medio sul sito per `Product page A` è `00:01:35`.

>[!NOTE]
>
>Questa metrica mostra un valore di `"Invalid"` se l’elemento dimensione contiene solo hit che si sono verificati per ultimi in una visita. Questa metrica richiede un hit successivo per tenere traccia del tempo trascorso.

## Tempo medio trascorso sul sito (secondi)

La metrica &quot;Tempo medio trascorso sul sito (secondi)&quot; mostra gli stessi dati presentati come numero intero anziché in `HH:MM:SS` formato. Questa metrica è particolarmente utile come componente all’interno delle metriche calcolate.

## I totali delle suddivisioni non corrispondono alla riga padre

La metrica &quot;Tempo medio sul sito&quot; utilizza sequenze non interrotte di una determinata dimensione. La dimensione di raggruppamento non dipende dalla dimensione principale durante il calcolo di queste sequenze. Ad esempio, considera la seguente visita:

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

Calcolo del tempo medio sul sito per l’elemento dimensione `Home` utilizzerebbe il seguente calcolo:

```text
(30 + 10) / 2 = 20 seconds average time on site
```

Se hai applicato un raggruppamento utilizzando [Sezioni del sito](../dimensions/site-section.md) dimensione, utilizzerebbe il seguente calcolo:

```text
(30 + 100 + 10) / 1 = 140 seconds (2 minutes 20 seconds) average time on site
```

Poiché nella dimensione di raggruppamento era presente una singola sequenza, essa utilizza un denominatore diverso rispetto alla dimensione principale. Queste metriche forniscono in genere risultati simili a livello di visita, ma possono essere diverse a livello di hit.

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo medio dell’intera dimensione sul sito e il numeratore è il tempo medio dell’elemento dimensione sul sito. Se il tempo medio dell’intera dimensione sul sito è inferiore al tempo medio sul sito di un dato elemento dimensione, vengono visualizzate percentuali superiori al 100%. L’ordinamento dei rapporti classificati in base a questa metrica mostra un’anomalia nel tempo medio sui valori del sito, che in genere non è importante. L’Adobe consiglia di ordinare per un’altra metrica, ad esempio [Visite](visits.md), nei rapporti classificati.

Consulta [Panoramica sul tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
