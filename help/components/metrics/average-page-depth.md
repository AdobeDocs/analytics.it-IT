---
title: Profondità media della pagine
description: In quante pagine esiste in media la dimensione.
feature: Metrics
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
TQID: https://experienceleague.adobe.com/Pm2WxRPqn9M-7IdrFQ2Tkj9t-L8ug3nZGr6ncpZg7lg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 365
ht-degree: 3%

---

# Profondità media della pagine

La &quot;Profondità media di pagina&quot; [metrica](overview.md) mostra in media l&#39;estensione di un elemento dimensione in una determinata visita. Ad esempio, la pagina Home (un elemento dimensione per la dimensione Pagina) in genere mostra una profondità di pagina media inferiore rispetto alla pagina di conferma dell’acquisto, che probabilmente si estende ulteriormente in una visita. Puoi utilizzare queste informazioni per ottimizzare determinate pagine per i nuovi visitatori, se la pagina ha in media una profondità bassa.

>[!TIP]
>
>Utilizza questa metrica insieme a un&#39;altra metrica, ad esempio [Visite](visits.md), per ottenere informazioni migliori. Se utilizzi questa metrica da sola, potresti ottenere elementi dimensionali contenenti profondità di pagina anomale, che in genere non è un valore insight.

## Come è calcolata questa metrica

La prima pagina di una visita ha una profondità di pagina di `0`. La pagina successiva ha una profondità di pagina pari a 1 e aumenta ogni visualizzazione di pagina fino alla fine della visita. Questa metrica aumenta solo con le chiamate di visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e non con le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

Per un dato elemento dimensione, aggiungi tutte le profondità di pagina per tale elemento dimensione e dividilo per visite. Il numero risultante è la profondità di pagina media, arrotondata al numero intero più vicino. Gli elementi Dimension con una profondità media di pagina di `0` indicano che si trovavano spesso nella prima pagina della visita.

Ad esempio, considera la visita di esempio seguente:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Se si desiderasse la profondità media delle pagine per l&#39;elemento dimensione `Page2`, verrebbe calcolata nel modo seguente:

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

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è la profondità di pagina media dell’intera dimensione e il numeratore è la profondità di pagina media dell’elemento dimensione.

Se la profondità di pagina media dell’intera dimensione è inferiore alla profondità di pagina media di un dato elemento dimensione, puoi vedere percentuali superiori al 100%. L’ordinamento dei rapporti classificati per questa metrica mostra le anomalie nei valori medi di profondità di pagina, che in genere non sono importanti. Adobe consiglia di ordinare i rapporti in base a un&#39;altra metrica, ad esempio [Visite](visits.md).
