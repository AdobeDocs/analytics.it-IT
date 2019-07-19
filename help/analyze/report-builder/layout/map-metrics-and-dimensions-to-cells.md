---
description: Prima di iniziare a mappare gli elementi sul foglio di calcolo, accertarsi che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro non consente qualsiasi azione utente, non sarà possibile selezionare le celle nel foglio di calcolo. Innanzitutto, rimuovete il foglio e aggiungete le mappature di cella.
seo-description: Prima di iniziare a mappare gli elementi sul foglio di calcolo, accertarsi che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro non consente qualsiasi azione utente, non sarà possibile selezionare le celle nel foglio di calcolo. Innanzitutto, rimuovete il foglio e aggiungete le mappature di cella.
seo-title: Mappare metriche e dimensioni alle celle
solution: Analytics
title: Mappare metriche e dimensioni alle celle
topic: Generatore di report
uuid: 50893 e 1 c -5 f 2 c -4558-8001-41 e 70 d 74 d 6 e 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Mappare metriche e dimensioni alle celle

Prima di iniziare a mappare gli elementi sul foglio di calcolo, accertarsi che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro non consente qualsiasi azione utente, non sarà possibile selezionare le celle nel foglio di calcolo. Innanzitutto, rimuovete il foglio e aggiungete le mappature di cella.

Il numero di aree e celle da mappare varia a seconda della metrica selezionata, della granularità, dell'intervallo di date e dei filtri impostati. For example, if you select [!UICONTROL Site Metric] &gt; [!UICONTROL Traffic Report], set [!UICONTROL Week] granularity, and set date range for [!UICONTROL Last 2 Weeks], you are prompted to map three cells (when using [!UICONTROL Custom Layout]) on the [!UICONTROL Request Wizard: Step 2]. La richiesta recupera i dati per la settimana uno e i dati per la settimana due, dove ogni valore di punto dati = il valore di una visualizzazione di pagina. Your third cell serves as the row heading, which you can configure using [!UICONTROL Format Options].

Se mappate erroneamente posizioni incompatibili sul foglio di calcolo, il generatore di report genera un errore.

Le sezioni che seguono contengono le informazioni seguenti:

* [Selezionare un intervallo di celle](../../../analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Tecniche per selezionare le celle](../../../analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problemi durante la mappatura](../../../analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Select a Range of Cells {#section_1E37FB46DA194FB7A1050B8833A48AC6}

On the [!UICONTROL Request Wizard: Step 2], when you enable [!UICONTROL Custom Layout] for a trended request, you can map the request to a range of cells.

Click the **[!UICONTROL Range Selector]** ![select_cell_icon.png](assets/select_cell_icon.png)

accanto all'elemento da mappare.

* ** All Cells in Range:** Requires you to select a group of cells for a [!UICONTROL Custom Layout] style request.

* ** First Cell of Range:** Lets you select the top-left cell of the range, and displays the [!UICONTROL Range] orientation to specify the horizontal or vertical orientation of input and output cells (column or row). Utilizzate questa opzione per selezionare le celle con il generatore di report.

* ** Orientamento intervallo: ** Consente di orientare gli intervalli di celle come colonne o righe.
* **Seleziona Posizione cella superiore dell'intervallo:** Visualizza i riferimenti di cella.

## Techniques for selecting cells {#section_760421C3D7F84D67A639174710C93B22}

You select the data by clicking the **[!UICONTROL Range Selection]** icon  ![select_cell_icon.png](assets/select_cell_icon.png)

e trascinate il mouse sull'intervallo di celle desiderato. Una selezione continua è delineata da un bordo nero.

![](assets/twenty_cells.gif)

Le righe selezionate separate presentano un bordo bianco sottili intorno a ogni riga.

![](assets/twoXten_cells_highlighted.gif)

To map separate rows in one request, use the [!UICONTROL Control] key, then click and drag the cursor over the desired cells. A questo scopo, se la richiesta richiede quattro aree con dieci celle ciascuna, anziché un'area continua con 40 celle insieme.

![](assets/map4.png)

After you select cells, click the **[!UICONTROL Range Selector]** again on the [!UICONTROL Range Selection] form to return to the [!UICONTROL Request Wizard: Step 2].

## Issues when mapping {#section_CC1BCF841291447EB3A994EB08F3A099}

Se decidete di mappare erroneamente una cella con già una mappatura attiva, noterete che nella casella di testo accanto all'icona del selettore intervallo non viene visualizzato alcun riferimento di cella. When you click [!UICONTROL OK], report builder displays the error, "The range selected intersects another request's range. Modificate la selezione. "

* If you still need to use the cell, right-click on the desired cell or cells, and select **[!UICONTROL Delete Request]**.

Se desiderate evitare questo messaggio, potete adottare due approcci:

* Pianificare il formato del rapporto aggiungendo la formattazione alle celle con richieste e mappature
* Verificare le aree del foglio di calcolo contenenti mappature

Per verificare le aree con richieste incorporate, potete:

* Launch the [!UICONTROL Request Manager] and click on individual requests listed in the table. Facendo clic sulla richiesta vengono evidenziate le celle del foglio di calcolo in cui la richiesta viene mappata.
* Select cells in the spreadsheet you intend to use for a new mapping and click [!UICONTROL From Sheet]. The [!UICONTROL Request Manager] selects the request in the list which has an output item that intersects the selected cell. Se non è selezionata alcuna richiesta, la cella è disponibile.

* Select cells in the spreadsheet, right-click in the context menu and verify if [!UICONTROL Edit Request] is available. In tal caso, esiste una richiesta associata a queste celle.

