---
title: Giorni precedenti al primo acquisto
description: Il numero di giorni tra la prima visita di un visitatore e il suo primo acquisto.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 5%

---

# Giorni precedenti al primo acquisto

I &quot;Giorni precedenti al primo acquisto&quot; [dimensione](overview.md) segnala il numero di giorni che trascorrono tra la prima volta che un visitatore raggiunge il sito e il momento in cui effettua un acquisto. Ad esempio, se un visitatore effettua un acquisto un giorno dopo la prima visita, tutte le visite o gli eventi successivi appartengono all’elemento dimensione &quot;1 giorno&quot;.

Dopo che un visitatore ha effettuato il suo primo acquisto, appartiene allo stesso elemento dimensione per il resto della durata del cookie del visitatore.

## Popola questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base al [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) nell’implementazione. Se si implementa `purchase` sul sito, questa dimensione funziona sempre.

## Elementi dimensionali

Gli elementi Dimension includono il numero di giorni tra la prima visita di un visitatore al sito e il suo primo acquisto. Ogni numero di giorni è un elemento dimensione separato, con &quot;Stesso giorno&quot; che si verifica quando la prima visita di un visitatore e il primo acquisto avvengono nello stesso giorno.
