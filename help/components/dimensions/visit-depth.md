---
title: Profondità della visita
description: Dimensione basata sulla visita che riporta la profondità della visita.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
TQID: https://experienceleague.adobe.com/mT5dQzR6edNpvU6Fbf9LlLwQuxW6RA-ZCZJDaIFkyAw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 10%
---
# Profondità della visita

La [dimensione](overview.md) &quot;Profondità della visita&quot; indica il numero di visualizzazioni di pagina viste dal visitatore nell&#39;intera visita. La profondità della visita aumenta solo se l&#39;hit è una visualizzazione di pagina e la dimensione [Pagina](page.md) non è la stessa dell&#39;elemento dimensione dell&#39;ultima visualizzazione di pagina. Si tratta di una dimensione basata sulle visite, il che significa che contiene lo stesso valore per l’intera visita. Questa variabile è impostata per tutti gli hit in una visita dopo la conclusione di tale visita.

## Popolare questa dimensione con i dati

Adobe calcola questa dimensione lato server dalle visualizzazioni di pagina in ogni visita. Non esiste una variabile da impostare; funziona automaticamente per tutte le implementazioni.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (calcolato da Adobe) |
| **Campo Web SDK / XDM** | Nessuno (calcolato da Adobe) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Visita |

## Elementi dimensionali

Gli elementi di Dimension includono la stringa `"Pages per visit"` seguita da un numero che rappresenta il numero di pagine della visita. L&#39;elemento dimensione di `"Pages per visit: 1"` rappresenta una visita a pagina singola, mentre l&#39;elemento dimensione `"Pages per visit: 8"` rappresenta una visita con 8 visualizzazioni di pagina (e un numero qualsiasi di chiamate di tracciamento dei collegamenti).

## Confronto con la profondità di hit

Vedi [Profondità di hit](hit-depth.md) per un confronto tra dimensioni.
