---
title: Profondità della visita
description: Dimensione basata sulla visita che riporta la profondità della visita.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 17%

---

# Profondità della visita

La [dimensione](overview.md) &quot;Profondità della visita&quot; indica il numero di visualizzazioni di pagina viste dal visitatore nell&#39;intera visita. La profondità della visita aumenta solo se l&#39;hit è una visualizzazione di pagina e la dimensione [Pagina](page.md) non è la stessa dell&#39;elemento dimensione dell&#39;ultima visualizzazione di pagina. Si tratta di una dimensione basata sulle visite, il che significa che contiene lo stesso valore per l’intera visita. Questa variabile è impostata per tutti gli hit in una visita dopo la conclusione di tale visita.

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi di Dimension includono la stringa `"Pages per visit"` seguita da un numero che rappresenta il numero di pagine della visita. L&#39;elemento dimensione di `"Pages per visit: 1"` rappresenta una visita a pagina singola, mentre l&#39;elemento dimensione `"Pages per visit: 8"` rappresenta una visita con 8 visualizzazioni di pagina (e un numero qualsiasi di chiamate di tracciamento dei collegamenti).

## Confronto con la profondità di hit

Vedi [Profondità di hit](hit-depth.md) per un confronto tra dimensioni.
