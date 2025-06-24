---
title: Collisioni hash
description: Descrive cosa è una collisione hash e come può manifestarsi.
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 1%

---

# Collisioni hash

Le dimensioni in Adobe Analytics raccolgono valori stringa. A volte queste stringhe sono lunghe centinaia di caratteri, mentre altre volte sono brevi. Per migliorare le prestazioni, questi valori stringa non vengono utilizzati direttamente nell’elaborazione. Viene invece calcolato un hash per ogni valore per rendere tutti i valori di una dimensione uniforme. Tutti i rapporti vengono eseguiti su questi valori con hash, che ne aumentano notevolmente le prestazioni.

Per la maggior parte dei campi, la stringa viene prima convertita in tutte le lettere minuscole. La conversione in minuscolo riduce il numero di valori univoci. I valori vengono sottoposti a hashing su base mensile; nel caso di un determinato valore viene utilizzato il primo valore visualizzato ogni mese. Mese per mese, esiste una piccola possibilità che due valori di variabile univoci vengano hash allo stesso valore. Questo concetto è noto come *conflitto hash*.

Le collisioni hash possono manifestarsi nei rapporti come segue:

* Se visualizzi un rapporto nel tempo e osservi un picco imprevisto, è possibile che più valori univoci per tale variabile utilizzino lo stesso hash.
* Se utilizzi un segmento e vedi un valore imprevisto, è possibile che l’elemento dimensione imprevisto utilizzi lo stesso hash di un altro elemento dimensione che corrisponde al segmento.

## Possibilità di una collisione hash

Adobe Analytics utilizza hash a 32 bit per la maggior parte delle dimensioni, il che significa che ci sono 2<sup>32</sup> possibili combinazioni di hash (circa 4,3 miliardi). Ogni mese viene creata una nuova tabella hash per ogni dimensione. Le probabilità approssimative di incontrare una collisione hash in base al numero di valori univoci sono le seguenti. Queste probabilità si basano su una singola dimensione per un singolo mese.

| Valori univoci | Odds |
| --- | --- |
| 1.000 | 0,01% |
| 10.000 | 1% |
| 50.000 | 26% |
| 100.000 | 71% |

{style="table-layout:auto"}

Simile al paradosso del [compleanno](https://en.wikipedia.org/wiki/Birthday_problem), la probabilità di conflitti di hash aumenta drasticamente con l&#39;aumentare del numero di valori univoci. Con 1 milione di valori univoci, è probabile che ci siano almeno 100 conflitti di hash per quella dimensione.

## Mitigazione delle collisioni hash

La maggior parte delle collisioni hash si verifica con due valori non comuni, che non hanno alcun impatto significativo sui rapporti. Anche se un hash si scontra con un valore comune e non comune, il risultato è trascurabile. Tuttavia, in rari casi in cui due valori popolari sperimentano una collisione hash, è possibile vedere chiaramente il suo effetto. Per ridurre l’effetto nei rapporti, Adobe consiglia di effettuare le seguenti operazioni:

* **Modifica l&#39;intervallo di date**: le tabelle hash cambiano ogni mese. Se si modifica l’intervallo di date in modo che si estenda su un altro mese, a ogni valore possono essere assegnati hash diversi che non si scontrano.
* **Riduci il numero di valori univoci**: puoi regolare l&#39;implementazione o utilizzare [Regole di elaborazione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) per ridurre il numero di valori univoci raccolti da una dimensione. Ad esempio, se la dimensione raccoglie un URL, puoi rimuovere stringhe di query o protocollo.

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
