---
description: Scopri come visualizzare i dati con tendenze per una tabella a forma libera in Analysis Workspace.
title: Visualizzare i dati con tendenze per una tabella a forma libera
feature: Freeform Tables
role: User, Admin
exl-id: b1d109fd-0e3c-45df-94d0-1a6383d7f995
TQID: https://experienceleague.adobe.com/-L-J1kq-YozWG8VnwD8-7637M6QlUYu3-wVeBvVBipA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 400
ht-degree: 0%

---

# Visualizzare i dati con tendenze per una tabella a forma libera

È possibile visualizzare la tendenza dei dati inclusi in una tabella a forma libera. Questi dati con tendenze sono visualizzati nelle seguenti aree in Analysis Workspace:

* [Grafici sparkline](#use-sparklines-to-view-trended-data)

* [Visualizzazioni delle linee](#use-line-visualizations-to-view-trended-data)

## Utilizza i grafici sparkline per visualizzare i dati con tendenze

I grafici sparkline sono visualizzati nell’intestazione della colonna delle metriche delle tabelle a forma libera.

![sparkline nella tabella a forma libera](assets/table-sparkline.png)

I grafici sparkline includono sempre:

* Dati con tendenze per tutti i dati nella colonna

* Qualsiasi criterio di filtro di ricerca applicato alla dimensione tabella

  Per ulteriori informazioni, vedere [Filtro e ordinamento](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

## Utilizzare le visualizzazioni a linee per visualizzare i dati con tendenze

Le visualizzazioni [Line](/help/analyze/analysis-workspace/visualizations/line.md) visualizzano i dati della tabella a forma libera a cui sono connesse.

### Connettere una visualizzazione a linee a una tabella a forma libera

A seconda di come e quando la visualizzazione delle linee è stata aggiunta al progetto, potrebbe già essere connessa alla tabella a forma libera desiderata. Utilizza i seguenti passaggi per verificare o per collegarlo manualmente:

1. Aggiungi una visualizzazione a linee a un progetto Analysis Workspace.

1. Seleziona il punto accanto al nome della visualizzazione, seleziona la scheda **[!UICONTROL Data source]**, quindi seleziona il nome della tabella a forma libera da connettere alla visualizzazione delle linee.

   ![visualizzazione a linee connessa a tabelle a forma libera](assets/table-line-viz.png)

### Scegli i dati inclusi nella visualizzazione delle linee

I dati inclusi nella visualizzazione della linea connessa differiscono, a seconda della cella selezionata nella tabella a forma libera.

Per visualizzare una tendenza di tutti i dati nella tabella a forma libera, seleziona la cella sparkline nella tabella a forma libera.

Quando la cella sparkline è selezionata, viene visualizzata in grigio scuro.

![sparkline selezionato](assets/table-sparkline-selected.png)

Quando la cella sparkline della tabella connessa è selezionata, le visualizzazioni delle linee includono:

* Dati con tendenze per tutti i dati nella colonna

* Qualsiasi criterio di filtro di ricerca applicato alla dimensione tabella

  Per ulteriori informazioni, vedere [Filtro e ordinamento](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

Quando il grafico sparkline della tabella connessa non è selezionato, le visualizzazioni delle linee includono:

* Dati per la riga selezionata nella tabella connessa. Se non è selezionata alcuna riga, vengono visualizzati i dati solo per la prima dimensione della tabella connessa.

* Qualsiasi criterio di filtro di ricerca applicato alla dimensione tabella viene ignorato

  Per ulteriori informazioni, vedere [Filtro e ordinamento](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


## Includere i criteri di filtro nelle visualizzazioni delle linee connesse

Per informazioni su quando i criteri di filtro sono inclusi nelle visualizzazioni delle linee connesse, vedi [Includere i criteri di filtro nei dati con tendenze nelle visualizzazioni delle linee sparkline e delle linee](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#include-filter-criteria-in-trended-data-in-sparklines-and-line-visualizations)
