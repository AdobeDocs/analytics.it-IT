---
title: Giorni precedenti al primo acquisto
description: Il numero di giorni tra la prima visita di un visitatore e il suo primo acquisto.
feature: Dimensions
exl-id: 651f9d55-49b9-402a-b7c7-ba4fba62c695
TQID: https://experienceleague.adobe.com/fA8CgahXKwJfiynK-I8yuD-byaIyFPkaii3FzkrrPoI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
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
source-wordcount: 174
ht-degree: 8%

---

# Giorni precedenti al primo acquisto

La [dimensione](overview.md) &quot;Giorni prima del primo acquisto&quot; indica il numero di giorni che passano tra il primo accesso del visitatore al sito e il momento dell&#39;acquisto. Ad esempio, se un visitatore effettua un acquisto un giorno dopo la prima visita, tutte le visite o gli eventi successivi appartengono all’elemento dimensione &quot;1 giorno&quot;.

Dopo che un visitatore ha effettuato il suo primo acquisto, appartiene allo stesso elemento dimensione per il resto della durata del cookie del visitatore.

## Popolare questa dimensione con i dati

Adobe compila automaticamente questa dimensione in base all&#39;evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) nell&#39;implementazione. Se implementi l&#39;evento `purchase` sul sito, questa dimensione funziona sempre.

## Elementi dimensionali

Gli elementi di Dimension includono il numero di giorni tra la prima visita di un visitatore al sito e il suo primo acquisto. Ogni numero di giorni è un elemento dimensione separato, con &quot;Stesso giorno&quot; che si verifica quando la prima visita di un visitatore e il primo acquisto avvengono nello stesso giorno.
