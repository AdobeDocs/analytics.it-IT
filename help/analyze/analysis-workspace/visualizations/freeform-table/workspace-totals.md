---
description: Modalità di calcolo dei totali in Workspace.
title: Totali in Workspace
feature: Freeform Tables
role: User, Admin
exl-id: 883c3e44-4139-46a1-a261-e11841312465
source-git-commit: 1ce002a513860ce15dc8a70825d26795fd93eb1d
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 26%

---

# Totali in Workspace

Nelle tabelle a forma libera viene visualizzata una riga del totale a ogni livello di suddivisione, la quale può mostrare due totali:

![Tabella a forma libera che evidenzia il totale complessivo e il totale della tabella.](assets/total-row.png)

* **[!UICONTROL Table total]** - Questo totale è in genere uguale o un sottoinsieme di [!UICONTROL Grand total]. Il totale riflette eventuali filtri applicati alla tabella a forma libera, inclusa l&#39;opzione [!UICONTROL Include None].
* **[!UICONTROL Grand total]** (**[!UICONTROL out of]** *numero*) - Questo totale rappresenta tutti gli eventi raccolti. Quando un filtro viene applicato a livello di pannello o all’interno della tabella a forma libera, questo totale si regola per riflettere tutti gli eventi che corrispondono ai criteri del filtro.




## Visualizza totali

In ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Column settings]** sono disponibili opzioni per **[!UICONTROL Show totals]** e **[!UICONTROL Show grand total]**. Se queste impostazioni non sono selezionate, i totali vengono rimossi dalla tabella, il che può essere utile nei casi in cui i totali non abbiano senso.


[I totali della riga statica](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) si comportano in modo diverso e sono controllati tramite ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Row Settings]**.

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Show sum of current rows as the total]** | Mostra una somma lato client delle righe nella tabella. Questo totale **non** deduplica metriche quali sessioni o persone. |
| **[!UICONTROL Show grand total]** | Mostra una somma lato server. Questo totale deduplica metriche quali sessioni o persone. |

Vedi [Elementi dimensionali dinamici e statici nelle tabelle a forma libera](column-row-settings/manual-vs-dynamic-rows.md).


## Domande frequenti

| Domande | Risposta |
|---|---|
| Su quali *totali* si basano le percentuali delle colonne grigie? | Questo *totale* dipende dalla selezione dell&#39;impostazione **[!UICONTROL Percentages]** in **[!UICONTROL Row Settings]**:<ul><li>Calcola le percentuali per colonna: questa impostazione è quella predefinita. Le percentuali sono basate sul totale della tabella.</li><li>Calcola le percentuali per riga: le percentuali sono basate sul totale complessivo.</li></ul> |
| In che modo l’impostazione **[!UICONTROL Include Unspecified (None)]** (Includi non specificati (Nessuno)) influisce sui totali? | Se l&#39;impostazione Includi non specificato (Nessuno) non è selezionata, la riga None/Unspecified verrà rimossa dalla tabella, ovvero dal totale della tabella, e passerà a tutte le metriche calcolate che utilizzano i tipi di metrica [&#39;Total&#39;](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md). |
| Quando si applicano filtri di tabella personalizzati a una tabella a forma libera, tutte le metriche calcolate e la formattazione condizionale vengono applicate al filtro? | Attualmente no. **[!UICONTROL Include Ubnspeficied (None)]** è un account per, ma i filtri di tabella personalizzati non influiscono sui seguenti elementi:<ul><li>L’intervallo massimo/minimo delle colonne utilizzato per la formattazione condizionale viene visualizzato in tutti i dati.</li><li>Metriche calcolate che sfruttano i tipi di metrica **[!UICONTROL Grand total]** (Totale complessivo).</li><li>Metriche calcolate con funzioni che calcolano tra le righe di una tabella a forma libera: Somma colonna, Massimo colonna, Minimo colonna, Conteggio, Media, Mediana, Percentile, Quartile, Conteggio righe, Deviazione standard, Varianza, Cumulativo, Media cumulativa, Varianti di regressione, Punteggio T, Test T, Punteggio Z e Test Z.</li></ul> |
| In Metriche calcolate, cosa riflette il tipo di metrica **[!UICONTROL Grand total]** (Totale complessivo)? | **[!UICONTROL Grand total]** (Totale complessivo) continua a fare riferimento al **[!UICONTROL Grand total]** (Totale complessivo) e non riflette i filtri applicati a una tabella o al **[!UICONTROL Table total]** (Totale tabella). |
| Qual è il totale visualizzato quando i dati vengono copiati e incollati da una tabella a forma libera o scaricati tramite CSV? | La riga del totale riflette solo **[!UICONTROL Table total]** e rispetta l&#39;impostazione della colonna **[!UICONTROL Show totals]**. |
