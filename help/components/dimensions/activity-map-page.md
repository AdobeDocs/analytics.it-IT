---
title: Pagina di Activity Map
description: Il nome della pagina quando è stato fatto clic su un collegamento.
feature: Dimensions
role: User, Admin
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# Pagina di Activity Map

La &#39;pagina Activity Map&#39; [dimensione](overview.md) visualizza la pagina sulla quale si trovava un visitatore quando ha fatto clic su un collegamento. Puoi utilizzare questa dimensione per determinare quali pagine contengono i collegamenti più cliccati. Questa dimensione viene utilizzata anche dalla sovrapposizione Activity Map per determinare quali collegamenti visualizzare.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla [variabile di dati di contesto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. Se l&#39;implementazione utilizza [Activity Map](/help/analyze/activity-map/overview.md), questa variabile di dati di contesto raccoglie automaticamente i dati quando si fa clic sui collegamenti.

Per un determinato collegamento su cui è stato fatto clic, questa variabile di dati di contesto raccoglie il valore nella dimensione [Pagina](page.md). Se la dimensione Pagina non contiene un valore, viene utilizzata la dimensione [URL pagina](page-url.md) (in modo simile al fallback utilizzato dalla dimensione Pagina). I dati Activity Map vengono in genere inviati all’hit successivo dopo aver fatto clic su un collegamento. Questa dimensione ti consente di determinare il valore della pagina al momento del clic sul collegamento, invece del valore della pagina al momento dell’invio dei dati.

## Elementi dimensionali

Gli elementi di Dimension includono tutti i valori trovati nella dimensione [Pagina](page.md).
