---
title: Accesso singolo
description: Il numero di volte in cui un valore di dimensione non è stato modificato in una visita.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Accesso singolo

La metrica &quot;Accesso singolo&quot; mostra il numero di visite in cui il valore della dimensione conteneva solo un singolo valore univoco per l’intera visita. Questa metrica è utile nel contesto di qualsiasi dimensione in cui si desidera vedere quali valori di dimensione stagnano durante una visita.

## Modalità di calcolo di questa metrica

Questa metrica conta le visite in cui il valore della dimensione conteneva un singolo valore univoco. È possibile impostare il valore della dimensione più volte o lasciarlo persistere e continuare a contenerlo come un singolo accesso. Non appena un valore di dimensione diventa un secondo valore univoco, la visita non si qualifica più come un singolo accesso.

## Differenza tra &quot;Accesso singolo&quot; e &quot;Visita a pagina singola&quot;

Nel contesto della dimensione [Pagina](../dimensions/page.md) , &#39;Accesso singolo&#39; e &#39;Visite a pagina singola&#39; sono esattamente identici. Le loro differenze emergono quando si utilizzano altre dimensioni.

* **Accesso** singolo: Mostra il numero di visite in cui il valore della dimensione specificato non è stato modificato per l’intera visita. È contestuale alla dimensione utilizzata nel progetto.
* **Visita** a pagina singola: Mostra il numero di visite in cui la dimensione &quot;Pagina&quot; non è stata modificata per l’intera visita. Anche se utilizzi un’altra dimensione nel rapporto, questo continua a conteggiare visite che contengono un unico valore di dimensione &quot;Pagina&quot;.

Ad esempio, considerate l&#39;esempio seguente due visite di hit. La dimensione nel rapporto è la sezione [](../dimensions/site-section.md)Sito.

* Un visitatore accede a due pagine, ma entrambe si trovano nella stessa sezione del sito. Poiché la sezione del sito è rimasta la stessa durante la visita, viene contato come accesso singolo. Non viene conteggiata come visita a pagina singola perché la visita contiene più di un valore di dimensione Pagina univoco.
* Un visitatore accede a due pagine in diverse sezioni del sito, ma entrambe le pagine hanno lo stesso nome. La visita non viene conteggiata come accesso singolo perché erano presenti due valori di sezione univoci del sito. Conteggia come visita a pagina singola perché era presente un singolo valore di dimensione Pagina.
