---
title: Voci
description: Un’istanza del primo valore in una visita.
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
TQID: https://experienceleague.adobe.com/H3LE0wm2uDL3-pILbvOXvccAJQdo5o9X3uHJ4xZe7UU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 3%

---

# Voci

*Questa pagina della Guida descrive il funzionamento delle voci come una metrica. Per informazioni sul funzionamento delle voci come dimensione, vedere [Dimensioni di ingresso](../dimensions/entry-dimensions.md).*

La [metrica](overview.md) &quot;Voci&quot; mostra il numero di volte in cui un dato elemento dimensione viene acquisito come primo valore in una visita. Questa metrica è utile quando vuoi saperne di più sulle prime impressioni che i visitatori hanno sul tuo sito. La visualizzazione dei primi valori di una dimensione può aiutarti a comprendere e ottimizzare l’esperienza che riceve un nuovo visitatore.

## Come è calcolata questa metrica

Per una determinata dimensione, registra il primo elemento dimensione visualizzato in una visita come voce. Esiste una sola voce per dimensione per visita. Non è necessariamente il primo hit della visita se la dimensione non è inizialmente impostata. Si tratta di una metrica basata sulle visite; una volta collegata a un elemento dimensione, persiste per il resto della visita.

>[!TIP]
>
>Se visualizzi questa metrica rispetto a una dimensione non sempre impostata in ogni visita, puoi nascondere l’elemento dimensione &quot;Non specificato&quot; in Analysis Workspace. Fare clic sull&#39;icona del filtro, quindi deselezionare [!UICONTROL Include unspecified (None)].
