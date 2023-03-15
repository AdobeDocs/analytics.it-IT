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

*Questa pagina della guida descrive come funzionano le voci come una metrica. Per informazioni sul funzionamento delle voci come dimensione, vedere [Dimensioni di entrata](../dimensions/entry-dimensions.md).*

La metrica &quot;Entrate&quot; mostra il numero di volte in cui un dato elemento dimensione viene acquisito come primo valore in una visita. Questa metrica è utile quando vuoi saperne di più sulle prime impressioni che i visitatori hanno sul tuo sito. La visualizzazione dei primi valori di una dimensione può aiutarti a comprendere e ottimizzare l’esperienza che riceve un nuovo visitatore.

## Modalità di calcolo di questa metrica

Per una determinata dimensione, registra il primo elemento dimensione visualizzato in una visita come voce. Esiste una sola voce per dimensione per visita. Non è necessariamente il primo hit della visita se la dimensione non è inizialmente impostata. Si tratta di una metrica basata sulle visite; una volta collegata a un elemento dimensione, persiste per il resto della visita.

>[!TIP]
>
>Se visualizzi questa metrica rispetto a una dimensione non sempre impostata in ogni visita, puoi nascondere l’elemento dimensione &quot;Non specificato&quot; in Analysis Workspace. Fai clic sull’icona del filtro, quindi deseleziona [!UICONTROL Include unspecified (None)].
