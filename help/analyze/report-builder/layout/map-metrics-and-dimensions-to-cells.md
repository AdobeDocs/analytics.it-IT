---
description: Prima di iniziare a mappare gli elementi sul foglio di calcolo, accertatevi che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro non consente azioni da parte dell'utente, non sarà possibile selezionare le celle nel foglio di calcolo. Innanzitutto, rimuovere la protezione dal foglio e aggiungere le mappature delle celle.
seo-description: Prima di iniziare a mappare gli elementi sul foglio di calcolo, accertatevi che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro non consente azioni da parte dell'utente, non sarà possibile selezionare le celle nel foglio di calcolo. Innanzitutto, rimuovere la protezione dal foglio e aggiungere le mappature delle celle.
seo-title: Mappare metriche e dimensioni alle celle
solution: Analytics
title: Mappare metriche e dimensioni alle celle
topic: Generatore di report
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Mappare metriche e dimensioni alle celle

Prima di iniziare a mappare gli elementi sul foglio di calcolo, accertatevi che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro non consente azioni da parte dell'utente, non sarà possibile selezionare le celle nel foglio di calcolo. Innanzitutto, rimuovere la protezione dal foglio e aggiungere le mappature delle celle.

Il numero di aree e celle da mappare varia a seconda della metrica selezionata, della granularità, dell'intervallo di date e dei filtri impostati. Ad esempio, se si seleziona [!UICONTROL Site Metric] &gt; [!UICONTROL Traffic Report], si imposta [!UICONTROL Week] la granularità e si imposta l'intervallo di date per [!UICONTROL Last 2 Weeks], viene richiesto di mappare tre celle (quando si utilizza [!UICONTROL Custom Layout]) sul [!UICONTROL Request Wizard: Step 2]. La richiesta recupera i dati per la prima settimana e i dati per la seconda settimana, dove ogni valore punto dati = il valore di una visualizzazione pagina. La terza cella funge da intestazione di riga, che è possibile configurare utilizzando [!UICONTROL Format Options].

Se mappate erroneamente posizioni incompatibili nel foglio di calcolo, il generatore di report genera un errore.

Le sezioni che seguono contengono le informazioni seguenti:

* [Selezionare un intervallo di celle](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Tecniche per la selezione delle celle](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problemi durante la mappatura](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Selezionare un intervallo di celle {#section_1E37FB46DA194FB7A1050B8833A48AC6}

Quando [!UICONTROL Request Wizard: Step 2]abilitate [!UICONTROL Custom Layout] una richiesta con tendenze, potete mappare la richiesta a un intervallo di celle.

Fate clic sul file **[!UICONTROL Range Selector]** ![select_cell_icon.png](assets/select_cell_icon.png)

accanto all’elemento da mappare.

* **** Tutte le celle nell'intervallo: Richiede di selezionare un gruppo di celle per una richiesta di [!UICONTROL Custom Layout] stile.
* **** Prima cella dell'intervallo: Consente di selezionare la cella superiore sinistra dell'intervallo e visualizza l' [!UICONTROL Range] orientamento per specificare l'orientamento orizzontale o verticale delle celle di input e output (colonna o riga). Utilizzare questa opzione per fare in modo che il generatore di report selezioni le celle.
* **** Orientamento intervallo: Consente di orientare gli intervalli di celle come colonne o righe.
* **** Seleziona Posizione cella superiore intervallo: Visualizza i riferimenti delle celle.

## Tecniche per la selezione delle celle {#section_760421C3D7F84D67A639174710C93B22}

Per selezionare i dati, fai clic sull’ **[!UICONTROL Range Selection]** icona ![select_cell_icon.png](assets/select_cell_icon.png)

quindi fate clic e trascinate il mouse sull’intervallo di celle desiderato del foglio di calcolo. Una selezione continua viene delineata da un bordo nero.

![](assets/twenty_cells.gif)

Le righe selezionate separate hanno un sottile bordo bianco intorno a ciascuna riga.

![](assets/twoXten_cells_highlighted.gif)

Per mappare righe separate in una richiesta, usate il [!UICONTROL Control] tasto, quindi fate clic e trascinate il cursore sulle celle desiderate. Lo fareste se la vostra richiesta richiedesse quattro aree con dieci celle ciascuna, piuttosto che un'area continua con 40 celle insieme.

![](assets/map4.png)

Dopo aver selezionato le celle, fare di **[!UICONTROL Range Selector]** nuovo clic sul [!UICONTROL Range Selection] modulo per tornare alla [!UICONTROL Request Wizard: Step 2].

## Problemi durante la mappatura {#section_CC1BCF841291447EB3A994EB08F3A099}

Se si sceglie erroneamente di eseguire il mapping a una cella che ha già una mappatura attiva, nella casella di testo accanto all'icona del selettore dell'intervallo non viene visualizzato alcun riferimento di cella. Quando fai clic [!UICONTROL OK], generatore di report visualizza l'errore "L'intervallo selezionato interseca l'intervallo di un'altra richiesta. Cambia la selezione."

* Se è comunque necessario utilizzare la cella, fare clic con il pulsante destro del mouse sulla cella o sulle celle desiderate e selezionare **[!UICONTROL Delete Request]**.

Per evitare questo messaggio, puoi adottare due approcci:

* Pianificare il formato del rapporto aggiungendo la formattazione alle celle contenenti richieste e mappature
* Test delle aree del foglio di calcolo contenenti mappature

Per verificare le aree con richieste incorporate, potete:

* Avviate la tabella [!UICONTROL Request Manager] e fate clic sulle singole richieste elencate nella tabella. Facendo clic sulla richiesta vengono evidenziate le celle del foglio di calcolo in cui è mappata la richiesta.
* Selezionate le celle nel foglio di calcolo che intendete utilizzare per una nuova mappatura e fate clic su [!UICONTROL From Sheet]. Seleziona [!UICONTROL Request Manager] nell'elenco la richiesta contenente un elemento di output che interseca la cella selezionata. Se non è selezionata alcuna richiesta, la cella è disponibile.
* Selezionate le celle nel foglio di calcolo, fate clic con il pulsante destro del mouse nel menu di scelta rapida e verificate se [!UICONTROL Edit Request] sono disponibili. In tal caso, è presente una richiesta associata a tali celle.
