---
description: Come creare una scorecard per le dashboard di Adobe Analytics
title: Creare una scorecard per dispositivi mobili
feature: Analytics Dashboards
role: User, Admin
exl-id: ebe6d83d-bbae-43de-bf85-35258bf6c1d0
source-git-commit: 7f630839ae7d75730f93588877a172f3590d5a5e
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 92%

---

# Creare una scorecard per dispositivi mobili

Le informazioni riportate di seguito spiegano ai curatori di dati di Adobe Analytics come configurare e presentare scorecard per dispositivi mobili per gli utenti manageriali. Per iniziare, puoi visualizzare il video Creazione di scorecard per le dashboard di Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/34544)

Una scorecard Adobe Analytics mostra le visualizzazioni dei dati chiave per gli utenti manageriali in un layout a tessere affiancate, come mostrato di seguito:

![Esempio di scorecard](assets/intro_scorecard.png)

In qualità di curatore di questa scorecard, puoi usare la funzione di creazione scorecard per configurare le tessere da presentare all’utente manageriale sulla scorecard. Puoi anche configurare il modo in cui le viste dettagliate, o i raggruppamenti, possono essere regolati una volta che le tessere vengono toccate. L’interfaccia del Creatore di scorecard è mostrata di seguito:

![Creatore di scorecard](assets/scorecard_builder.png)

Per creare la scorecard, dovrai procedere in questo modo:

1. Accedi al modello [!UICONTROL Blank Mobile Scorecard].
2. Configura la scorecard con i dati e salvala.

## Accedi al modello [!UICONTROL Blank Mobile Scorecard] {#template}

Puoi accedere al modello [!UICONTROL Blank Mobile Scorecard] creando un nuovo progetto o dal menu degli strumenti.

### Creare un nuovo progetto {#create}

1. Apri Adobe Analytics e fai clic sulla scheda **[!UICONTROL Workspace]**.
1. Fai clic sul pulsante **[!UICONTROL Create project]** e seleziona il modello di progetto **[!UICONTROL Blank mobile scorecard]**.
1. Fai clic su **[!UICONTROL Create]**.

![Template Scorecard](assets/new_template.png)

### Menu Strumenti

1. Dal menu **[!UICONTROL Tools]**, seleziona **[!UICONTROL Analytics dashboards (Mobile App)]**.
1. Nella schermata successiva, fai clic su **[!UICONTROL Create new scorecard]**.

## Configurare la scorecard con i dati e salvarla {#configure}

Per implementare il template della scorecard:

1. Alla voce **[!UICONTROL Properties]** (nella barra a destra), specifica la **[!UICONTROL Project report suite]** della quale desideri utilizzare i dati.

   ![Selezione di suite di rapporti](assets/properties_save.png)

1. Per aggiungere una nuova tessera alla scorecard, trascina una metrica dal pannello a sinistra e rilasciala nella zona **[!UICONTROL Drag and Drop Metrics Here]**. È anche possibile inserire una metrica tra due tessere utilizzando un flusso di lavoro simile.

   ![Aggiungere tessere](assets/build_list.png)


1. Da ogni tessera, è possibile accedere a una vista dettagliata che visualizza informazioni aggiuntive sulla metrica, come gli elementi principali di un elenco di dimensioni correlate.

## Aggiungere dimensioni o metriche {#dimsmetrics}

Per aggiungere una dimensione correlata a una metrica, trascina una dimensione dal pannello di sinistra e rilasciala su una tessera.

Ad esempio, puoi aggiungere dimensioni appropriate (come **[!DNL Marketing Channel]**, in questo esempio) alla metrica **[!UICONTROL Unique Visitors]** trascinandola e rilasciandola sulla tessera. Le suddivisioni delle singole dimensioni vengono visualizzate nella sezione [!UICONTROL Drill Ins] (Approfondimenti) delle **[!UICONTROL Properties]** della tessera. Puoi aggiungere più dimensioni a ogni tessera.

![Aggiunta di dimensioni](assets/layer_dimensions.png)

## Applicare i segmenti {#segments}

Per applicare segmenti alle singole tessere, trascina un segmento dal pannello di sinistra e rilascialo direttamente sulla tessera.

Se vuoi applicare il segmento a tutte le tessere della scorecard, rilascia la tessera sopra la scorecard. Oppure, puoi anche applicare i segmenti selezionandoli nel menu del filtro sotto gli intervalli di date. Puoi [configurare e applicare filtri per le scorecard](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=it) nello stesso modo che utilizzeresti in Adobe Analytics Workspace.

![Creare segmenti per il filtro](assets/segment_ui.png)

## Aggiungere intervalli di date {#dates}

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

## Applicare visualizzazioni {#viz}

Guarda un video sulle visualizzazioni delle scorecard per dispositivi mobili:

>[!VIDEO](https://video.tv.adobe.com/v/337570/?quality=12&learn=on)

Le dashboard di Analytics offrono quattro visualizzazioni che consentono di ottenere informazioni approfondite su elementi e metriche delle dimensioni. Applica una visualizzazione diversa modificando la sezione [!UICONTROL chart type] delle proprietà di una tessera [!UICONTROL Properties]. Seleziona la tessera destra e modifica il tipo di grafico.

![Proprietà delle tessere](assets/properties.png)

Oppure, fai clic sull’icona [!UICONTROL Visualizations] nella barra a sinistra, quindi trascina la visualizzazione a destra sulla tessera:

![Visualizzazioni](assets/vizs.png)

### [!UICONTROL Summary Number]

Utilizza la visualizzazione Numero di riepilogo per evidenziare un numero elevato importante in un progetto.

![Numero di riepilogo](assets/summary-number.png)

### [!UICONTROL Donut]

Questa visualizzazione è simile al grafico a torta e presenta i dati come parti o segmenti di un intero. Utilizzare un grafico ad anello per confrontare le percentuali di un totale. Ad esempio, per capire quale piattaforma di annunci ha contribuito al numero totale di visitatori univoci:

![Visualizzazione ad anello](assets/donut-viz.png)

### [!UICONTROL Line]

La visualizzazione delle linee rappresenta le metriche con linee che mostrano come cambiano i valori nel tempo. Un grafico a linee mostra le dimensioni nel tempo, ma funziona con qualsiasi visualizzazione. In questo esempio stai visualizzando la dimensione della categoria di prodotto.

![Visualizzazione delle linee](assets/line.png)


### [!UICONTROL Horizontal Bar]

Questa visualizzazione mostra barre orizzontali che rappresentano diversi valori per una o più metriche. Ad esempio, per vedere facilmente quali sono i tuoi prodotti migliori, utilizza la [!UICONTROL Horizontal Bar] per la visualizzazione desiderata.

![barra orizzontale](assets/horizontal.png)

### Rimuovere elementi di dimensione [!UICONTROL Unspecified]

Se desideri rimuovere dai dati gli elementi di dimensione [!UICONTROL Unspecified], effettua le seguenti operazioni:

1. Seleziona la tessera corretta.
1. Nella barra a destra, sotto **[!UICONTROL Drill ins]**, seleziona la freccia destra accanto all’elemento di dimensione di cui vuoi rimuovere gli elementi **[!UICONTROL Unspecified]**.

   ![non specificato](assets/unspecified.png)

1. Fai clic sull’icona accanto a **[!UICONTROL Unspecified]** per rimuovere i dati non specificati dalle attività di reporting. È inoltre possibile rimuovere qualsiasi altro elemento di dimensione.

## Visualizzare e configurare le proprietà delle tessere {#tiles}

Quando fai clic su una tessera nel Creatore di scorecard, la barra di destra mostra le proprietà e le caratteristiche associate a quella tessera. In questa barra puoi assegnare un nuovo **[!UICONTROL Title]** alla tessera e, in alternativa, configurarla specificando i componenti invece di trascinarli dalla barra di sinistra.

![Tessera delle proprietà](assets/properties_tile.png)

Quando si fa clic su una tessera, un pop-up dinamico mostra la vista di approfondimento (Raggruppamento) che verrà presentata all’utente manageriale nell’app. Se non è stata applicata alcuna dimensione alla tessera, la dimensione di raggruppamento sarà **ore** o **giorni**, a seconda dell’intervallo date predefinito.

I raggruppamenti consentono di perfezionare l’analisi suddividendo letteralmente metriche e dimensioni per altre metriche e dimensioni, come in questo esempio di vendita al dettaglio:

* Metrica Visitatori univoci suddivisa per piattaforma di annunci (AMO ID)
* Visite suddivise per categoria di prodotto (al dettaglio)
* Entrate totali suddivise per nome prodotto

![Vista_Raggruppamento](assets/break_view.png)

Ogni dimensione aggiunta alla tessera viene visualizzata in un elenco a discesa nella vista dettagliata dell’app. L’utente esecutivo può quindi scegliere tra le opzioni elencate nell’elenco a discesa.

## Rimuovere i componenti {#remove}

Allo stesso modo, per rimuovere un componente applicato all’intera scorecard, fai clic sulla scorecard al di fuori delle tessere, quindi fai clic sulla **x** che compare quando passi il mouse sul componente, come mostrato di seguito per il segmento **Nuovo visitatore**:

![Rimuovere_componenti](assets/new_remove.png)

## Scheda di valutazione anteprima {#preview}

Puoi visualizzare in anteprima l’aspetto e il funzionamento della scorecard una volta pubblicata nell’app delle dashboard di Analytics.

1. Fai clic su **[!UICONTROL Preview]** nell&#39;angolo in alto a destra dello schermo.

   ![Anteprima_scorecard](assets/preview.png)

1. Per visualizzare l’aspetto della scorecard su diversi dispositivi, seleziona un dispositivo dal [!UICONTROL Device preview] menu a discesa.

   ![Device_preview](assets/device-preview.png)

1. Per interagire con l’anteprima, puoi:

   * Fare clic con il pulsante sinistro del mouse per simulare il tocco sullo schermo del telefono.

   * Utilizzare la funzione di scorrimento del computer per simulare lo scorrimento dello schermo del telefono con il dito.

   * Fare clic e tenere premuto per simulare premendo e tenendo premuto il dito sullo schermo del telefono. Questa funzione è utile per interagire con le visualizzazioni nella vista dettagliata.

## Assegnare un nome a una scorecard {#name}

Per dare un nome alla scorecard, fai clic sullo spazio del nome in alto a sinistra dello schermo e digita il nuovo nome.

![Assegnare_un_nome_alle_scorecard](assets/new_name.png)

## Condividere una scorecard {#share}

Per condividere la scorecard con un utente esecutivo:

1. Fai clic sul menu **[!UICONTROL Share]** e seleziona **[!UICONTROL Share scorecard]**.

1. Nel modulo **[!UICONTROL Share mobile scorecard]**, compila i campi:

   * Inserimento del nome della scorecard
   * Inserimento di una descrizione della scorecard
   * Aggiungendo tag rilevanti
   * Specificare i destinatari della scorecard

1. Fai clic su **[!UICONTROL Share]**.

![Condividere_scorecard](assets/new_share.png)

Dopo che hai condiviso una scorecard, i destinatari possono accedervi sulle loro dashboard di Analytics. Se apporti successive modifiche alla scorecard nel Creatore di scorecard, queste verranno automaticamente aggiornate nella scorecard condivisa. Gli utenti esecutivi vedranno poi i cambiamenti dopo aver aggiornato la scorecard nella loro app.

Se aggiorni la scorecard aggiungendo nuovi componenti, ti consigliamo di condividerla nuovamente (e di selezionare l’opzione **[!UICONTROL Share embedded components]**) per assicurarti che gli utenti manageriali abbiano accesso a queste modifiche.
