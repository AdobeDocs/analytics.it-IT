---
title: Accesso singolo
description: Il numero di volte in cui un elemento dimensione non è cambiato in una visita.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 2%

---

# Accesso singolo

La [metrica](overview.md) di &quot;Accesso singolo&quot; mostra il numero di visite in cui l&#39;elemento dimensione conteneva un solo valore univoco per l&#39;intera visita. Questa metrica è utile nel contesto di qualsiasi dimensione in cui desideri vedere quali elementi dimensionali ristagnano durante una visita.

## Come è calcolata questa metrica

Questa metrica conta le visite in cui l’elemento dimensionale conteneva un singolo valore univoco. Puoi impostare l’elemento dimensionale più volte oppure impostarlo in modo che persista e venga comunque conteggiato come un singolo accesso. Non appena un elemento dimensionale diventa un secondo valore univoco, la visita non si qualifica più come un singolo accesso.

## Differenza tra &quot;Accesso singolo&quot; e &quot;Visita a pagina singola&quot;

Nel contesto della dimensione [Pagina](../dimensions/page.md), &quot;Accesso singolo&quot; e &quot;Visite a pagina singola&quot; sono identici. Le loro differenze emergono quando utilizzate altre quote.

* **Accesso singolo**: mostra il numero di visite in cui l&#39;elemento dimensione specificato non è stato modificato per l&#39;intera visita. È contestuale alla dimensione utilizzata nel progetto.
* **Visita a pagina singola**: mostra il numero di visite in cui la dimensione &quot;Pagina&quot; non è cambiata per l&#39;intera visita. Anche se utilizzi un’altra dimensione nel rapporto, vengono comunque conteggiate le visite che contengono un singolo elemento dimensione &quot;Pagina&quot; univoco.

Ad esempio, considera l’esempio seguente due visite hit. La dimensione nel report è [Sezione del sito](../dimensions/site-section.md).

* Un visitatore visita due pagine, ma si trovano entrambe nella stessa sezione del sito. Poiché la sezione del sito è rimasta la stessa durante la visita, conta come un accesso singolo. Non viene conteggiata come visita a pagina singola perché la visita contiene più di un elemento dimensione Pagina univoco.
* Un visitatore visita due pagine in diverse sezioni del sito, ma entrambe le pagine hanno lo stesso nome. La visita non viene conteggiata come accesso singolo perché sono presenti due valori univoci della sezione del sito. Conta come visita di una singola pagina perché era presente un singolo elemento dimensione Pagina univoco.
