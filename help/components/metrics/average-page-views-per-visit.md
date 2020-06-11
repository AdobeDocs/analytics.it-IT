---
title: Visualizzazione media delle pagine per visita
description: Numero medio di volte in cui un dato valore di dimensione viene visualizzato in una visita.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---


# Visualizzazione media delle pagine per visita

La dimensione &quot;Numero medio di visualizzazioni di pagina per visita&quot; mostra il numero medio di visualizzazioni di pagina rispetto alla dimensione desiderata. Per le dimensioni basate sul tempo, puoi vedere il numero medio di visualizzazioni di pagina all’interno delle tendenze di una visita nel tempo. Questa metrica è utile per comprendere la frequenza con cui i valori delle dimensioni vengono visualizzati in una visita.

>[SUGGERIMENTO] Utilizzate questa metrica insieme a un’altra metrica (come [Visite](visits.md)) per ottenere informazioni più dettagliate. Se si utilizza questa metrica da sola, si ottengono valori di dimensione contenenti visualizzazioni di pagina con anomalie per visita, che in genere non è preziosa.

## Modalità di calcolo di questa metrica

Questa metrica viene calcolata utilizzando la formula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è la media delle visualizzazioni di pagina per visita dell’intera dimensione e il numeratore è la media delle visualizzazioni di pagina per visita del valore della dimensione. Se le visualizzazioni di pagina medie per visita dell’intera dimensione sono inferiori alle visualizzazioni di pagina medie per visita di un dato valore di dimensione, vedrete percentuali superiori al 100%. L&#39;ordinamento di report con classifica in base a questa metrica mostra le visualizzazioni di pagina medie anomalie per i valori delle visite, che in genere non è prezioso. Adobe consiglia di ordinare i dati in base a un’altra metrica, ad esempio [Visite](visits.md), nei rapporti con classifica.