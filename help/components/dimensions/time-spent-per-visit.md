---
title: Tempo trascorso per visita (dimensioni)
description: Quantità totale di tempo impiegata per la visita.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
TQID: 'https://experienceleague.adobe.com/jtBAAq-Pe0PyCQJPwvzwnK9eLv14CxTvrVQP4lvWy7k'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
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
source-wordcount: '349'
ht-degree: 6%
---
# Tempo trascorso per visita

>[!BEGINSHADEBOX]

*In questa pagina della guida viene descritto il funzionamento di &#39;Tempo trascorso per visita&#39; come le rispettive [dimensioni](overview.md). Per ulteriori informazioni, vedere la metrica [Tempo trascorso per visita](../metrics/time-spent-per-visit.md).*

>[!ENDSHADEBOX]

Le dimensioni &quot;Tempo trascorso per visita&quot; registrano il tempo trascorso da un visitatore per l’intera visita. Per misurare il calcolo, utilizza i passaggi seguenti:

1. Osserva la marca temporale del primo hit della visita.
2. Confronta questo hit con la marca temporale dell’ultimo hit della visita.
3. Il tempo trascorso tra questi due hit contribuisce al tempo trascorso.

Queste dimensioni sono utili per comprendere per quanto tempo i visitatori interagiscono con il sito in generale.

>[!TIP]
>
>Il tempo trascorso richiede almeno due hit in una visita per misurare il tempo. Le visite costituite da un singolo hit non vengono visualizzate in questa dimensione.

Questa dimensione è basata sulle visite, il che significa che il valore si applica a ogni hit all’interno della visita e non cambia. Confronta questa dimensione con [Tempo trascorso sulla pagina](time-spent-on-page.md), che è una dimensione basata sugli hit.

Questa dimensione è correlata alle metriche [Tempo medio trascorso sul sito](../metrics/average-time-on-site.md) e [Tempo trascorso per visita](../metrics/time-spent-per-visit.md).

## Popolare questa dimensione con i dati

Adobe calcola queste dimensioni lato server dal tempo trascorso tra il primo e l’ultimo hit della visita. Non c’è alcuna variabile da impostare; funzionano automaticamente per tutte le implementazioni.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (calcolato da Adobe) |
| **Campo Web SDK / XDM** | Nessuno (calcolato da Adobe) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Visita |

## Elementi dimensionali

Esistono più dimensioni per il tempo trascorso per visita:

* **Tempo trascorso per visita - a blocchi**: la quantità di tempo è a blocchi. Gli elementi di Dimension sono compresi tra `"Less than 1 minute"` e `"More than 15 hours"`. Le visite in genere non durano più di 12 ore; tuttavia, le visite possono superare le 12 ore se si utilizzano hit con marca temporale o origini dati.
* **Tempo trascorso per visita - granulare**: ogni numero di secondi è un elemento dimensione univoco. Dimensione non disponibile in Data Warehouse.

Consulta [Panoramica sul tempo trascorso](../metrics/time-spent.md) per informazioni più generali sul tempo trascorso.
