---
title: Giorni dall’ultimo acquisto
description: Il numero di giorni tra l’hit corrente e l’ultimo acquisto effettuato.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
# Giorni dall’ultimo acquisto

La dimensione &#39;Giorni dall&#39;ultimo acquisto&#39; [1&rbrace; misura il tempo trascorso tra l&#39;hit corrente del visitatore e il suo acquisto più recente in quel momento. &#x200B;](overview.md)Questa dimensione ti aiuta a comprendere il comportamento dei visitatori dopo l’acquisto di qualcosa sul sito.

I visitatori che non hanno mai acquistato qualcosa non sono inclusi in questa dimensione. Inoltre, non sono inclusi neanche gli hit generati prima del primo acquisto di un visitatore. Sono inclusi solo gli hit successivi al primo acquisto del visitatore.

## Popolare questa dimensione con i dati

Adobe calcola questa dimensione lato server dalla cronologia acquisti del visitatore. Nessuna variabile da impostare. Dipende dall&#39;implementazione dell&#39;evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) sul sito.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (calcolato da Adobe) |
| **Campo Web SDK / XDM** | Nessuno (calcolato da Adobe) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi Dimension includono il numero di giorni tra l’acquisto più recente di un visitatore e l’hit corrente. Ogni numero di giorni è un elemento dimensione separato, con &quot;Stesso giorno&quot; che si verifica quando l’acquisto più recente di un visitatore e l’hit corrente si verificano nello stesso giorno.
