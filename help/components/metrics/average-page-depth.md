---
title: Profondità media della pagine
description: In quante pagine esiste in media la dimensione.
feature: Metrics
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
source-git-commit: 7966c7d9add0011831c97fbe0dfcca2acd8afb58
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 1%

---

# Profondità media della pagine

La metrica &quot;Profondità media della pagina&quot; mostra fino a che punto si trova l’elemento dimensione in una determinata visita. Ad esempio, la pagina principale presenta in genere una profondità di pagina media inferiore rispetto alla pagina di conferma dell’acquisto, che in genere si trova più in là in una visita. Questa metrica è utile quando vuoi comprendere quante pagine in un dato elemento dimensione siedono in media. Puoi utilizzare queste informazioni per ottimizzare determinate pagine per i nuovi visitatori, se la pagina presenta in media una profondità bassa.

>[!TIP]
>
>Utilizza questa metrica insieme a un’altra metrica (ad esempio [Visite](visits.md)) per ottenere informazioni migliori. Se utilizzi questa metrica da sola, otterrai elementi dimensionali contenenti profondità di pagina anomale, che in genere non sono preziose.

## Modalità di calcolo di questa metrica

La prima pagina di una visita ha una profondità di pagina pari a `0`. La pagina successiva ha una profondità di pagina pari a 1 e aumenta ogni visualizzazione di pagina fino alla fine della visita. Questa metrica aumenta solo con la visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e non il tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

Per un dato elemento dimensione, aggiungi tutte le profondità di pagina per tale elemento dimensione e dividilo per visite. Il numero risultante è la profondità di pagina media, arrotondata al numero intero più vicino. Elementi Dimension con profondità di pagina media di `0` significa che era spesso sulla prima pagina della visita.

Ad esempio, considera la visita di esempio seguente:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Se volessimo la profondità di pagina media per l’elemento dimensione `Page2`, viene calcolato come segue:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>Se desideri visualizzare la profondità media della pagina con una posizione decimale, crea una metrica calcolata utilizzando questa metrica come unico elemento all’interno della formula. Aumenta le posizioni decimali nella metrica calcolata fino al decimale desiderato.

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è la profondità di pagina media dell’intera dimensione e il numeratore è la profondità di pagina media dell’elemento dimensione. Se la profondità di pagina media dell’intera dimensione è inferiore alla profondità di pagina media di un dato elemento dimensione, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti classificati per questa metrica mostra le anomalie nei valori medi di profondità di pagina, che in genere non sono importanti. L’Adobe consiglia di ordinare per un’altra metrica, ad esempio [Visite](visits.md), nei rapporti classificati.
