---
title: Visualizzazione media delle pagine per visita
description: Numero medio di volte in cui un dato elemento dimensione viene visualizzato in una visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---


# Visualizzazione media delle pagine per visita

La dimensione &quot;Numero medio di visualizzazioni di pagina per visita&quot; mostra il numero medio di visualizzazioni di pagina rispetto alla dimensione desiderata. Per le dimensioni basate sul tempo, puoi vedere il numero medio di visualizzazioni di pagina all’interno delle tendenze di una visita nel tempo. Questa metrica è utile per comprendere la frequenza con cui gli elementi dimensionali vengono visualizzati in una visita.

>[SUGGERIMENTO] Utilizzate questa metrica insieme a un’altra metrica (come [Visite](visits.md)) per ottenere informazioni più dettagliate. Se si utilizza questa metrica da sola, si ottengono elementi dimensionali contenenti visualizzazioni di pagina con anomalie per visita, il che in genere non è prezioso.

## Modalità di calcolo di questa metrica

Questa metrica viene calcolata utilizzando la formula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è la visualizzazione della pagina media dell’intera dimensione per visita, e il numeratore è la visualizzazione della pagina media per visita dell’elemento della dimensione. Se le visualizzazioni di pagina medie per visita dell’intera dimensione sono inferiori alle visualizzazioni di pagina medie per visita di un determinato elemento dimensione, vedrete percentuali superiori al 100%. L&#39;ordinamento di report con classifica in base a questa metrica mostra le visualizzazioni di pagina medie anomalie per i valori delle visite, che in genere non è prezioso. Adobe consiglia di ordinare i dati in base a un’altra metrica, ad esempio [Visite](visits.md), nei rapporti con classifica.