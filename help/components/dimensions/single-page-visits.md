---
title: Visite a pagina singola
description: Flag che indica che la visita è costituita da una singola pagina.
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 4%

---

# Visite a pagina singola

*Questa pagina di aiuto descrive il funzionamento di &quot;visite a pagina singola&quot; come una dimensione. Consulta la sezione [Visite a pagina singola](../metrics/single-page-visits.md) per ulteriori informazioni.*

La dimensione &quot;Visite a pagina singola&quot; indica il numero di visite che consistevano in un singolo evento univoco [Pagina](page.md) elemento dimensione. È la forma dimensionale del [Visite a pagina singola](../metrics/single-page-visits.md) metrica.

Questa dimensione viene comunemente utilizzata come componente all’interno di [segmentazione](../segmentation/seg-home.md). In genere non viene utilizzato come dimensione nei rapporti.

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

L’unico elemento della dimensione è `"Enabled"`. Se una visita consiste in una singola pagina, l’hit viene impostato su questo valore. Tutti gli altri hit vengono omessi da questo rapporto.
