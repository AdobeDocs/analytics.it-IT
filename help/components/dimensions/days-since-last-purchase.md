---
title: Giorni dall'ultimo acquisto
description: Il numero di giorni tra l'hit corrente e l'ultimo acquisto che hanno effettuato.
translation-type: tm+mt
source-git-commit: c9e696201d0e9ec97dcdd6ff797ca72244dcf366
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Giorni dall&#39;ultimo acquisto

La dimensione &quot;Giorni dall&#39;ultimo acquisto&quot; misura il tempo trascorso tra l&#39;hit corrente del visitatore e il suo acquisto più recente in quel momento. Questa dimensione ti aiuta a capire il comportamento che i visitatori fanno dopo aver acquistato qualcosa sul tuo sito.

I visitatori che non hanno mai acquistato qualcosa non sono inclusi in questa dimensione. Inoltre, gli hit licenziati prima del primo acquisto di un visitatore non sono inclusi. Sono inclusi solo gli hit dopo il primo acquisto del visitatore.

## Compilare questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base all’ [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) evento nell’implementazione. Se implementate l’ `purchase` evento sul sito, questa dimensione funziona sempre.

## Valori dimensione

I valori delle dimensioni includono il numero di giorni tra l&#39;acquisto più recente di un visitatore e l&#39;hit corrente. Ogni numero di giorni è un valore di dimensione separato, con &quot;Stesso giorno&quot; che si verifica quando l&#39;acquisto più recente di un visitatore e l&#39;hit corrente si sono verificati nello stesso giorno.
