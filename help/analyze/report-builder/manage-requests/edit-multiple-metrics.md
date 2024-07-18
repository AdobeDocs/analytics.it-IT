---
description: Scopri come aggiungere, rimuovere o sostituire le metriche in una richiesta preesistente o in un gruppo di richieste.
title: Come modificare le metriche in più richieste
feature: Report Builder
role: User, Admin
exl-id: e537b67a-aa07-4acd-a476-7497426e2f7d
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 23%

---

# Modificare le metriche in più richieste

Aggiungere, rimuovere o sostituire metriche in una richiesta preesistente o in un gruppo di richieste.

## Aggiungere metriche {#section_3FBDA9668039404895059618D70FCBCD}

Quando aggiungi metriche, prendi in considerazione le seguenti linee guida:

* Le metriche possono essere aggiunte solo alle richieste di layout pivot.
Se alcune delle richieste selezionate sono Layout personalizzati, non è possibile aggiungere metriche. Se il layout è personalizzato, il Report Builder non sa dove collocare la nuova metrica nel foglio di calcolo.
* Se si selezionano solo richieste di layout personalizzato, l&#39;opzione **[!UICONTROL Add Metrics]** non è disponibile.
* L’aggiunta di metriche aumenta le dimensioni di una richiesta e potrebbe causarne la sovrapposizione con un’altra richiesta. Assicurati che la richiesta disponga di spazio sufficiente intorno a essa per consentire l’aggiunta di metriche.
* Se la metrica aggiunta è già presente in una delle richieste selezionate, non verrà aggiunta a tale richiesta.

Per aggiungere una o più metriche

1. Seleziona una o più richieste in Excel e fai clic con il pulsante destro del mouse per selezionare **[!UICONTROL Edit Metrics]**. (Oppure fai clic su **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > `<choose metric>` > **[!UICONTROL Edit Group]** per selezionare il gruppo di richieste da modificare.)
1. Seleziona **[!UICONTROL Add Metric(s)]**e seleziona le metriche da aggiungere.

   ![Schermata che mostra l&#39;opzione Modifica richiesta, Aggiungi metriche selezionata.](assets/add_metric.png)

1. Aggiorna la richiesta per visualizzare i dati effettivi. I dati offline vengono visualizzati fino all’aggiornamento dei dati.

## Sostituire le metriche

Quando sostituisci le metriche, considera le seguenti linee guida:

* Sono consentite solo sostituzioni 1:1. 1:molti o molti:1 non sono consentiti.
* Se la metrica selezionata non è presente in una delle richieste selezionate, la richiesta viene lasciata invariata.
* La nuova metrica viene posizionata nella stessa posizione della metrica sostituita.

   * **In un layout pivot**, se una richiesta di layout pivot restituisce data, visita, visitatori, univoci giornalieri e *visitatori* è sostituito da *ricavi*, il layout della richiesta aggiornato sarà: data, visita, ricavi e univoci giornalieri.
   * **In un layout personalizzato**, se la metrica *visitatori* è stata generata nella cella F11, il layout della richiesta aggiornato mostrerà *ricavi* nella stessa cella F11.

* Se alla metrica sostituita è stata applicata un’operazione (media, testo pre-scritto, testo scritto, micrografico), queste operazioni verranno applicate anche alla nuova metrica.

Per sostituire una metrica

1. Seleziona una o più richieste in Excel e fai clic con il pulsante destro del mouse per selezionare **[!UICONTROL Edit Metrics]**. In alternativa, è possibile fare clic su **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > **`<choose metric>`** > **[!UICONTROL Edit Group]** per selezionare il gruppo di richieste da modificare.

1. Seleziona **[!UICONTROL Replace Metric]**.

   ![Schermata della schermata Modifica gruppo con la metrica Sostituisci selezionata.](assets/replace_metric.png)

1. Seleziona la metrica da sostituire e la metrica di sostituzione.
1. Aggiorna la richiesta. I dati offline vengono visualizzati fino all’aggiornamento dei dati.

## Rimuovere le metriche {#section_D3CD5BAC7670416593B633B2B8423C60}

Quando rimuovi le metriche, considera le seguenti linee guida:

* Se una delle metriche selezionate per la rimozione non è presente in una delle richieste selezionate, la richiesta viene lasciata invariata.
* In un layout pivot, la rimozione di una metrica determina lo spostamento del layout per le metriche che si trovano dopo la metrica rimossa. Ad esempio, se una richiesta di layout pivot restituisce data, visite, visitatori e univoci giornalieri e si rimuovono *visite*, il layout aggiornato della richiesta mostrerà: data, visitatori e univoci giornalieri.

Per rimuovere le metriche

1. Seleziona una o più richieste in Excel e fai clic con il pulsante destro del mouse per selezionare **[!UICONTROL Edit Metrics]**. In alternativa, fare clic su **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > **`<choose metric>`** > **[!UICONTROL Edit Group]** per selezionare il gruppo di richieste da modificare.

1. Seleziona **[!UICONTROL Remove Metric(s)]**.

   ![Schermata che mostra l&#39;opzione Modifica gruppo e Rimuovi metriche selezionata.](assets/remove_metric.png)

1. Seleziona una o più metriche da rimuovere dalla richiesta.
1. Aggiorna la richiesta. Fino a quando non aggiorni, vedrai i dati offline.
