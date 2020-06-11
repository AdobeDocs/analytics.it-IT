---
title: Giorni prima del primo acquisto
description: Il numero di giorni tra la prima visita di un visitatore e il suo primo acquisto.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Giorni prima del primo acquisto

La dimensione &quot;Giorni prima del primo acquisto&quot; indica il numero di giorni trascorsi tra la prima volta che un visitatore raggiunge il sito e la data in cui effettua un acquisto. Ad esempio, se un visitatore effettua un acquisto un giorno dopo la prima visita, qualsiasi visita o evento successivo appartiene al valore di dimensione &quot;1 giorno&quot;.

Dopo che un visitatore ha effettuato il primo acquisto, apparterrà allo stesso valore di dimensione per il resto della durata dei cookie del visitatore.

## Compilare questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base all’ [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) evento nell’implementazione. Se implementate l’ `purchase` evento sul sito, questa dimensione funziona sempre.

## Valori dimensione

I valori delle dimensioni includono il numero di giorni tra la prima visita di un visitatore sul sito e il suo primo acquisto. Ogni numero di giorni è un valore di dimensione separato, con &quot;Lo stesso giorno&quot; che si verifica quando la prima visita di un visitatore e il suo primo acquisto avvengono nello stesso giorno.
