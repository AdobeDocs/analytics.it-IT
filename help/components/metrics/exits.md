---
title: Uscite
description: Un’istanza dell’ultimo valore in una visita.
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---

# Uscite

*Questa pagina di aiuto descrive come le uscite funzionano come metriche. Per informazioni sul funzionamento delle uscite come dimensione, consulta [Dimensioni di uscita](../dimensions/exit-dimensions.md).*

La metrica &quot;Uscite&quot; mostra il numero di volte in cui un dato elemento dimensione viene acquisito come ultimo valore in una visita. Questa metrica è utile quando desideri comprendere di più sull’ultima cosa che i visitatori visualizzano prima di lasciare il sito. Visualizzare gli ultimi valori di una dimensione può essere utile per comprendere e ottimizzare l’esperienza che un visitatore ottiene prima di partire.

## Calcolo di questa metrica

Dopo un [visita](visits.md) conclude, registra l’elemento della dimensione più recente come uscita. Esiste una sola uscita per dimensione per visita. Non è necessariamente l’ultimo hit della visita se la dimensione è stata impostata negli hit precedenti. È una metrica basata su visite; si applica retroattivamente a tutti gli hit della visita.

>[!TIP]
>
>Se visualizzi questa metrica rispetto a una dimensione non sempre impostata in ogni visita, puoi nascondere l’elemento dimensione &quot;Non specificato&quot; in Analysis Workspace. Fai clic sull’icona del filtro, quindi deseleziona [!UICONTROL Include unspecified (None)].
