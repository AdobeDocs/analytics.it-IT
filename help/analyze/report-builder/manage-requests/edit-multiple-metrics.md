---
description: La funzione Modifica metriche in più richieste consente di aggiungere, rimuovere o sostituire agevolmente le metriche in una richiesta o gruppo di richieste preesistenti.
seo-description: La funzione Modifica metriche in più richieste consente di aggiungere, rimuovere o sostituire agevolmente le metriche in una richiesta o gruppo di richieste preesistenti.
seo-title: Modificare le metriche su più richieste
title: Modificare le metriche su più richieste
uuid: 50 fba 4 e 7-ca 7 d -4 a 5 c -98 a 9-c 9725 b 436 e 4 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Modificare le metriche su più richieste

La funzione Modifica metriche in più richieste consente di aggiungere, rimuovere o sostituire agevolmente le metriche in una richiesta o gruppo di richieste preesistenti.

## Add metrics {#section_3FBDA9668039404895059618D70FCBCD}

Aspetti da considerare:

* Le metriche possono essere aggiunte solo alle richieste di layout pivot. Se alcune delle richieste selezionate sono Layout personalizzati, non è possibile aggiungere metriche. Il motivo sta nel fatto che Generatore di report non sa dove inserire la nuova metrica nel foglio di calcolo, poiché il layout viene personalizzato.
* Accordingly, if you have selected only Custom Layout requests, the **[!UICONTROL Add Metric/s]** option is not available.
* L'aggiunta di metriche/s aumenterà la dimensione di una richiesta e può causare la sovrapposizione con un'altra richiesta. Assicuratevi che la richiesta disponga di spazio sufficiente intorno ad essa per consentire l'aggiunta di metriche.
* Se la metrica aggiunta è già presente in una delle richieste selezionate, non verrà aggiunta a tale richiesta.

Per aggiungere una o più metriche:

1. Select one or more requests in Excel and right-click to select **[!UICONTROL Edit Metrics]**. (Or, click **[!UICONTROL Manage]** &gt; **[!UICONTROL Edit Multiple]** &gt; **[!UICONTROL[choose metric]]** &gt; **[!UICONTROL Edit Group]** **** to select the group of requests to modify.)

1. Select **[!UICONTROL Add Metric(s)]**and select the metrics to add.

   ![](assets/add_metric.png)

1. Aggiornate la richiesta per visualizzare dati effettivi. Fino alla visualizzazione aggiornata, verranno visualizzati dati offline.

## Replace metric {#section_D773AAC7B30C4FBEBDB66B203C217818}

Aspetti da considerare:

* Sono consentite solo le sostituzioni 1:1, non 1: molti o molti: 1.
* Se la metrica selezionata per la sostituzione non è presente in una delle richieste selezionate, questa richiesta rimane invariata.
* La nuova metrica verrà inserita nella stessa posizione della metrica sostituita. Ciò significa:

   * **In un layout pivot**: se una richiesta di layout pivot genera data, visita, visitatori, univoci giornalieri e "visitatori" viene sostituita da "entrate", il layout aggiornato della richiesta sarà: data, visita, entrate, univoche giornaliere.
   * **In un layout personalizzato**: se la metrica «visitatori» veniva generata nella cella F 11, il layout di richiesta aggiornato mostrerà «entrate» nella stessa cella F 11.

* Se la metrica sostituita è stata applicata ad essa (testo medio, testo preregistrato, testo con post-pended, micrografia), queste operazioni saranno applicate anche alla nuova metrica.

Per sostituire una metrica

1. Select one or more requests in Excel and right-click to select **[!UICONTROL Edit Metrics]**. (Or, click **[!UICONTROL Manage]** &gt; **[!UICONTROL Edit Multiple]** &gt; **[!UICONTROL[choose metric]]** &gt; **[!UICONTROL Edit Group]** **** to select the group of requests to modify.)

1. Select **[!UICONTROL Replace Metric]**.

   ![](assets/replace_metric.png)

1. Seleziona la metrica da sostituire e la metrica con cui sostituirlo.
1. Aggiornate la richiesta. Fino alla visualizzazione aggiornata, verranno visualizzati dati offline.

## Remove metrics {#section_D3CD5BAC7670416593B633B2B8423C60}

Aspetti da considerare:

* Se una delle metriche selezionate da rimuovere non è presente in una delle richieste selezionate, questa richiesta rimane invariata.
* In un layout pivot, la rimozione di una metrica causa lo spostamento del layout per le metriche che si trovano dopo la metrica rimossa.

   **Esempio**: se una richiesta di layout pivot genera date, visite, visitatori, univoci giornalieri e rimuovi "visite", viene visualizzato il layout aggiornato della richiesta: data, visitatori, univoci giornalieri.

Per rimuovere le metriche:

1. Select one or more requests in Excel and right-click to select **[!UICONTROL Edit Metrics]**. (Or, click **[!UICONTROL Manage]** &gt; **[!UICONTROL Edit Multiple]** &gt; **[!UICONTROL[choose metric]]** &gt; **[!UICONTROL Edit Group]** **** to select the group of requests to modify.)

1. Select **[!UICONTROL Remove Metric(s)]**.

   ![](assets/remove_metric.png)

1. Selezionate una o più metriche da rimuovere dalla richiesta.
1. Aggiornate la richiesta. Fino alla visualizzazione aggiornata, verranno visualizzati dati offline.

