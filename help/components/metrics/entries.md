---
title: Voci
description: Un'istanza del primo valore in una visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 1%

---


# Voci

*Questa pagina della guida descrive il funzionamento delle voci come metriche. Per informazioni sul funzionamento delle voci come una dimensione, vedere Dimensioni[](../dimensions/entry-dimensions.md)entrata.*

La metrica &quot;Voci&quot; mostra il numero di volte in cui un dato elemento dimensione viene acquisito come primo valore in una visita. Questa metrica è utile per comprendere meglio le prime impressioni che i visitatori hanno sul sito. Visualizzare i primi valori di una dimensione può aiutarti a comprendere e ottimizzare l’esperienza acquisita da un nuovo visitatore.

## Modalità di calcolo di questa metrica

Per una determinata dimensione, registra il primo elemento dimensione visto in una visita come voce. Esiste una sola voce per dimensione per visita. Non è necessariamente il primo hit della visita se la dimensione non è impostata inizialmente. È una metrica basata sulle visite; una volta che è collegato a un elemento dimensione, esso persiste per il resto della visita.

>[!TIP]
>
>Se visualizzi questa metrica rispetto a una dimensione non sempre impostata in ogni visita, puoi nascondere l’elemento dimensione &quot;Non specificato&quot; in  Analysis Workspace. Fate clic sull&#39;icona del filtro, quindi deselezionate [!UICONTROL Include unspecified (None)].
