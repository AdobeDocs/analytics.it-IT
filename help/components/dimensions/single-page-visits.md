---
title: Visite di una singola pagina
description: Flag che indica che la visita è costituita da una singola pagina.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# Visite di una singola pagina

*Questa pagina della guida descrive il funzionamento delle &quot;visite a pagina singola&quot; come una dimensione. Per ulteriori informazioni, vedi la metrica visite[a pagina](../metrics/single-page-visits.md)singola.*

La dimensione &quot;Visite a pagina singola&quot; indica il numero di visite che consistevano in un singolo elemento dimensione [Pagina](page.md) univoca. È la forma dimensionale della metrica visite [a pagina](../metrics/single-page-visits.md) singola.

Questa dimensione viene utilizzata più comunemente come componente all’interno della [segmentazione](../c-segmentation/seg-home.md). In genere non viene utilizzato come dimensione nei report.

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensione

L&#39;unico elemento dimensione è `"Enabled"`. Se una visita è costituita da una singola pagina, l’hit viene impostato su questo valore. Tutti gli altri hit vengono omessi da questo rapporto.
