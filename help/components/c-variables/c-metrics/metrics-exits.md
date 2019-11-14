---
description: Il numero di volte in cui un dato valore viene acquisito come ultimo valore di una visita. Le uscite possono verificarsi solo una volta per visita.
solution: Analytics
title: Uscite
topic: Metrics
uuid: cd5436ef-65d3-431b-a24f-aceff8542c50
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Uscite

Il numero di volte in cui un dato valore viene acquisito come ultimo valore di una visita. Le uscite possono verificarsi solo una volta per visita.

Le pagine di uscita dispongono di un ambito di suddivisione per le visite, ossia persistono in tutti gli hit per una visita. Per ulteriori informazioni, consulta Contenitori [di](https://marketing.adobe.com/resources/help/en_US/sc/user/c_Breakdown_and_segmentation_containers.html) suddivisione e segmentazione.

Se applicate a una dimensione, le uscite vengono conteggiate sull’ultimo valore di una visita, che può verificarsi su qualsiasi hit durante la visita. Se non è presente alcun valore nell’ultimo hit, l’opzione Esci viene attribuita al valore più recente.

Se un'uscita si verifica al di fuori dell'intervallo di reporting per una visita all'interno dell'intervallo di reporting, verrà inclusa purché non si trovi lungo un limite del mese (all'interno del set di dati).
