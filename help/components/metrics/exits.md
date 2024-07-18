---
title: Uscite
description: Un’istanza dell’ultimo valore in una visita.
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# Uscite

*Questa pagina della guida descrive il funzionamento delle uscite come una metrica. Per informazioni sul funzionamento delle uscite come dimensione, vedere [Dimensioni di uscita](../dimensions/exit-dimensions.md).*

La [metrica](overview.md) &quot;Uscite&quot; mostra il numero di volte in cui un dato elemento dimensione viene acquisito come ultimo valore in una visita. Questa metrica è utile quando vuoi saperne di più sull’ultima cosa che i visitatori vedono prima di lasciare il sito. Vedere gli ultimi valori di una dimensione può aiutarti a comprendere e ottimizzare l’esperienza che un visitatore ottiene prima di partire.

## Come è calcolata questa metrica

Al termine di una [visita](visits.md), registra l&#39;elemento dimensione più recente come uscita. Esiste una sola uscita per dimensione per visita. Non è necessariamente l’ultimo hit della visita se la dimensione è stata impostata negli hit precedenti. È una metrica basata sulle visite; si applica retroattivamente a tutti gli hit nella visita.

>[!TIP]
>
>Se visualizzi questa metrica rispetto a una dimensione non sempre impostata in ogni visita, puoi nascondere l’elemento dimensione &quot;Non specificato&quot; in Analysis Workspace. Fare clic sull&#39;icona del filtro, quindi deselezionare [!UICONTROL Include unspecified (None)].
