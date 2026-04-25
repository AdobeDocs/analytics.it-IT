---
title: Collisioni hash
description: Descrive cosa è una collisione hash e come può manifestarsi.
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: e6dd38fe34d7e0ab69bdf1c68716427905caa356
workflow-type: tm+mt
source-wordcount: '535'
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

Le collisioni hash non possono essere eliminate completamente, ma il loro impatto sui rapporti può essere mitigato. La maggior parte delle collisioni hash si verifica con due valori non comuni, che non hanno alcun impatto significativo sui rapporti. Even if a hash collides with a common and uncommon value, the result is negligible. However, in rare cases where two popular values experience a hash collision, it is possible to see its effect clearly. Adobe recommends the following to reduce its effect in reports:

* **Change the date range**: Hash tables change each month. Changing the date range to span another month can give each value different hashes that don&#39;t collide. It is usually the fastest way to clear a visible anomaly from a specific report.
* **Reduce the number of unique values**: You can adjust your implementation or use [Processing rules](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) to help reduce the number of unique values that a dimension collects. For example, if your dimension collects a URL, you can strip query strings or protocol.
* **Use [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) or [Data Feeds](/help/export/analytics-data-feed/data-feed-overview.md)**: These tools do not rely on hash tables.
* **Move to [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=it)**: Customer Journey Analytics has no hashing layer and [no cardinality limits on dimensions](https://experienceleague.adobe.com/docs/analytics-platform/using/components/dimensions/high-cardinality.html). Consider moving to this product if hash collisions or [[!UICONTROL Low-Traffic]](/help/technotes/low-traffic.md) frequently affect your reports.

>[!MORELIKETHIS]
>
>* [[!UICONTROL Low-Traffic] value in Adobe Analytics](/help/technotes/low-traffic.md)
>* [Processing rules overview](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
