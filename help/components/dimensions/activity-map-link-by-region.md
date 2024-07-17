---
title: Collegamento Activity Map per area geografica
description: Valore concatenato di collegamento e area geografica.
feature: Dimensions
role: User, Admin
source-git-commit: 65e75a1c2b39823e72abfb0e5b61122c62f1f013
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 4%

---

# Collegamento Activity Map per area geografica

La dimensione [dimensione](overview.md) di &#39;Collegamento Activity Map per regione&#39; visualizza una concatenazione di [Collegamento Activity Map](activity-map-link.md) e [Regione Activity Map](activity-map-link-by-region.md). Questa dimensione è utile quando disponi di collegamenti denominati in modo simile, ma che risiedono in aree diverse del sito. Ad esempio, se disponi di più collegamenti alla pagina principale tutti etichettati come &quot;Home page&quot;, puoi utilizzare questa dimensione per distinguere tali collegamenti in ogni area del sito.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalle [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link` e `c.a.activitymap.region`. Questi due valori sono concatenati e separati da una barra verticale (`|`). Se l&#39;implementazione utilizza [Activity Map](/help/analyze/activity-map/overview.md), queste variabili di dati di contesto raccolgono automaticamente i dati quando si fa clic sui collegamenti.

## Elementi dimensionali

Gli elementi del Dimension includono i valori di [Activity Map Link](activity-map-link.md) e [Activity Map Region](activity-map-link-by-region.md). La struttura e l’implementazione del sito della tua organizzazione determinano i valori esatti raccolti.
