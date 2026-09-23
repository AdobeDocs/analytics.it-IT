---
title: Tempo precedente all’evento
description: La quantità di tempo tra la metrica e il primo hit della visita.
feature: Dimensions
exl-id: 2586673f-d908-4b69-901a-5fafe635d0d5
TQID: https://experienceleague.adobe.com/vO3S-yZwV7KSLmIzRfwNDrVaB3NzpsIocmHsAaamfj0
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
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 13%
---
# Tempo precedente all’evento

La &#39;dimensione Tempo precedente all&#39;evento&#39; [dimension](overview.md) indica il tempo trascorso tra il primo hit della visita e la metrica desiderata. Questa dimensione è utile per determinare il tempo necessario per raggiungere un evento di successo, ad esempio l’invio di un modulo o un acquisto.

## Popolare questa dimensione con i dati

Adobe calcola questa dimensione lato server dal tempo trascorso tra il primo hit della visita e l’evento di destinazione. Nessuna variabile da impostare. Anche se tecnicamente funziona come previsto, funziona meglio quando eventi personalizzati e di acquisto vengono implementati sul sito.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (calcolato da Adobe) |
| **Campo Web SDK / XDM** | Nessuno (calcolato da Adobe) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi Dimension includono bucket basati sul tempo che vanno da `"Less than 1 minute"` a `"More than 15 hours"`. Ad esempio, se un visitatore ha impiegato 23 minuti dal suo primo hit per effettuare un acquisto, questo apparterrà all&#39;elemento dimensione `"10 to 30 minutes"`. Non è possibile personalizzare i bucket per questa metrica.
