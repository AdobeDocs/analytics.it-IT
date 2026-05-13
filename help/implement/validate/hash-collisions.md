---
title: Collisioni hash
description: Descrive cosa è una collisione hash e come può manifestarsi.
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
TQID: https://experienceleague.adobe.com/yjYX-h-8jJA7k-jzRMOJ0l2BxN5-no2kCfySkGYss8w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 535
ht-degree: 3%

---

# Collisioni hash

Le dimensioni in Adobe Analytics raccolgono valori stringa. A volte queste stringhe sono lunghe centinaia di caratteri, mentre altre volte sono brevi. Per migliorare le prestazioni, questi valori stringa non vengono utilizzati direttamente nell’elaborazione al momento del reporting. Viene invece calcolato un hash per ogni valore, producendo un identificatore di dimensione uniforme. Per la maggior parte dei campi, il valore viene convertito in minuscolo prima dell’hashing, riducendo il numero totale di valori univoci. Tutti i rapporti vengono eseguiti su questi valori con hash, che ne aumentano notevolmente le prestazioni.

Adobe Analytics mantiene una tabella hash separata per ogni variabile e ogni tabella viene ricreata ogni mese. All&#39;interno di una di queste tabelle, due diversi valori di origine possono occasionalmente produrre lo stesso hash, noto come *conflitto hash*.

Le collisioni hash possono manifestarsi nei rapporti come segue:

* Se visualizzi un rapporto nel tempo e osservi un picco imprevisto, è possibile che più valori univoci per tale variabile utilizzino lo stesso hash.
* Se utilizzi un segmento e vedi un valore imprevisto, è possibile che l’elemento dimensione imprevisto utilizzi lo stesso hash di un altro elemento dimensione che corrisponde al segmento.

## Possibilità di una collisione hash

Adobe Analytics utilizza hash a 32 bit per la maggior parte delle dimensioni, il che significa che ci sono 2<sup>32</sup> possibili combinazioni di hash (circa 4,3 miliardi). Le probabilità approssimative di incontrare una collisione hash in base al numero di valori univoci sono le seguenti. Queste probabilità si basano su una singola dimensione per un singolo mese.

| Valori univoci | Odds |
| --- | --- |
| 1.000 | 0.01% |
| 10.000 | 1% |
| 50.000 | 26% |
| 100.000 | 71% |

Simile al paradosso del [compleanno](https://en.wikipedia.org/wiki/Birthday_problem), la probabilità di conflitti di hash aumenta drasticamente con l&#39;aumentare del numero di valori univoci. Con 1 milione di valori univoci, è probabile che ci siano almeno 100 conflitti di hash per quella dimensione.

## Mitigazione delle collisioni hash

Le collisioni hash non possono essere eliminate completamente, ma il loro impatto sui rapporti può essere mitigato. La maggior parte delle collisioni hash si verifica con due valori non comuni, che non hanno alcun impatto significativo sui rapporti. Anche se un hash si scontra con un valore comune e non comune, il risultato è trascurabile. Tuttavia, in rari casi in cui due valori popolari sperimentano una collisione hash, è possibile vedere chiaramente il suo effetto. Per ridurre l’effetto nei rapporti, Adobe consiglia di effettuare le seguenti operazioni:

* **Modifica l&#39;intervallo di date**: le tabelle hash cambiano ogni mese. Se si modifica l’intervallo di date in modo che si estenda su un altro mese, a ogni valore possono essere assegnati hash diversi che non si scontrano. In genere è il modo più rapido per eliminare un’anomalia visibile da un rapporto specifico.
* **Riduci il numero di valori univoci**: puoi regolare l&#39;implementazione o utilizzare [Regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) per ridurre il numero di valori univoci raccolti da una dimensione. Ad esempio, se la dimensione raccoglie un URL, puoi rimuovere stringhe di query o protocollo.
* **Usa [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) o [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md)**: questi strumenti non si basano su tabelle hash.
* **Passa a [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=it)**: Customer Journey Analytics non ha livelli di hashing e [nessun limite di cardinalità per le dimensioni](https://experienceleague.adobe.com/docs/analytics-platform/using/components/dimensions/high-cardinality.html). Prendere in considerazione il passaggio a questo prodotto se i rapporti sono spesso influenzati da conflitti di hash o da [[!UICONTROL Low-Traffic]](/help/technotes/low-traffic.md).

>[!MORELIKETHIS]
>
>* Valore [[!UICONTROL Low-Traffic] in Adobe Analytics](/help/technotes/low-traffic.md)
>* [Panoramica delle regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
