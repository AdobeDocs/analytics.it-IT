---
title: Giorni dall’ultimo acquisto
description: Il numero di giorni tra l'hit corrente e l'ultimo acquisto effettuato.
feature: Dimensions
exl-id: 6f0d9d79-cf40-4de3-9d9f-9b1bc57f97b6
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# Giorni dall’ultimo acquisto

La dimensione &quot;Giorni dall’ultimo acquisto&quot; misura il tempo trascorso tra l’hit corrente del visitatore e il suo acquisto più recente in quel momento. Questa dimensione ti aiuta a comprendere il comportamento dei visitatori dopo aver acquistato qualcosa sul tuo sito.

I visitatori che non hanno mai acquistato qualcosa non sono inclusi in questa dimensione. Inoltre, non sono inclusi gli hit generati prima del primo acquisto di un visitatore. Sono inclusi solo gli hit dopo il primo acquisto del visitatore.

## Popolare questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base al [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) nella tua implementazione. Se implementi la `purchase` sul sito, questa dimensione funziona sempre.

## Elementi Dimension

Gli elementi di Dimension includono il numero di giorni tra l&#39;acquisto più recente di un visitatore e l&#39;hit corrente. Ogni numero di giorni è un elemento dimensione separato, con il verificarsi dello &quot;stesso giorno&quot; in cui l’acquisto più recente di un visitatore e l’hit corrente si sono verificati nello stesso giorno.
