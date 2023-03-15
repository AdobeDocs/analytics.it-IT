---
title: Visite a pagina singola (dimensioni)
description: Un flag che indica che la visita era costituita da una singola pagina.
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 3%

---

# Visite a pagina singola

*Questa pagina della guida descrive come funziona &quot;Visite a pagina singola&quot; come dimensione. Consulta la [Visite a pagina singola](../metrics/single-page-visits.md) per ulteriori informazioni.*

La dimensione &quot;Visite a pagina singola&quot; riporta il numero di visite costituito da un singolo messaggio univoco [Pagina](page.md) elemento dimensione. È la forma dimensionale del [Visite a pagina singola](../metrics/single-page-visits.md) metrica.

Questa dimensione viene comunemente utilizzata come componente in [segmentazione](../segmentation/seg-home.md). In genere non viene utilizzata come dimensione nei rapporti.

## Popola questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

L’unico elemento dimensionale è `"Enabled"`. Se una visita è costituita da una singola pagina, l’hit viene impostato su questo valore. Tutti gli altri hit vengono omessi da questo rapporto.
