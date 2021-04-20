---
description: Prima di iniziare a mappare gli elementi sul foglio di calcolo, accertati che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro impedisce qualsiasi azione dell'utente, non sarà possibile selezionare le celle nel foglio di calcolo. Innanzitutto, deseleziona il foglio e aggiungi le mappature delle celle.
title: Mappare metriche e dimensioni alle celle
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 3%

---


# Mappare metriche e dimensioni alle celle

Prima di iniziare a mappare gli elementi sul foglio di calcolo, accertati che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro impedisce qualsiasi azione dell&#39;utente, non sarà possibile selezionare le celle nel foglio di calcolo. Innanzitutto, deseleziona il foglio e aggiungi le mappature delle celle.

Il numero di aree e celle da mappare varia a seconda della metrica selezionata, della granularità, dell’intervallo di date e dei filtri impostati. Ad esempio, se selezioni [!UICONTROL Site Metric] > [!UICONTROL Traffic Report], imposta la granularità [!UICONTROL Week] e imposta l’intervallo di date per [!UICONTROL Last 2 Weeks], ti viene richiesto di mappare tre celle (quando utilizzi [!UICONTROL Custom Layout]) sul [!UICONTROL Request Wizard: Step 2]. La richiesta recupera i dati della prima settimana e quelli della seconda settimana, dove ogni valore del punto dati = il valore di una visualizzazione di pagina. La terza cella funge da intestazione di riga, che è possibile configurare utilizzando [!UICONTROL Format Options].

Se mappi erroneamente posizioni non compatibili sul foglio di calcolo, Report Builder genera un errore.

Le sezioni che seguono contengono le informazioni seguenti:

* [Selezionare un intervallo di celle](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Tecniche per selezionare le celle](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problemi durante la mappatura](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Seleziona un intervallo di celle {#section_1E37FB46DA194FB7A1050B8833A48AC6}

Su [!UICONTROL Request Wizard: Step 2], quando abiliti [!UICONTROL Custom Layout] per una richiesta con tendenze, puoi mappare la richiesta a un intervallo di celle.

Fai clic su **[!UICONTROL Range Selector]** ![select_cell_icon.png](assets/select_cell_icon.png)

accanto all’elemento da mappare.

* **Tutte le celle nell’intervallo:** richiede di selezionare un gruppo di celle per una richiesta di  [!UICONTROL Custom Layout] stile.
* **Prima cella di intervallo:** consente di selezionare la cella in alto a sinistra dell’intervallo e visualizza l’ [!UICONTROL Range] orientamento per specificare l’orientamento orizzontale o verticale delle celle di input e output (colonna o riga). Utilizza questa opzione per fare in modo che il generatore di report selezioni le celle desiderate.
* **Orientamento intervallo:** consente di orientare gli intervalli di celle come colonne o righe.
* **Seleziona Posizione cella superiore intervallo:** visualizza i riferimenti di cella.

## Tecniche per la selezione delle celle {#section_760421C3D7F84D67A639174710C93B22}

Per selezionare i dati, fai clic sull&#39;icona **[!UICONTROL Range Selection]** ![select_cell_icon.png](assets/select_cell_icon.png)

e fai clic su trascina il mouse sull’intervallo di celle desiderato nel foglio di calcolo. Una selezione continua è evidenziata da un bordo nero.

![](assets/twenty_cells.gif)

Le righe selezionate separate hanno un sottile bordo bianco intorno a ciascuna riga.

![](assets/twoXten_cells_highlighted.gif)

Per mappare righe separate in una richiesta, utilizza il tasto [!UICONTROL Control] , quindi fai clic e trascina il cursore sulle celle desiderate. Lo fareste se la vostra richiesta richiedesse quattro aree con dieci celle ciascuna, invece di un&#39;area continua con 40 celle insieme.

![](assets/map4.png)

Dopo aver selezionato le celle, fare di nuovo clic su **[!UICONTROL Range Selector]** nel modulo [!UICONTROL Range Selection] per tornare alla cartella [!UICONTROL Request Wizard: Step 2].

## Problemi durante la mappatura {#section_CC1BCF841291447EB3A994EB08F3A099}

Se scegli erroneamente di eseguire il mapping a una cella che ha già una mappatura attiva, noterai che nella casella di testo accanto all’icona del selettore dell’intervallo non viene visualizzato alcun riferimento di cella. Quando fai clic su [!UICONTROL OK], Report Builder visualizza l&#39;errore &quot;L&#39;intervallo selezionato interseca l&#39;intervallo di un&#39;altra richiesta. Modifica la selezione.&quot;

* Se è ancora necessario utilizzare la cella, fare clic con il pulsante destro del mouse sulla cella o sulle celle desiderate e selezionare **[!UICONTROL Delete Request]**.

Per evitare questo messaggio, puoi adottare due approcci:

* Pianifica il formato del rapporto aggiungendo formattazione alle celle contenenti richieste e mappature
* Verifica delle aree del foglio di calcolo contenenti mappature

Per verificare le aree con richieste incorporate, puoi:

* Avvia [!UICONTROL Request Manager] e fai clic sulle singole richieste elencate nella tabella. Facendo clic sulla richiesta vengono evidenziate le celle del foglio di calcolo in cui è mappata la richiesta.
* Seleziona le celle nel foglio di calcolo che intendi utilizzare per una nuova mappatura e fai clic su [!UICONTROL From Sheet]. La [!UICONTROL Request Manager] seleziona la richiesta nell&#39;elenco che ha un elemento di output che interseca la cella selezionata. Se non è selezionata alcuna richiesta, la cella è disponibile.
* Seleziona le celle nel foglio di calcolo, fai clic con il pulsante destro del mouse nel menu di scelta rapida e verifica se [!UICONTROL Edit Request] è disponibile. In tal caso, è presente una richiesta associata a queste celle.
