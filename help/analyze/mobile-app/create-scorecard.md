---
description: Come creare una scorecard delle dashboard di Adobe Analytics
title: Creare una scorecard
feature: Analytics Dashboards
role: User, Admin
source-git-commit: 5c9502536c96bc43288adfa259f1b60e6fd078c0
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 76%

---


# Creare una scorecard

Le informazioni riportate di seguito spiegano ai curatori di dati di Adobe Analytics come configurare e presentare dashboard per gli utenti esecutivi. Per iniziare, puoi visualizzare il video Creatore di scorecard delle dashboard di Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/34544)

Una scheda di valutazione di Adobe Analytics visualizza le visualizzazioni dei dati chiave per gli utenti esecutivi in un layout a tessere, come illustrato di seguito:

![Esempio di scorecard](assets/intro_scorecard.png)

In qualità di curatore di questa scorecard, puoi utilizzare lo strumento di creazione delle scorecard per configurare quali tessere visualizzare sulla scorecard per il consumatore esecutivo. Puoi anche configurare in che modo le viste dettagliate, o le suddivisioni, possono essere regolate una volta che le tessere vengono toccate. L’interfaccia del Creatore di scorecard è mostrata di seguito:

![Creatore di scorecard](assets/scorecard_builder.png)

Per creare la scorecard, devi effettuare le seguenti operazioni:

1. Accedi al modello [!UICONTROL Blank Mobile Scorecard].
2. Configura la scorecard con i dati e salvala.

## Accedi al modello [!UICONTROL Blank Mobile Scorecard]

Puoi accedere al modello [!UICONTROL Blank Mobile Scorecard] creando un nuovo progetto o dal menu Strumenti .

### Creare un nuovo progetto

1. Apri Adobe Analytics e fai clic sulla scheda **[!UICONTROL Workspace]**.
1. Fai clic su **[!UICONTROL Create project]** e seleziona il modello di progetto **[!UICONTROL Blank mobile scorecard]**.
1. Fai clic su **[!UICONTROL Create]**.

![Template Scorecard](assets/new_template.png)

### Modello Strumenti

1. Dal menu **[!UICONTROL Tools]**, seleziona **[!UICONTROL Analytics dashboards (Mobile App)]**.
1. Nella schermata successiva, fai clic sul pulsante **[!UICONTROL Create new scorecard]**.

## Configura la scorecard con i dati e salvala

Per implementare il template della scorecard:

1. Alla voce **[!UICONTROL Properties]** (nella barra a destra), specifica la **[!UICONTROL Project report suite]** della quale desideri utilizzare i dati.

   ![Selezione di suite di rapporti](assets/properties_save.png)

1. Per aggiungere una nuova tessera alla scorecard, trascina una metrica dal pannello a sinistra e rilasciala nella zona **[!UICONTROL Drag and Drop Metrics Here]**. È anche possibile inserire una metrica tra due tessere utilizzando un flusso di lavoro simile.

   ![Aggiungere tessere](assets/build_list.png)


   *Da ogni tessera, è possibile accedere a una vista dettagliata che visualizza informazioni aggiuntive sulla metrica, come gli elementi principali di un elenco di dimensioni correlate.*

### Aggiungere dimensioni o metriche

Per aggiungere una dimensione correlata a una metrica:

Trascina una dimensione dal pannello a sinistra e rilasciala su una tessera.

Ad esempio, per aggiungere le dimensioni appropriate (come **[!DNL DMA Region]**, in questo esempio) alla metrica **[!UICONTROL Unique Visitors]**, trascinale sulla tessera; le dimensioni che aggiungi verranno visualizzate nella sezione breakdown delle **[!UICONTROL Properties]** specifiche della tessera. Puoi aggiungere più dimensioni a ogni tessera.

![Aggiunta di dimensioni](assets/layer_dimensions.png)

### Visualizzare e configurare le proprietà dei riquadri

Quando fai clic su una tessera nel Creatore di scorecard, la barra a destra mostra le proprietà e le caratteristiche associate a tale tessera. In questa barra puoi assegnare un nuovo **[!UICONTROL Title]** alla tessera e, in alternativa, configurarla specificando i componenti invece di trascinarli dalla barra di sinistra.

![Tessera delle proprietà](assets/properties_tile.png)

Inoltre, se fai clic sulle tessere, un pop-up dinamico mostrerà come la vista Raggruppamento viene visualizzata dall’utente esecutivo nell’app. Se non è stata applicata alcuna dimensione alla tessera, la dimensione di raggruppamento sarà **ore** o **giorni**, a seconda dell’intervallo date predefinito.

![Vista_Raggruppamento](assets/break_view.png)

Ogni dimensione aggiunta alla tessera viene visualizzata in un elenco a discesa nella vista dettagliata dell’app. L’utente esecutivo può quindi scegliere tra le opzioni elencate nell’elenco a discesa.

### Applicare i segmenti

Per applicare segmenti alle singole tessere, trascina un segmento dal pannello di sinistra e rilascialo direttamente sulla tessera.

Se vuoi applicare il segmento a tutte le tessere della scorecard, rilascia la tessera sopra la scorecard. Oppure, puoi anche applicare i segmenti selezionandoli nel menu del filtro sotto gli intervalli di date. Puoi [configurare e applicare filtri per le scorecard](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=it) nello stesso modo che utilizzeresti in Adobe Analytics Workspace.

![Creare segmenti per il filtro](assets/segment_ui.png)

### Rimuovere i componenti

Allo stesso modo, per rimuovere un componente applicato all’intera scorecard, fai clic sulla scorecard al di fuori delle tessere, quindi fai clic sulla **x** che compare quando passi il mouse sul componente, come mostrato di seguito per il segmento **Nuovo visitatore**:

![Rimuovere_componenti](assets/new_remove.png)

### Intervalli di date

Aggiungi e rimuovi combinazioni di intervalli di date che possono essere selezionate nella scorecard mediante il menu a discesa dell’intervallo di date.

![Nuova scorecard](assets/new_score_card.png)

Ogni nuova scorecard inizia con 6 combinazioni di intervalli di date incentrate sui dati di oggi e ieri. Per rimuovere gli intervalli di date di cui non hai bisogno, fai clic sulla x. Per modificare una combinazione di intervalli di date, fai clic sull’icona della matita.

![Nuova scorecard2](assets/new_score_card2.png)

Per creare o modificare una data primaria, utilizza il menu a discesa per selezionare uno degli intervalli di date disponibili oppure trascina un componente data dalla barra a destra fino alla zona di rilascio.

![Nuova scorecard3](assets/new_score_card3.png)

Per creare una data di confronto, puoi scegliere tra i pratici predefiniti per i confronti temporali più comuni, disponibili nel menu a discesa. Puoi anche trascinare un componente data dalla barra a destra.

![Nuova scorecard4](assets/new_score_card4.png)

Se l’intervallo di date desiderato non è ancora stato creato, puoi crearne uno nuovo facendo clic sull’icona Calendario.

![Nuova scorecard5](assets/new_score_card5.png)

Viene visualizzato il generatore di intervalli di date, in cui è possibile creare e salvare un nuovo componente Intervallo di date.

## Assegnare un nome a una scorecard

Per dare un nome alla scorecard, fai clic sullo spazio del nome in alto a sinistra dello schermo e digita il nuovo nome.

![Assegnare_un_nome_alle_scorecard](assets/new_name.png)

## Condividi la scorecard

Per condividere la scorecard con un utente esecutivo:

1. Fai clic sul menu **[!UICONTROL Share]** e seleziona **[!UICONTROL Share scorecard]**.

1. Nel modulo **[!UICONTROL Share mobile scorecard]**, compila i campi:

   * Inserendo il nome della scorecard
   * Inserendo una descrizione della scorecard
   * Aggiungendo tag rilevanti
   * Specificando i destinatari della scorecard

1. Fai clic su **[!UICONTROL Share]**.

![Condividere_scorecard](assets/new_share.png)

Dopo aver condiviso una scorecard, i destinatari possono accedervi sulle proprie dashboard di Analytics. Se apporti modifiche successive alla scorecard nel Creatore di scorecard, queste verranno aggiornate automaticamente nella scorecard condivisa. Gli utenti esecutivi vedranno poi i cambiamenti dopo aver aggiornato la scorecard nella loro app.

Se aggiorni la scorecard aggiungendo nuovi componenti, ti consigliamo di condividerla nuovamente e di selezionare l’opzione **[!UICONTROL Share embedded components]** (condividi componenti incorporati) per assicurarti che gli utenti esecutivi abbiano accesso a queste modifiche.