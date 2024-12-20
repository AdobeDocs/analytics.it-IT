---
title: Come utilizzare i segmenti nel Report Builder in Adobe Analytics
description: Descrive come utilizzare i segmenti in Report Builder per Adobe Analytics
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 2691fde0-59c6-45a7-80a5-8e5e221adce2
source-git-commit: ec14dde5b0e91a9fcfb217a811d36af2eea5f772
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# Utilizzare i segmenti nel Report Builder

È possibile applicare segmenti quando si crea un nuovo blocco di dati o quando si seleziona l&#39;opzione **Modifica blocco di dati** dal pannello COMANDI.

## Applicare segmenti a un blocco di dati

Per applicare un segmento all’intero blocco di dati, fai doppio clic su un segmento o trascina i filtri dall’elenco dei componenti alla sezione Segmenti della tabella.

## Applicare segmenti a singole metriche

Per applicare segmenti a singole metriche, trascina un segmento su una metrica nella tabella. È inoltre possibile fare clic sull&#39;icona **...** a destra di una metrica nel riquadro Tabella, quindi selezionare **[!UICONTROL Segment metric]**. Per visualizzare i segmenti applicati, passa il cursore del mouse su una metrica o selezionala nel riquadro Tabella. Le metriche con segmenti applicati visualizzano un’icona di filtro.

![Scheda Segmenti con le metriche visualizzate.](./assets/filter_by.png)

## Modifica rapida segmenti

Puoi utilizzare il pannello Modifica rapida per aggiungere, rimuovere o sostituire segmenti per i blocchi di dati esistenti.

Quando selezioni un intervallo di celle nel foglio di calcolo, il collegamento **[!UICONTROL Segments]** nel pannello di modifica rapida visualizza un elenco di riepilogo dei segmenti utilizzati dai blocchi di dati nella selezione.

Per modificare i segmenti mediante il pannello Modifica rapida

1. Seleziona un intervallo di celle da uno o più blocchi di dati.

   ![Pannello Quick Edit segment (Modifica rapida segmento) che mostra le opzioni dei segmenti per le suite di rapporti, l&#39;intervallo di date e i segmenti.](./assets/select_multiple_dbs.png)

1. Fai clic sul collegamento sotto **[!UICONTROL Segments]** per avviare il pannello Quick edit - Filters.

   ![il pannello Segmenti che mostra il campo Aggiungi segmenti e gli elenchi Segmenti applicati.](./assets/quick_edit_filters.png)

### Aggiungere o rimuovere un segmento

Puoi aggiungere o rimuovere segmenti utilizzando le opzioni Aggiungi/Rimuovi.

1. Selezionare la scheda **[!UICONTROL Add/Remove]** nel pannello Quick edit-segments (Modifica rapida segmenti).

   Tutti i segmenti applicati ai blocchi di dati selezionati sono elencati nel pannello Quick Edit-segments (Modifica rapida segmenti). I segmenti applicati a tutti i blocchi di dati nella selezione sono elencati nell&#39;intestazione **[!UICONTROL Applied to all selected data blocks]**. I segmenti applicati ad alcuni blocchi di dati, ma non a tutti, sono elencati nell&#39;intestazione **[!UICONTROL Applied to 1 or more selected data blocks]**.

   Quando nei blocchi di dati selezionati sono presenti più segmenti, è possibile cercare segmenti specifici utilizzando il campo di ricerca **[!UICONTROL Add Filter]**.

   ![Campo Aggiungi segmenti.](./assets/add_filter.png)

1. Aggiungere segmenti selezionando i segmenti dal menu a discesa **[!UICONTROL Add segment]**.

   L’elenco dei segmenti ricercabili include tutti i segmenti accessibili alle suite di rapporti presenti in uno o più blocchi di dati selezionati, nonché tutti i segmenti disponibili a livello globale nell’organizzazione.

   L’aggiunta di un segmento applica il segmento a tutti i blocchi di dati della selezione.

1. Per rimuovere i segmenti, fare clic sull&#39;icona Elimina **x** a destra dei segmenti nell&#39;elenco **[!UICONTROL Segments applied]**.

1. Fare clic su **[!UICONTROL Apply]** per salvare le modifiche e tornare al pannello hub.

   Nel Report Builder viene visualizzato un messaggio per confermare le modifiche apportate al segmento applicato.

### Sostituire un segmento

Puoi sostituire un segmento esistente con un altro segmento per modificare la modalità di segmentazione dei dati.

1. Selezionare la scheda **[!UICONTROL Replace]** nel pannello Quick edit-segment (Modifica rapida segmenti).

   ![Selezionare la scheda Sostituisci.](./assets/replace_filter.png)

1. Utilizza il campo di ricerca **[!UICONTROL Search list]** per individuare segmenti specifici.

1. Scegli uno o più segmenti da sostituire.

1. Cerca uno o più segmenti nel campo Sostituisci con.

   Selezionando un filtro, viene aggiunto all&#39;elenco **[!UICONTROL Replace with]**....

   ![La scheda Sostituisci con il blocco di dati Persone nell&#39;app selezionato e l&#39;elenco Sostituisci con aggiornato mostrano Persone nell&#39;app rivista.](./assets/replace_screen_new.png)

1. Fai clic su **[!UICONTROL Apply]**.

   Report Builder aggiorna l’elenco dei segmenti in base alla sostituzione.

### Definire i segmenti dei blocchi di dati dalla cella

I blocchi di dati possono fare riferimento a segmenti da una cella. Più blocchi di dati possono fare riferimento alla stessa cella per i segmenti, consentendo di cambiare facilmente segmenti per più blocchi di dati alla volta.

Per applicare segmenti da una cella

1. Passa al passaggio 2 nel processo di creazione o modifica dei blocchi di dati. Vedi [Creare un blocco di dati](./create-a-data-block.md).
1. Fare clic sulla scheda **[!UICONTROL Segments]** per definire i filtri.
1. Fai clic su **[!UICONTROL Create segment from cell]**.

   ![Crea segmento dall&#39;icona cella.](./assets/create-filter-from-cell.png)

1. Seleziona la cella da cui desideri che i blocchi di dati facciano riferimento a un segmento.

1. Aggiungi alla cella la scelta di segmento che desideri aggiungere facendo doppio clic sul segmento o trascinandolo nella sezione Segmenti inclusi.

   Nota: è possibile selezionare una sola scelta per la cella specificata alla volta.

   ![La finestra Aggiungi segmento da cella mostra i filtri inclusi.](./assets/select-filters.png)

1. Fare clic su **[!UICONTROL Apply]** per creare la cella di riferimento.

1. Dalla scheda **[!UICONTROL Segments]**, aggiungi i nuovi segmenti della cella di riferimento al blocco di dati.

   ![Scheda Segmenti che mostra il segmento Sheet1!J1(All Data) aggiunto alla tabella.](./assets/reference-cell-filter.png)

1. Fai clic su **[!UICONTROL Finish]**.

   Ora è possibile fare riferimento a questa cella da altri blocchi di dati nei loro segmenti. Per applicare la cella di riferimento come segmento ad altri blocchi di dati, è sufficiente aggiungere il riferimento di cella ai relativi segmenti dalla scheda Segmenti.

#### Utilizza la cella di riferimento per modificare i segmenti dei blocchi di dati

1. Selezionare la cella di riferimento nel foglio di calcolo.

1. Fare clic sul collegamento in **[!UICONTROL Segments from Cell]** nel menu Modifica rapida.

   ![Segmenti dal collegamento di cella che mostrano Sheet1!J1 (Tutti i dati)](./assets/filters-from-cell-link.png)

1. Seleziona il segmento dal menu a discesa.

   ![Menu a discesa Segmenti](./assets/filter-drop-down.png)

1. Fai clic su **[!UICONTROL Apply]**.
