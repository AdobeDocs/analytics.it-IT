---
title: Giorni precedenti al primo acquisto
description: Il numero di giorni tra la prima visita di un visitatore e il suo primo acquisto.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# Giorni precedenti al primo acquisto

La dimensione &quot;Giorni precedenti al primo acquisto&quot; indica il numero di giorni trascorsi tra la prima volta che un visitatore raggiunge il sito e quando effettua un acquisto. Ad esempio, se un visitatore effettua un acquisto un giorno dopo la prima visita, qualsiasi visita o evento successivo appartiene all’elemento dimensione &quot;1 giorno&quot;.

Dopo che un visitatore effettua il suo primo acquisto, appartiene allo stesso elemento dimensionale per il resto della durata del cookie del visitatore.

## Popolare questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base al [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) nella tua implementazione. Se implementi la `purchase` sul sito, questa dimensione funziona sempre.

## Elementi Dimension

Gli elementi di Dimension includono il numero di giorni tra la prima visita di un visitatore al sito e il suo primo acquisto. Ogni numero di giorni è un elemento dimensione separato, con il verificarsi dello &quot;stesso giorno&quot; in cui la prima visita di un visitatore e il suo primo acquisto sono avvenuti lo stesso giorno.
