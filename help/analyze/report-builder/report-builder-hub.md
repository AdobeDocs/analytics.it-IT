---
title: Hub Report Builder
description: Scopri l’hub Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: e18381ea-b7d4-4d7a-9ded-23b2d06fa204
source-git-commit: ff1722416fe5062d16c12185d17271ebc2d6b624
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 25%

---

# Hub Report Builder


L&#39;hub Report Builder è il riquadro destro visualizzato nella cartella di lavoro di Excel quando si seleziona ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** dalla barra multifunzione di Excel.

Utilizza l’hub Report Builder per creare, aggiornare, eliminare e gestire i blocchi di dati.

L&#39;hub Report Builder contiene i pulsanti ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**, ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** e ![Calendar](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]**, il pannello **[!UICONTROL Commands]** e il pannello **[!UICONTROL Quick edit]**.

![Hub Report Builder](assets/hub51.png){zoomable="yes"}


Seleziona

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]** per [creare nuovi blocchi di dati](create-a-data-block.md).
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]** per [gestire i blocchi di dati esistenti](manage-reportbuilder.md).
* ![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL Schedule]** per [gestire pianificazioni per inviare la cartella di lavoro tramite e-mail](schedule-reportbuilder.md).

## Pannello Comandi

Utilizzare il pannello **[!UICONTROL Commands]** per accedere a comandi compatibili con le celle selezionate o con un&#39;azione precedente.

| Comandi | Quando è disponibile | Finalità |
|------|------------------|--------|
| ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Edit data block]** | La cella o l’intervallo di celle selezionato fa parte di un solo blocco di dati. | Utilizza per modificare un blocco di dati. |
| ![Aggiorna](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]** | La selezione contiene almeno un blocco di dati. Il comando aggiorna solo i blocchi di dati nella selezione. | Utilizza per aggiornare uno o più blocchi di dati. |
| ![AggiornaDocumento](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** | La cartella di lavoro contiene uno o più blocchi di dati. | Utilizzare per aggiornare tutti i blocchi di dati nella cartella di lavoro |
| ![Invia](/help/assets/icons/Send.svg) **[!UICONTROL Send workbook]** | La cartella di lavoro contiene uno o più blocchi di dati. | Utilizza per [inviare la cartella di lavoro come file tramite e-mail](schedule-reportbuilder.md). |
| ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copy data block]** | La cella o l’intervallo di celle selezionato fa parte di uno o più blocchi di dati. | Utilizza per copiare un blocco di dati. |
| ![Taglia](/help/assets/icons/Cut.svg) **[!UICONTROL Cut data block]** | La cella o l’intervallo di celle selezionato fa parte di uno o più blocchi di dati. | Utilizza per tagliare un blocco di dati. |
| ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Delete data block]** | La cella o l’intervallo di celle selezionato fa parte di un solo blocco di dati. | Utilizzare per eliminare un blocco di dati |

## Pannello Quick edit (Modifica rapida)

Quando selezioni uno o più blocchi di dati in un foglio di calcolo, Report Builder visualizza il pannello **[!UICONTROL Quick edit]**. È possibile utilizzare il pannello **[!UICONTROL Quick edit]** per modificare i parametri in uno o più blocchi di dati contemporaneamente.

Le modifiche apportate quando si utilizzano le sezioni **[!UICONTROL Quick Edit]** vengono applicate a tutti i blocchi di dati selezionati.

### di Report Suite Manager

I blocchi di dati estraggono dati da una suite di rapporti selezionata. Se più blocchi di dati sono selezionati in un foglio di lavoro e non estraggono dati dalla stessa suite di rapporti, il collegamento **Suite di rapporti** visualizza **[!UICONTROL _Multiple_]**.

Quando modifichi la suite di rapporti, tutti i blocchi di dati nella selezione adottano la nuova suite di rapporti. I componenti nel blocco di dati vengono associati alla nuova suite di rapporti in base all’ID. Se un componente non viene trovato in un blocco di dati, il componente viene rimosso e sostituito con **[!UICONTROL Invalid value]** oppure viene visualizzato ![AlertRed](/help/assets/icons/AlertRed.svg) per il componente specifico.

Per modificare la suite di rapporti, seleziona una nuova suite di rapporti dal menu a discesa **[!UICONTROL Report suite]**.


### Intervallo date

**Intervallo date** mostra l’intervallo di date per i blocchi di dati selezionati. Se sono selezionati più blocchi di dati con più intervalli di date, il collegamento **[!UICONTROL Date range]** visualizza **[!UICONTROL _Multiple_]**.

### Segmenti

Il collegamento **Segmenti** visualizza un elenco di riepilogo dei segmenti utilizzati dai blocchi di dati selezionati. Se sono selezionati più blocchi di dati con più segmenti applicati, il collegamento **Segmenti** visualizza **[!UICONTROL _Multipli_]**.

>[!MORELIKETHIS]
>
>[Seleziona una suite di rapporti](select-report-suite.md)
>[Seleziona un intervallo di date](select-date-range.md)
>[Utilizzare i filtri](work-with-segments.md)
>

<!--

Use the Report Builder hub to create, update, delete, and manage data blocks.

The Report Builder hub contains the Create, Manage, and Schedule buttons, the COMMANDS panel, and The QUICK EDIT panel.

<img src="./assets/hub51.png" alt="Report Builder Hub"/>


## Create, Manage, and Schedule buttons

Use the Create, Manage, and Schedule buttons to create new data blocks, manage existing data blocks, or schedule datablocks.

## COMMANDS panel

Use the COMMANDS panel to access commands that are compatible with the selected cells or a previous action.

### Commands

| Commands displayed      | Available when…   | Purpose          |
|------|------------------|--------|
| Edit data block | The selected cell or cells range is part of one data block only. | Used to edit a data block |
| Refresh data block | The selection contains at least one data block. The command refreshes only the data blocks in the selection. | Used to refresh one or more data blocks |
| Refresh all data blocks | The workbook contains one or more data blocks. | Used to refresh ALL data blocks in the workbook |
| Send workbook |   |  Send a workbook on a schedule. |
| Copy data block   | The selected cell or cell range is part of one or more data blocks. | Used to copy a data block   |
| Cut data block |   | Used to cut a data block |
| Delete data block | The selected cell or cells range is part of one data block only. | Used to delete a data block |

## QUICK EDIT panel

When you select one or more data blocks in a spreadsheet, Report Builder displays the QUICK EDIT panel. You can use the QUICK EDIT panel to change parameters in a single data block or to change parameters in multiple data blocks at the same time.

![The Quick Edit panel in Report Builder](./assets/hub2.png)

The changes made using the Quick Edit sections apply to all selected data blocks.

### Report suites

Data blocks pull data from a selected report suite. If multiple data blocks are selected in a worksheet and they don't pull data from the same report suite, the **Report Suites** link displays *Multiple*.

When you change the report suite, all data blocks in the selection adopt the new report suite. Components in the data block are matched to the new report suite based on ID, for example, matching ```evars```). If a component isn't found in a data block, a warning message is displayed and the component is removed from the data block.

To change the report suite, select a new report suite from the drop-down menu.

![The Report Builder Hub showing the report suite drop-down menu.](./assets/image16.png)

### Date range

**[!UICONTROL Date range]** shows the date range for the selected data blocks. If multiple data blocks are selected with multiple date ranges, the **[!UICONTROL Date range]** link displays *Multiple*. [Learn more](/help/analyze/report-builder/select-date-range.md)

### Segments

The **Segments** link displays a summary list of the segments used by the selected data blocks. If multiple data blocks are selected with multiple segments applied, the **Segments** link displays *Multiple*. [Learn more](/help/analyze/report-builder/work-with-segments.md)

-->