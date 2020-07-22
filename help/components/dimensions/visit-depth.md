---
title: Informazioni sulla visita
description: Dimensione basata sulle visite che indica la profondità della visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Informazioni sulla visita

La dimensione &#39;Profondità visita&#39; indica il numero di visualizzazioni di pagina visualizzate dal visitatore nell&#39;intera visita. La profondità della visita aumenta solo se l’hit è una visualizzazione di pagina e la dimensione della [pagina](page.md) non corrisponde all’elemento dimensione dell’ultima pagina. Si tratta di una dimensione basata sulle visite, il che significa che contiene lo stesso valore per l’intera visita. Questa variabile viene impostata per tutti gli hit in una visita al termine della visita.

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensione

Gli elementi dimensione includono la stringa `"Pages per visit"` seguita da un numero che rappresenta il numero di pagine della visita. L’elemento dimensione di `"Pages per visit: 1"` rappresenta una visita a pagina singola, mentre l’elemento dimensione `"Pages per visit: 8"` rappresenta una visita con 8 visualizzazioni di pagina (e un numero qualsiasi di chiamate di tracciamento dei collegamenti).

## Confronto con la profondità di hit

Consulta Profondità [](hit-depth.md) hit per un confronto tra dimensioni.