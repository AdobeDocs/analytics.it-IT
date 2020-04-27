---
description: La funzione Modifica metriche in più richieste consente di aggiungere, rimuovere o sostituire agevolmente le metriche in una richiesta o gruppo di richieste preesistenti.
title: Modifica metriche in più richieste
uuid: 50fba4e7-ca7d-4a5c-98a9-c9725b436e4a
translation-type: tm+mt
source-git-commit: 52cc111c0f28b099f038e4b6c69a9431fe506111

---


# Modifica metriche in più richieste

La funzione Modifica metriche in più richieste consente di aggiungere, rimuovere o sostituire agevolmente le metriche in una richiesta o gruppo di richieste preesistenti.

## Aggiunta di metriche {#section_3FBDA9668039404895059618D70FCBCD}

Nota bene

* Le metriche possono essere aggiunte solo alle richieste di layout pivot. Se alcune delle richieste selezionate sono Layout personalizzati, non è possibile aggiungere metriche. Il motivo è che Generatore di report non sa dove inserire la nuova metrica nel foglio di calcolo, poiché il layout è personalizzato.
* Di conseguenza, se avete selezionato solo richieste di layout personalizzato, l&#39; **[!UICONTROL Add Metric/s]** opzione non è disponibile.
* L&#39;aggiunta di metriche aumenterà le dimensioni di una richiesta e potrebbe causare la sovrapposizione con un&#39;altra richiesta. Accertatevi che la richiesta disponga di spazio sufficiente intorno a essa per consentire l&#39;aggiunta di metriche.
* Se la metrica aggiunta è già presente in una delle richieste selezionate, non verrà aggiunta a tale richiesta.

Per aggiungere una o più metriche:

1. Selezionate una o più richieste in Excel e fate clic con il pulsante destro del mouse per selezionarle **[!UICONTROL Edit Metrics]**. In alternativa, fate clic su **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > `<choose metric>` > **[!UICONTROL Edit Group]** per selezionare il gruppo di richieste da modificare.
1. Selezionare **[!UICONTROL Add Metric(s)]**e selezionare le metriche da aggiungere.

   ![](assets/add_metric.png)

1. Aggiorna la richiesta per visualizzare i dati effettivi. Fino all&#39;aggiornamento, i dati offline verranno visualizzati.

## Sostituire la metrica {#section_D773AAC7B30C4FBEBDB66B203C217818}

Nota bene

* Sono consentite solo sostituzioni 1:1, non 1:many o many:1.
* Se la metrica selezionata per la sostituzione non è presente in una delle richieste selezionate, la richiesta viene lasciata invariata.
* La nuova metrica verrà inserita nella stessa posizione della metrica sostituita. Ciò significa:

   * **In un layout** pivot: se una richiesta di layout pivot genera data, visita, visitatori, univoci giornalieri e &quot;visitatori&quot; viene sostituita da &quot;ricavi&quot;, il layout di richiesta aggiornato sarà: data, visita, entrate, giorno unico.
   * **In un layout** personalizzato: se la metrica &quot;visitatori&quot; è stata generata nella cella F11, il layout della richiesta aggiornata mostrerà &quot;ricavi&quot; nella stessa cella F11.

* Se alla metrica sostituita è stata applicata un&#39;operazione (testo medio, pre-disposto, testo post-pended, microcharting), queste operazioni saranno applicate anche alla nuova metrica.

Per sostituire una metrica

1. Selezionate una o più richieste in Excel e fate clic con il pulsante destro del mouse per selezionarle **[!UICONTROL Edit Metrics]**. In alternativa, fate clic su **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > **`<choose metric>`** > **[!UICONTROL Edit Group]** per selezionare il gruppo di richieste da modificare.

1. Select **[!UICONTROL Replace Metric]**.

   ![](assets/replace_metric.png)

1. Selezionare la metrica da sostituire e la metrica con cui sostituirla.
1. Aggiorna la richiesta. Fino all&#39;aggiornamento, i dati offline verranno visualizzati.

## Rimuovere le metriche {#section_D3CD5BAC7670416593B633B2B8423C60}

Nota bene

* Se una delle metriche selezionate per la rimozione non è presente in una delle richieste selezionate, la richiesta rimane invariata.
* In un layout pivot, la rimozione di una metrica determina lo spostamento del layout per le metriche che si trovano dopo la metrica rimossa.

   **Esempio**: se una richiesta di layout pivot genera data, visite, visitatori, univoci giornalieri e rimuovete &quot;visite&quot;, il layout aggiornato della richiesta mostrerà: data, visitatori, univoci giornalieri.

Per rimuovere le metriche:

1. Selezionate una o più richieste in Excel e fate clic con il pulsante destro del mouse per selezionarle **[!UICONTROL Edit Metrics]**. In alternativa, fate clic su **[!UICONTROL Manage]** > **[!UICONTROL Edit Multiple]** > **`<choose metric>`** > **[!UICONTROL Edit Group]** per selezionare il gruppo di richieste da modificare.

1. Select **[!UICONTROL Remove Metric(s)]**.

   ![](assets/remove_metric.png)

1. Selezionate una o più metriche da rimuovere dalla richiesta.
1. Aggiorna la richiesta. Fino all&#39;aggiornamento, i dati offline verranno visualizzati.

