---
description: Il numero di volte in cui un dato valore viene acquisito come ultimo valore di una visita. Le uscite possono verificarsi solo una volta per visita.
title: Uscite
topic: Metrics
uuid: cd5436ef-65d3-431b-a24f-aceff8542c50
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Uscite

Il numero di volte in cui un dato valore viene acquisito come ultimo valore di una visita. Le uscite possono verificarsi solo una volta per visita.

Le pagine di uscita dispongono di un ambito di suddivisione per le visite, il che significa che persistono in tutti gli hit per una visita. Per ulteriori informazioni, consulta Contenitori [di](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-overview.html) suddivisione e segmentazione.

Se applicate a una dimensione, le uscite vengono conteggiate sull’ultimo valore di una visita, che può verificarsi su qualsiasi hit durante la visita. Se non è presente alcun valore nell’ultimo hit, l’opzione Esci viene attribuita al valore più recente.

Se un&#39;uscita si verifica al di fuori dell&#39;intervallo di reporting per una visita all&#39;interno dell&#39;intervallo di reporting, verrà inclusa purché non si trovi lungo un limite del mese (all&#39;interno del set di dati).
