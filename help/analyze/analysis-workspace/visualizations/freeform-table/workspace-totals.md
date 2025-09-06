---
description: Scopri come vengono calcolati i totali nelle tabelle a forma libera in Analysis Workspace.
title: Totali
feature: Freeform Tables
role: User, Admin
exl-id: 883c3e44-4139-46a1-a261-e11841312465
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 81%

---

# Totali {#workspace-totals}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="Totale complessivo"
>abstract="Il totale complessivo non è supportato per tabelle o raggruppamenti con righe statiche."

Nelle tabelle a forma libera viene visualizzata una riga del totale a ogni livello di raggruppamento, la quale può mostrare due totali:

![Tabella a forma libera che evidenzia il totale complessivo e il totale della tabella.](assets/total-row.png)

* **[!UICONTROL Table total]** ➊ - Questo totale è in genere uguale o un sottoinsieme di [!UICONTROL Grand total]. Il totale riflette eventuali filtri applicati alla tabella a forma libera, inclusa l’opzione [!UICONTROL Include None].
* **[!UICONTROL Grand total]** (**[!UICONTROL out of]** *numero*) ➋ - Questo totale rappresenta tutti gli eventi raccolti. Quando un filtro viene applicato a livello di pannello o all’interno della tabella a forma libera, il totale si rettifica in modo da riflettere tutti gli eventi che corrispondono ai criteri di filtro.




## Visualizzare i totali

In ![Impostazioni](/help/assets/icons/Setting.svg) **[!UICONTROL Column settings]** sono disponibili le opzioni **[!UICONTROL Show totals]** and **[!UICONTROL Show grand total]**. Se queste impostazioni non sono selezionate, i totali vengono rimossi dalla tabella, il che può essere utile nei casi in cui i totali non abbiano senso.


In una tabella a forma libera che contiene [righe statiche](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md), i totali si comportano in modo diverso. E sono controllati con ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Row Settings]**.

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Show sum of current rows as the total]** | Mostra una somma lato client delle righe nella tabella. Questo totale **non** deduplica metriche quali sessioni o persone. |
| **[!UICONTROL Show grand total]** | Mostra una somma lato server. Questo totale deduplica metriche quali sessioni o persone. |

Consulta [Elementi dimensionali dinamici e statici nelle tabelle a forma libera](column-row-settings/manual-vs-dynamic-rows.md).


## Domande frequenti

| Domande | Risposta |
|---|---|
| Su quale *totale* si basano le percentuali delle colonne grigie? | Il *totale* dipende dall’impostazione **[!UICONTROL Percentages]** selezionata in **[!UICONTROL Row Settings]**:<ul><li>Calcola le percentuali per colonna: questa impostazione è quella predefinita. Le percentuali saranno basate sul totale della tabella.</li><li>Calcola le percentuali per riga: le percentuali saranno basate sul totale complessivo.</li></ul> |
| In che modo l’impostazione **[!UICONTROL Include Unspecified (None)]** (Includi non specificati (Nessuno)) influisce sui totali? | Se l&#39;impostazione Includi non specificato (Nessuno) non è selezionata, la riga None/Unspecified verrà rimossa dalla tabella, ovvero dal totale della tabella, e passerà a tutte le metriche calcolate che utilizzano i tipi di metrica [&#39;Total&#39;](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md). |
| Quando si applicano filtri di tabella personalizzati a una tabella a forma libera, tutte le metriche calcolate e la formattazione condizionale vengono applicate al filtro? | Attualmente no. **[!UICONTROL Include Ubnspeficied (None)]** è tenuto in conto, ma i filtri di tabella personalizzati non avranno alcun impatto sui seguenti elementi:<ul><li>Intervallo max/min delle colonne utilizzato per la formattazione condizionale considera tutti i dati.</li><li>Metriche calcolate che sfruttano i tipi di metrica **[!UICONTROL Grand total]** (Totale complessivo).</li><li>Metriche calcolate con funzioni che si calcolano considerando le righe di una tabella a forma libera, ad esempio Column Sum (Somma colonna), Column max (Massimo colonna), Column min (Minimo colonna), Count (Conteggio), Mean (Media), Median (Mediana), Percentile (Percentile), Quartile (Quartile), Row Count (Conteggio righe), Standard Deviation (Deviazione standard), Variance (Varianza), Cumulative (Cumulativa), Cumulative Average (Media cumulativa), Regression variants (Varianti di regressione), T-Score, T-Test, Z-Score e Z-Test.</li></ul> |
| In Metriche calcolate, a cosa fa riferimento il tipo di metrica **[!UICONTROL Grand total]**? | **[!UICONTROL Grand total]** (Totale complessivo) continua a fare riferimento al **[!UICONTROL Grand total]** (Totale complessivo) e non riflette i filtri applicati a una tabella o al **[!UICONTROL Table total]** (Totale tabella). |
| Qual totale viene visualizzato quando i dati vengono copiati e incollati da una tabella a forma libera o scaricati tramite CSV? | La riga del totale riflette solo il **[!UICONTROL Table total]** e rispetta l’impostazione della colonna **[!UICONTROL Show totals]**. |
