---
description: Prima di iniziare a mappare gli elementi al foglio di calcolo, verificare che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro impedisce qualsiasi azione da parte dell'utente, non sarà possibile selezionare celle nel foglio di calcolo. Per prima cosa, rimuovere la protezione del foglio, quindi aggiungere mappature di celle.
title: Mappare metriche e dimensioni alle celle
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
feature: Report Builder
role: User, Admin
exl-id: e63fc679-39eb-417b-9a2b-6620db63a824
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 3%

---

# Mappare metriche e dimensioni alle celle

Prima di iniziare a mappare gli elementi al foglio di calcolo, verificare che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro impedisce qualsiasi azione da parte dell&#39;utente, non sarà possibile selezionare celle nel foglio di calcolo. Per prima cosa, rimuovere la protezione del foglio, quindi aggiungere mappature di celle.

Il numero di aree e celle da mappare varia in base alla metrica selezionata, alla granularità, all’intervallo di date e ai filtri impostati. Ad esempio, se selezioni [!UICONTROL Site Metric] > [!UICONTROL Traffic Report], impostato [!UICONTROL Week] granularità e impostazione dell’intervallo di date per [!UICONTROL Last 2 Weeks], viene richiesto di mappare tre celle (quando si utilizza [!UICONTROL Custom Layout]) sul [!UICONTROL Request Wizard: Step 2]. La richiesta recupera i dati per la settimana uno e i dati per la settimana due, dove ogni valore di punto dati = il valore di una visualizzazione di pagina. La terza cella funge da intestazione di riga, che puoi configurare utilizzando [!UICONTROL Format Options].

Se mappi erroneamente posizioni non compatibili sul foglio di calcolo, Report Builder genera un errore.

Le sezioni che seguono contengono le informazioni seguenti:

* [Seleziona un intervallo di celle](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Tecniche per la selezione delle celle](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problemi durante la mappatura](/help/analyze/report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Seleziona un intervallo di celle {#section_1E37FB46DA194FB7A1050B8833A48AC6}

Il giorno [!UICONTROL Request Wizard: Step 2], quando si abilita [!UICONTROL Custom Layout] per una richiesta con tendenze, puoi mappare la richiesta a un intervallo di celle.

Fai clic su **[!UICONTROL Range Selector]** ![select_cell_icon.png](assets/select_cell_icon.png)

accanto all&#39;elemento da mappare.

* **Tutte le celle nell&#39;intervallo:** Richiede la selezione di un gruppo di celle per un [!UICONTROL Custom Layout] richiesta di stile.
* **Prima cella dell&#39;intervallo:** Consente di selezionare la cella in alto a sinistra dell&#39;intervallo e di visualizzare [!UICONTROL Range] per specificare l&#39;orientamento orizzontale o verticale delle celle di input e output (colonna o riga). Utilizza questa opzione per fare in modo che Report Builder selezioni automaticamente le celle.
* **Orientamento intervallo:** Consente di orientare gli intervalli di celle come colonne o righe.
* **Seleziona posizione cella superiore intervallo:** Visualizza i riferimenti di cella.

## Tecniche per la selezione delle celle {#section_760421C3D7F84D67A639174710C93B22}

Per selezionare i dati, fare clic su **[!UICONTROL Range Selection]** icona  ![select_cell_icon.png](assets/select_cell_icon.png)

e trascinando il mouse sull&#39;intervallo di celle desiderato del foglio di calcolo. Una selezione continua è delimitata da un bordo nero.

![](assets/twenty_cells.gif)

Le righe selezionate separate presentano un sottile bordo bianco intorno a ogni riga.

![](assets/twoXten_cells_highlighted.gif)

Per mappare righe separate in una richiesta, utilizza [!UICONTROL Control] , quindi fare clic e trascinare il cursore sulle celle desiderate. Puoi eseguire questa operazione se la richiesta richiede quattro aree con dieci celle ciascuna, anziché un’area continua con 40 celle insieme.

![](assets/map4.png)

Dopo aver selezionato le celle, fare clic su **[!UICONTROL Range Selector]** di nuovo il [!UICONTROL Range Selection] modulo per tornare al [!UICONTROL Request Wizard: Step 2].

## Problemi durante la mappatura {#section_CC1BCF841291447EB3A994EB08F3A099}

Se si sceglie erroneamente di eseguire il mapping a una cella che dispone già di un mapping attivo, nella casella di testo accanto all&#39;icona del selettore di intervalli non verrà visualizzato alcun riferimento di cella. Quando fai clic su [!UICONTROL OK], Report Builder visualizza l’errore, &quot;L’intervallo selezionato interseca l’intervallo di un’altra richiesta. Modifica la selezione.&quot;

* Se è ancora necessario utilizzare la cella, fare clic con il pulsante destro del mouse sulla cella o sulle celle desiderate e selezionare **[!UICONTROL Delete Request]**.

Se desideri evitare questo messaggio, puoi adottare due approcci:

* Pianifica il formato del rapporto aggiungendo formattazione alle celle con richieste e mappature
* Verifica delle aree del foglio di calcolo contenenti mappature

Per verificare la presenza di aree con richieste incorporate, puoi effettuare le seguenti operazioni:

* Avvia il [!UICONTROL Request Manager] e fai clic sulle singole richieste elencate nella tabella. Facendo clic sulla richiesta vengono evidenziate le celle del foglio di calcolo in cui è mappata la richiesta.
* Seleziona le celle del foglio di calcolo che intendi utilizzare per una nuova mappatura e fai clic su [!UICONTROL From Sheet]. Il [!UICONTROL Request Manager] seleziona la richiesta nell’elenco che presenta un elemento di output che interseca la cella selezionata. Se non è selezionata alcuna richiesta, la cella è disponibile.
* Seleziona le celle nel foglio di calcolo, fai clic con il pulsante destro del mouse nel menu di scelta rapida e verifica se [!UICONTROL Edit Request] è disponibile. In tal caso, esiste una richiesta associata a queste celle.
