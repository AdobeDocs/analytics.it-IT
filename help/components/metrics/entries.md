---
title: Voci
description: Un’istanza del primo valore in una visita.
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 1%

---

# Voci

*Questa pagina di aiuto descrive come le voci funzionano come una metrica. Per informazioni sul funzionamento delle voci come dimensione, consulta [Dimensioni di ingresso](../dimensions/entry-dimensions.md).*

La metrica &quot;Entrate&quot; mostra il numero di volte in cui un dato elemento dimensione viene acquisito come primo valore in una visita. Questa metrica è utile per comprendere di più sulle prime impression che i visitatori hanno sul sito. Visualizzare i primi valori di una dimensione può aiutarti a comprendere e ottimizzare l’esperienza ottenuta da un nuovo visitatore.

## Calcolo di questa metrica

Per una determinata dimensione, registra il primo elemento dimensione visualizzato in una visita come voce. Esiste una sola voce per dimensione per visita. Non è necessariamente il primo hit della visita se la dimensione non è inizialmente impostata. È una metrica basata su visite; una volta collegato a un elemento dimensionale, persiste per il resto della visita.

>[!TIP]
>
>Se visualizzi questa metrica rispetto a una dimensione non sempre impostata in ogni visita, puoi nascondere l’elemento dimensione &quot;Non specificato&quot; in Analysis Workspace. Fai clic sull’icona del filtro, quindi deseleziona [!UICONTROL Include unspecified (None)].
