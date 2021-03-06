---
title: Accesso singolo
description: Il numero di volte in cui un elemento dimensione non è cambiato in una visita.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 1%

---

# Accesso singolo

La metrica &quot;Accesso singolo&quot; mostra il numero di visite in cui l’elemento dimensione conteneva un solo valore univoco per l’intera visita. Questa metrica è utile nel contesto di qualsiasi dimensione in cui desideri vedere quali elementi dimensionali rimangono durante una visita.

## Calcolo di questa metrica

Questa metrica conta le visite in cui l’elemento dimensione conteneva un singolo valore univoco. È possibile impostare l’elemento dimensionale più volte oppure mantenerlo persistente e conteggiato comunque come un singolo accesso. Non appena un elemento dimensione diventa un secondo valore univoco, la visita non sarà più qualificata come accesso singolo.

## Differenza tra &quot;Accesso singolo&quot; e &quot;Visita a pagina singola&quot;

Nel contesto [Pagina](../dimensions/page.md) le dimensioni , l’accesso singolo e le visite a pagina singola sono esattamente identiche. Le loro differenze emergono quando si utilizzano altre dimensioni.

* **Accesso singolo**: Mostra il numero di visite in cui l’elemento della dimensione specificato non è stato modificato per l’intera visita. È contestuale alla dimensione utilizzata nel progetto.
* **Visita singola pagina**: Mostra il numero di visite in cui la dimensione &quot;Pagina&quot; non è cambiata per l’intera visita. Anche se utilizzi un’altra dimensione nel rapporto, conta comunque le visite che contengono un singolo elemento dimensione &quot;Pagina&quot; univoco.

Ad esempio, considera l’esempio seguente due visite di hit. La dimensione nel rapporto è [Sezione del sito](../dimensions/site-section.md).

* Un visitatore raggiunge due pagine, ma si trova nella stessa sezione del sito. Poiché la sezione del sito è rimasta invariata durante la visita, viene conteggiato come accesso singolo. Non viene conteggiato come visita a pagina singola perché la visita contiene più di un elemento dimensione pagina univoco.
* Un visitatore accede a due pagine in diverse sezioni del sito, ma entrambe le pagine hanno lo stesso nome. La visita non viene conteggiata come accesso singolo perché erano presenti due valori di sezione univoci del sito. Conteggia come visita a pagina singola perché c’era un singolo elemento dimensione pagina univoco.
