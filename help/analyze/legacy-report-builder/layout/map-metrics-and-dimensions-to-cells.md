---
description: Scopri come selezionare un intervallo di celle, le tecniche di selezione delle celle e la risoluzione dei problemi di mappatura.
title: Scopri come mappare metriche e dimensioni alle celle
uuid: 50893e1c-5f2c-4558-8001-41e70d74d6e7
feature: Report Builder
role: User, Admin
exl-id: e63fc679-39eb-417b-9a2b-6620db63a824
TQID: https://experienceleague.adobe.com/yeU4gugMR2nSKwjo4LuX79spXIaD4UtuaTQ52bZwGrU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 627
ht-degree: 1%

---

# Mappare metriche e dimensioni alle celle

{{legacy-arb}}

Prima di iniziare a mappare gli elementi al foglio di calcolo, verificare che il foglio di calcolo non sia protetto. Se lo schema di protezione del foglio di lavoro impedisce qualsiasi azione da parte dell&#39;utente, non sarà possibile selezionare celle nel foglio di calcolo. Per prima cosa, rimuovere la protezione del foglio, quindi aggiungere mappature di celle.

Il numero di aree e celle da mappare varia in base alla metrica selezionata, alla granularità, all’intervallo di date e ai filtri impostati. Se ad esempio si seleziona [!UICONTROL Site Metric] > [!UICONTROL Traffic Report], si imposta la granularità [!UICONTROL Week] e si imposta l&#39;intervallo di date per [!UICONTROL Last 2 Weeks], verrà richiesto di mappare tre celle (quando si utilizza [!UICONTROL Custom Layout]) in [!UICONTROL Request Wizard: Step 2]. La richiesta recupera i dati per la settimana uno e i dati per la settimana due, dove ogni valore di punto dati è uguale al valore di una visualizzazione di pagina. La terza cella funge da intestazione di riga, che puoi configurare utilizzando [!UICONTROL Format Options].

Se mappi erroneamente posizioni non compatibili sul foglio di calcolo, Report Builder genera un errore.

Per ulteriori informazioni, vedere le sezioni seguenti:

* [Seleziona un intervallo di celle](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_1E37FB46DA194FB7A1050B8833A48AC6)
* [Tecniche per la selezione delle celle](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_760421C3D7F84D67A639174710C93B22)
* [Problemi durante la mappatura](/help/analyze/legacy-report-builder/layout/map-metrics-and-dimensions-to-cells.md#section_CC1BCF841291447EB3A994EB08F3A099)

## Seleziona un intervallo di celle {#section_1E37FB46DA194FB7A1050B8833A48AC6}

In [!UICONTROL Request Wizard: Step 2], quando abiliti [!UICONTROL Custom Layout] per una richiesta con tendenze, puoi mappare la richiesta a un intervallo di celle.

Fai clic sul **[!UICONTROL Range Selector]** ![select_cell_icon.png](assets/select_cell_icon.png) accanto all&#39;elemento da mappare.

* **Tutte le celle nell&#39;intervallo:** È necessario selezionare un gruppo di celle per una richiesta di stile [!UICONTROL Custom Layout].
* **Prima cella dell&#39;intervallo:** Consente di selezionare la cella superiore sinistra dell&#39;intervallo e di visualizzare l&#39;orientamento [!UICONTROL Range] per specificare l&#39;orientamento orizzontale o verticale delle celle di input e di output (colonna o riga). Utilizzare questa opzione per fare in modo che Report Builder selezioni automaticamente le celle.
* **Orientamento intervallo:** Consente di orientare gli intervalli di celle come colonne o righe.
* **Seleziona posizione cella superiore dell&#39;intervallo:** Visualizza i riferimenti di cella.

## Tecniche per la selezione delle celle {#section_760421C3D7F84D67A639174710C93B22}

Selezionare i dati facendo clic sull&#39;icona **[!UICONTROL Range Selection]** ![select_cell_icon.png](assets/select_cell_icon.png)

e trascinando il mouse sull&#39;intervallo di celle desiderato del foglio di calcolo. Una selezione continua è delimitata da un bordo nero.

![](assets/twenty_cells.gif)

Le righe selezionate separate presentano un sottile bordo bianco intorno a ogni riga.

![](assets/twoXten_cells_highlighted.gif)

Per mappare righe separate in una richiesta, utilizzare il tasto [!UICONTROL Control], quindi fare clic e trascinare il cursore sulle celle desiderate. Puoi eseguire questa operazione se la richiesta richiede quattro aree con dieci celle ciascuna, anziché un’area continua con 40 celle insieme.

![](assets/map4.png)

Dopo aver selezionato le celle, fare di nuovo clic su **[!UICONTROL Range Selector]** nel modulo [!UICONTROL Range Selection] per tornare a [!UICONTROL Request Wizard: Step 2].

## Risoluzione dei problemi di mappatura{#section_CC1BCF841291447EB3A994EB08F3A099}

Se si sceglie erroneamente di eseguire il mapping a una cella che dispone già di un mapping attivo, nella casella di testo accanto all&#39;icona del selettore di intervalli non verrà visualizzato alcun riferimento di cella. Quando si fa clic su [!UICONTROL OK], in Report Builder viene visualizzato l&#39;errore *L&#39;intervallo selezionato interseca l&#39;intervallo di un&#39;altra richiesta. Modifica la selezione.*

* Se è ancora necessario utilizzare la cella, fare clic con il pulsante destro del mouse sulla cella o sulle celle desiderate e selezionare **[!UICONTROL Delete Request]**.

Se desideri evitare questo messaggio, puoi adottare due approcci:

* Pianifica il formato del rapporto aggiungendo formattazione alle celle con richieste e mappature
* Verifica delle aree del foglio di calcolo contenenti mappature

Per verificare la presenza di aree con richieste incorporate, puoi effettuare le seguenti operazioni:

* Avvia [!UICONTROL Request Manager] e fai clic sulle singole richieste elencate nella tabella. Facendo clic sulla richiesta vengono evidenziate le celle del foglio di calcolo in cui è mappata la richiesta.
* Selezionare le celle del foglio di calcolo che si desidera utilizzare per una nuova mappatura e fare clic su [!UICONTROL From Sheet]. [!UICONTROL Request Manager] seleziona la richiesta nell&#39;elenco che ha un elemento di output che interseca la cella selezionata. Se non è selezionata alcuna richiesta, la cella è disponibile.
* Selezionare le celle nel foglio di calcolo, fare clic con il pulsante destro del mouse nel menu di scelta rapida e verificare se [!UICONTROL Edit Request] è disponibile. In tal caso, esiste una richiesta associata a queste celle.
