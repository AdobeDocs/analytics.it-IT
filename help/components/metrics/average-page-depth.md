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

La metrica &quot;Profondità media della pagina&quot; mostra a che punto in una data visita si trova l’elemento dimensione. Ad esempio, la pagina principale mostra in genere una profondità media della pagina inferiore rispetto alla pagina di conferma dell’acquisto, che in genere si trova più avanti in una visita. Questa metrica è utile quando desideri comprendere quante pagine in un dato elemento dimensione si trovano in media. Puoi utilizzare queste informazioni per ottimizzare determinate pagine verso nuovi visitatori se la pagina ha una profondità media bassa.

>[!TIP]
>
>Utilizza questa metrica accanto a un’altra metrica (ad esempio [Visite](visits.md)) per ottenere informazioni migliori. Se utilizzi questa metrica da solo, ottieni elementi dimensionali contenenti anomalie nella profondità della pagina, che in genere non è preziosa.

## Calcolo di questa metrica

La prima pagina di una visita ha una profondità di pagina pari a `0`. La pagina successiva ha una profondità di pagina pari a 1 e aumenta ogni visualizzazione di pagina fino alla fine della visita. Questa metrica aumenta solo con la visualizzazione di pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e non il tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

Per un dato elemento dimensione, aggiungi tutte le profondità di pagina per tale elemento dimensione e dividetelo per visite. Il numero risultante è la profondità media della pagina, arrotondata al numero intero più vicino. elementi di Dimension con una profondità media di pagina `0` indica che si trovava frequentemente nella prima pagina della visita.

Ad esempio, considera l’esempio di visita seguente:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Se si desidera una profondità di pagina media per l’elemento dimensione `Page2`, è calcolato come segue:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>Se desideri visualizzare la profondità media della pagina con un decimale, crea una metrica calcolata utilizzando questa metrica come unico elemento all’interno della formula. Aumenta le posizioni decimali della metrica calcolata al decimale desiderato.

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è la profondità media della pagina dell’intera dimensione e il numeratore è la profondità media della pagina dell’elemento dimensionale. Se la profondità media della pagina dell’intera dimensione è inferiore alla profondità media della pagina di un dato elemento dimensionale, le percentuali sono superiori al 100%. L’ordinamento dei rapporti con classifica in base a questa metrica mostra valori di profondità della pagina medi anomali, che in genere non sono preziosi. L’Adobe consiglia l’ordinamento in base a un’altra metrica, ad esempio [Visite](visits.md), in rapporti con classifica.
