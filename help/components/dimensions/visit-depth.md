---
title: Profondità della visita
description: Dimensione basata sulle visite che indica la profondità della visita.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 2%

---

# Profondità della visita

La dimensione &quot;Profondità visita&quot; indica il numero di visualizzazioni di pagina visualizzate dal visitatore nell’intera visita. La profondità della visita aumenta solo se l’hit è una visualizzazione di pagina e la [Pagina](page.md) La dimensione non è la stessa dell’ultimo elemento della visualizzazione della pagina. Si tratta di una dimensione basata sulle visite, il che significa che contiene lo stesso valore per l’intera visita. Questa variabile viene impostata per tutti gli hit in una visita dopo la conclusione della visita.

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Gli elementi di Dimension includono la stringa `"Pages per visit"` seguito da un numero che rappresenta il numero di pagine della visita. Elemento dimensionale di `"Pages per visit: 1"` rappresenta una visita a pagina singola, mentre l’elemento dimensione `"Pages per visit: 8"` rappresenta una visita con 8 visualizzazioni di pagina (e un numero qualsiasi di chiamate per il tracciamento dei collegamenti).

## Confronto con la profondità di hit

Vedi [Profondità di hit](hit-depth.md) per un confronto tra dimensioni.
