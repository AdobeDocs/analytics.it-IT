---
description: Le voci rappresentano il numero di volte in cui un dato valore viene acquisito come il primo valore di una visita. Le voci possono verificarsi solo una volta per visita. Tuttavia, non è necessariamente il primo hit se la variabile non è definita.
title: Voci
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Voci

&quot;Voci&quot; rappresenta il numero di volte in cui un dato valore viene acquisito come primo valore di una visita. Le voci possono verificarsi solo una volta per visita. Tuttavia, non è necessariamente il primo hit se la variabile non è definita.

A partire da marzo 2020, in Analysis Workspace è stato modificato il modo in cui il valore “None” interagisce con le entrate e le uscite.  Poiché ora in Analysis Workspace è possibile attivare e disattivare &quot;Nones&quot;, dopo l’entrata o l’uscita viene applicato &quot;None&quot;, mentre (per le variabili evar) veniva applicato in precedenza.  Ad esempio, se il primo hit di una visita non ha alcun valore per, ad esempio, eVar21, ma il secondo hit sì. In Reports &amp; Analytics verrà visualizzato come “Non specificato” per l’entrata, ma in Analysis Workspace verrà visualizzato come valore per il secondo risultato.

Le pagine di entrata hanno un ambito di suddivisione della visita, il che significa che persistono in tutti gli hit per una visita. Per ulteriori informazioni, consulta Contenitori [di](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-overview.html) suddivisione e segmentazione.
