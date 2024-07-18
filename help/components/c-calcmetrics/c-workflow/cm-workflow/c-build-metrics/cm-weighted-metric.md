---
description: Mostra esempi di metriche filtrate e ponderate.
title: Metriche filtrate e ponderate
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 5%

---

# Metriche filtrate e ponderate

Mostra esempi di metriche filtrate e ponderate.

## Percentuale non recapitate filtrate {#section_D42F2452E4464948934063EB6F2DAAB4}

Questa semplice metrica filtrata mostra il tasso di mancato recapito solo per le pagine con più di 100 visite:

![](assets/cm_fbr.png)

Tieni presente che questa formula dipende da un intervallo di tempo coerente. Se esegui un rapporto per un singolo giorno, vale la pena esaminare qualsiasi pagina con più di 20 visite. Se lo esegui per un mese, potrebbe essere utile che il filtro includa più visite.

## Percentile percentuale di mancato recapito filtrata {#section_4F3E6D33A1FD438A932FA662B3510552}

Questo filtro mostra la Percentuale non recapitate per il primo 30% delle pagine, quando ordinato per visite.

![](assets/cm_wbr_2.png)

## Metrica ponderata {#section_F2D16B14569948289CF1310F9E6E3FC2}

Supponiamo di voler ordinare in generale per frequenza di rimbalzo, ma le pagine con visite più alte dovrebbero essere più in alto nell’elenco. Puoi creare una percentuale di mancato recapito ponderata simile alla seguente:

![](assets/cm_wbr.png)
