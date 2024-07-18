---
title: Visite a pagina singola (dimensioni)
description: Un flag che indica che la visita era costituita da una singola pagina.
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 20%

---

# Visite a pagina singola

*Questa pagina della Guida descrive il funzionamento di &#39;Visite a pagina singola&#39; come [dimensione](overview.md). Per ulteriori informazioni, consulta la metrica [Visite a pagina singola](../metrics/single-page-visits.md).*

La dimensione &quot;Visite a pagina singola&quot; riporta il numero di visite costituito da un singolo elemento dimensione univoco [Pagina](page.md). È la dimensione della metrica [Visite a pagina singola](../metrics/single-page-visits.md).

Questa dimensione viene comunemente utilizzata come componente all&#39;interno di [segmentazione](../segmentation/seg-home.md). In genere non viene utilizzata come dimensione nei rapporti.

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

L&#39;unico elemento dimensione è `"Enabled"`. Se una visita è costituita da una singola pagina, l’hit viene impostato su questo valore. Tutti gli altri hit vengono omessi da questo rapporto.
