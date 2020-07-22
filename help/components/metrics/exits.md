---
title: Uscite
description: Un'istanza dell'ultimo valore di una visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---


# Uscite

*In questa pagina della guida viene descritto come le uscite funzionano come una metrica. Per informazioni sul funzionamento delle uscite come una dimensione, vedi[Dimensioni](../dimensions/exit-dimensions.md)di uscita.*

La metrica &#39;Exits&#39; mostra il numero di volte in cui un dato elemento dimensione viene acquisito come ultimo valore in una visita. Questa metrica è utile per comprendere meglio l’ultima cosa che i visitatori vedono prima di lasciare il sito. La visualizzazione degli ultimi valori di una dimensione può aiutarti a comprendere e ottimizzare l’esperienza acquisita da un visitatore prima che esca.

## Modalità di calcolo di questa metrica

Al termine di una [visita](visits.md) , registra l’elemento della dimensione più recente come uscita. Esiste una sola uscita per dimensione per visita. Non è necessariamente l’ultimo hit della visita se la dimensione è stata impostata negli hit precedenti. È una metrica basata sulle visite; si applica retroattivamente a tutti gli hit della visita.

>[!TIP]
>
>Se visualizzi questa metrica rispetto a una dimensione non sempre impostata in ogni visita, puoi nascondere l’elemento dimensione &quot;Non specificato&quot; in  Analysis Workspace. Fate clic sull&#39;icona del filtro, quindi deselezionate [!UICONTROL Include unspecified (None)].
