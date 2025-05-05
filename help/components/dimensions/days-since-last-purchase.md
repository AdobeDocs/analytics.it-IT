---
title: Giorni dall’ultimo acquisto
description: Il numero di giorni tra l’hit corrente e l’ultimo acquisto effettuato.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Giorni dall’ultimo acquisto

La dimensione &#39;Giorni dall&#39;ultimo acquisto&#39; [1&rbrace; misura il tempo trascorso tra l&#39;hit corrente del visitatore e il suo acquisto più recente in quel momento. ](overview.md) Questa dimensione ti aiuta a comprendere il comportamento dei visitatori dopo l’acquisto di qualcosa sul sito.

I visitatori che non hanno mai acquistato qualcosa non sono inclusi in questa dimensione. Inoltre, non sono inclusi neanche gli hit generati prima del primo acquisto di un visitatore. Sono inclusi solo gli hit successivi al primo acquisto del visitatore.

## Popolare questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base all&#39;evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) nell&#39;implementazione. Se implementi l&#39;evento `purchase` sul sito, questa dimensione funziona sempre.

## Elementi dimensionali

Gli elementi Dimension includono il numero di giorni tra l’acquisto più recente di un visitatore e l’hit corrente. Ogni numero di giorni è un elemento dimensione separato, con &quot;Stesso giorno&quot; che si verifica quando l’acquisto più recente di un visitatore e l’hit corrente si verificano nello stesso giorno.
