---
title: Profondità media della pagine
description: Quante pagine in media la dimensione esiste.
translation-type: tm+mt
source-git-commit: 226bbce18750825d459056ac2a87549614eb3c2c
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 1%

---


# Profondità media della pagine

La metrica &#39;Profondità media pagina&#39; mostra la distanza in una data visita dell&#39;elemento dimensione. Ad esempio, la pagina principale mostrerebbe in genere una profondità di pagina media inferiore rispetto alla pagina di conferma dell&#39;acquisto, che in genere si troverebbe più distante in una visita. Questa metrica è utile per capire quante pagine di un dato elemento dimensione si trovano in media. È possibile utilizzare queste informazioni per ottimizzare determinate pagine verso nuovi visitatori se la pagina ha una profondità media bassa.

>[!TIP]
>
>Utilizza questa metrica insieme a un’altra metrica (ad esempio [Visite](visits.md)) per ottenere informazioni più dettagliate. Se si utilizza questa metrica da sola, si ottengono elementi dimensionali contenenti profondità anomale della pagina, che in genere non è preziosa.

## Modalità di calcolo di questa metrica

La prima pagina di una visita ha una profondità di pagina pari a `0`. La pagina successiva ha una profondità di pagina pari a 1 e aumenta ogni visualizzazione di pagina fino alla fine della visita. Questa metrica aumenta solo con le chiamate di visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e non con quelle di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

Per un dato elemento dimensione, aggiungete tutte le profondità di pagina per tale elemento dimensione e dividetelo per visite. Il numero risultante è la profondità media della pagina, arrotondata al numero intero più vicino. Gli elementi di Dimension con una profondità di pagina media di `0` indica che frequentemente si trovavano nella prima pagina della visita.

Ad esempio, prendete in considerazione la seguente visita di esempio:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Se si desidera una profondità di pagina media per l’elemento della dimensione `Page2`, viene calcolata come segue:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>Se si desidera visualizzare la profondità media della pagina con una posizione decimale, creare una metrica calcolata utilizzando questa metrica come unico elemento all&#39;interno della formula. Aumentare le posizioni decimali della metrica calcolata al decimale desiderato.

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è la profondità di pagina media dell&#39;intera dimensione e il numeratore è la profondità di pagina media dell&#39;elemento della dimensione. Se la profondità di pagina media dell&#39;intera dimensione è inferiore alla profondità di pagina media di un dato elemento dimensione, vengono visualizzate percentuali superiori al 100%. L&#39;ordinamento di report con classifica in base a questa metrica mostra i valori di profondità della pagina medi delle anomalie, che in genere non sono preziosi.  Adobe consiglia l&#39;ordinamento in base a un&#39;altra metrica, come [Visite](visits.md), nei report con classifica.