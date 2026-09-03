---
title: Giorni dall’ultimo acquisto
description: Il numero di giorni tra l’hit corrente e l’ultimo acquisto effettuato.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
TQID: https://experienceleague.adobe.com/q86bc1bMRctUBe7dFEJaALsq0GjALFQQtKU9cRpRkoU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 8%

---

# Giorni dall’ultimo acquisto

La dimensione &#39;Giorni dall&#39;ultimo acquisto&#39; [1&rbrace; misura il tempo trascorso tra l&#39;hit corrente del visitatore e il suo acquisto più recente in quel momento. &#x200B;](overview.md)Questa dimensione ti aiuta a comprendere il comportamento dei visitatori dopo l’acquisto di qualcosa sul sito.

I visitatori che non hanno mai acquistato qualcosa non sono inclusi in questa dimensione. Inoltre, non sono inclusi neanche gli hit generati prima del primo acquisto di un visitatore. Sono inclusi solo gli hit successivi al primo acquisto del visitatore.

## Popolare questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base all&#39;evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) nell&#39;implementazione. Se implementi l&#39;evento `purchase` sul sito, questa dimensione funziona sempre.

## Elementi dimensionali

Gli elementi Dimension includono il numero di giorni tra l’acquisto più recente di un visitatore e l’hit corrente. Ogni numero di giorni è un elemento dimensione separato, con &quot;Stesso giorno&quot; che si verifica quando l’acquisto più recente di un visitatore e l’hit corrente si verificano nello stesso giorno.
