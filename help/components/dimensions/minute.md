---
title: Minuto
description: Il minuto in cui è avvenuta la metrica.
feature: Dimensions
exl-id: 63f13083-321f-4fd8-9352-e413e1ebf168
TQID: https://experienceleague.adobe.com/GRivRprXBteGxRZieSI3uyjHALDJ-0hHbZx3S9ldJW0
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
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 23%
---
# Minuto

La [dimensione](overview.md) &#39;Minuto&#39; indica il minuto in cui si è verificata una determinata metrica (arrotondata per difetto). Il primo elemento dimensione è il primo minuto nell’intervallo di date e l’ultimo elemento dimensione è l’ultimo minuto nell’intervallo di date. Questa dimensione è utile per i rapporti con tendenze, in quanto consente di visualizzare le metriche nel tempo. Data la granularità di questa dimensione, Adobe consiglia di limitare l’intervallo di date del rapporto a uno o due giorni.

## Popolare questa dimensione con i dati

Questa dimensione è derivata dalla marca temporale di ciascun hit. Non esiste una variabile da impostare; funziona come previsto in qualsiasi implementazione.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dal timestamp dell’hit) |
| **Campo Web SDK / XDM** | Nessuno (derivato dal timestamp dell’hit) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli elementi di Dimension includono un determinato minuto nell’intervallo di date di un rapporto insieme alla relativa data. È formattato come `HH:MM YYYY-MM-DD`. Gli elementi di Dimension che iniziano con `00:00` equivalgono a mezzanotte di quel giorno, mentre i valori che iniziano con `23:59` equivalgono alle 23:59 di quel giorno.
