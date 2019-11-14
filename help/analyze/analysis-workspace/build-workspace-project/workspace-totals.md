---
description: Modalità di calcolo dei totali di Workspace.
title: Totali area di lavoro
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Totali area di lavoro

Nelle tabelle a forma libera, viene visualizzata una riga totale a ogni livello di suddivisione e può mostrare due totali:

* **[!UICONTROL Grand Total]** (numero 'fuori' grigio) - questo totale rappresenta tutti gli hit che sono stati raccolti, talvolta denominati 'totale suite di rapporti'. Quando un segmento viene applicato a livello di pannello o all’interno della tabella a forma libera, questo totale si regola per riflettere tutti gli hit che corrispondono ai criteri del segmento.
* **[!UICONTROL Table Total]** (numero nero) - questo totale è in genere uguale o un sottoinsieme del [!UICONTROL Grand Total]. Riflette eventuali filtri applicati alla tabella a forma libera, inclusa l’ [!UICONTROL Include None] opzione.

![](assets/total-row.png)

## Impostazione Totale visualizzazione

In **[!UICONTROL Column Settings]**, sono disponibili opzioni per **[!UICONTROL Show Totals]** e **[!UICONTROL Show Grand Total]**. Se queste impostazioni non sono selezionate, i totali verranno rimossi dalla tabella. Ciò può essere desiderato nei casi in cui i totali non hanno senso, ad esempio, in alcuni scenari [Metrica](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html)calcolata.

![](assets/column-settings-total.png)

## Impostazioni Totale righe statiche

[I totali delle righe](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) statiche si comportano in modo diverso e sono controllati in **[!UICONTROL Row Settings]**.

* **[!UICONTROL Show sum of current rows as the total]** - mostra una somma lato client delle righe nella tabella, il che significa che il totale **non** deduplica metriche come visite o visitatori.
* **[!UICONTROL Show Grand Total]** - mostra una somma lato server, il che significa che il totale deduplicherà le metriche come visite o visitatori.

![](assets/static-rows.png)

## Domande frequenti

| Domande | Risposta |
|---|---|
| Su quale 'totale' si basano le percentuali delle colonne grigie? | Questo dipende dalla **[!UICONTROL Percentages]** selezione delle impostazioni in **[!UICONTROL Row Settings]**:<ul><li>Calcola le percentuali per colonna - Questa è l'impostazione predefinita. Le percentuali saranno basate sul totale della tabella.</li><li>Calcola le percentuali per riga - Le percentuali saranno basate sul totale complessivo.</li></ul> |
| In che modo l' **[!UICONTROL Include Unspecified (None)]** impostazione influisce sui totali? | Se l' **[!UICONTROL Include Unspecified (None)]** impostazione non è selezionata, la riga Nessuno/Non specificato verrà rimossa dalla tabella, dal Totale tabella e passerà a tutte le metriche calcolate che utilizzano i tipi di metriche ["Totale"](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| Quando si applicano filtri di tabella personalizzati a una tabella a forma libera, tutte le metriche calcolate e l'account di formattazione condizionale del filtro vengono applicate? | Non al momento. **[!UICONTROL Include Unspecified (None)]** verranno contabilizzati, ma i filtri di tabella personalizzati non avranno alcun impatto sui seguenti elementi:<ul><li>L'intervallo massimo/min delle colonne utilizzato per la formattazione condizionale sarà visualizzato in tutti i dati.</li><li>Metriche calcolate che sfruttano i tipi di **[!UICONTROL Grand Total]** metriche.</li><li>Metriche calcolate con funzioni che si calcolano tra le righe in una tabella a forma libera, ad esempio Somma colonna, Massimo colonna, Minimo colonna, Conteggio, Media, Media, Percentile, Quarile, Conteggio righe, Deviazione standard, Varianza, Cumulativa, Media cumulativa, Varianti di regressione, Valutazione T, Test T, Valutazione Z, Test Z.</li></ul> |
| In Metriche calcolate, cosa riflette il tipo di **[!UICONTROL Grand Total]** metrica? | **[!UICONTROL Grand Total]** continua a fare riferimento alla tabella **[!UICONTROL Grand Total]** e non riflette i filtri applicati a una tabella o alla **[!UICONTROL Table Total]**. |
| Qual è il totale visualizzato quando i dati vengono copiati e incollati da una tabella a forma libera o scaricati tramite CSV? | La riga totale riflette l' **[!UICONTROL Table Total]** unica riga e rispetta l'impostazione della colonna **[!UICONTROL Show Totals]** . |

