---
title: Giorni precedenti al primo acquisto
description: Il numero di giorni tra la prima visita di un visitatore e il suo primo acquisto.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
TQID: https://experienceleague.adobe.com/fA8CgahXKwJfiynK-I8yuD-byaIyFPkaii3FzkrrPoI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
source-wordcount: '207'
ht-degree: 12%
---
# Giorni precedenti al primo acquisto

La [dimensione](overview.md) &quot;Giorni prima del primo acquisto&quot; indica il numero di giorni che passano tra il primo accesso del visitatore al sito e il momento dell&#39;acquisto. Ad esempio, se un visitatore effettua un acquisto un giorno dopo la prima visita, tutte le visite o gli eventi successivi appartengono all’elemento dimensione &quot;1 giorno&quot;.

Dopo che un visitatore ha effettuato il suo primo acquisto, appartiene allo stesso elemento dimensione per il resto della durata del cookie del visitatore.

## Popolare questa dimensione con i dati

Adobe calcola questa dimensione lato server dalla cronologia acquisti del visitatore. Nessuna variabile da impostare. Dipende dall&#39;implementazione dell&#39;evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) sul sito.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (calcolato da Adobe) |
| **Campo Web SDK / XDM** | Nessuno (calcolato da Adobe) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Visitatore |

## Elementi dimensionali

Gli elementi di Dimension includono il numero di giorni tra la prima visita di un visitatore al sito e il suo primo acquisto. Ogni numero di giorni è un elemento dimensione separato, con &quot;Stesso giorno&quot; che si verifica quando la prima visita di un visitatore e il primo acquisto avvengono nello stesso giorno.
