---
description: Scopri come gestire gli avvisi.
title: Gestire gli avvisi
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 24dd47e995523aedba1385ee8882af5e11c7b128
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 19%

---


# Gestire gli avvisi


È possibile filtrare, assegnare tag, eliminare, rinominare, copiare, abilitare, disabilitare, rinnovare ed esportare gli avvisi da un&#39;interfaccia di gestione centrale di [!UICONTROL Alerts]. Per gestire gli avvisi:

* Seleziona **[!UICONTROL Components]** nell’interfaccia principale, quindi seleziona **[!UICONTROL Alerts]**.

La gestione avvisi è strutturata come la [gestione segmenti](/help/components/segmentation/segmentation-workflow/seg-manage.md) e la [gestione metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md).


## Gestione avvisi

Gestione avvisi dispone dei seguenti elementi dell’interfaccia:

![Interfaccia filtri](assets/alerts-manager.png)

### Elenco avvisi

Nell&#39;elenco degli avvisi ➊ vengono visualizzati tutti gli avvisi di cui sei proprietario, quelli con ambito di tutti i tuoi progetti e quelli condivisi con te. L’elenco dispone delle seguenti colonne:

| Colonna | Descrizione |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleziona questa opzione per favorire ![Star](/help/assets/icons/Star.svg) o per non favorire ![StarOutline](/help/assets/icons/StarOutline.svg) un avviso. |
| **[!UICONTROL Title and description]** | Per modificare l&#39;avviso, selezionare il collegamento del titolo, che apre il generatore di [avvisi](alert-builder.md#alert-builder). |
| **[!UICONTROL Type]** | Il tipo di avviso: un avviso di dati di Adobe Analytics o un avviso di utilizzo di una chiamata al server. |
| **[!UICONTROL Enabled]** | L&#39;avviso è attivato o disattivato. |
| **[!UICONTROL Report suite]** | Le suite di rapporti a cui si applica questo avviso. |
| **[!UICONTROL Owner]** | Proprietario dell&#39;avviso. In qualità di non amministratore, puoi visualizzare solo gli avvisi di tua proprietà o quelli condivisi con te. |
| **[!UICONTROL Tags]** | Tag per l&#39;avviso. |
| **[!UICONTROL Expiration Date]** | La data e l’ora in cui l’avviso è impostato per scadere. |
| **[!UICONTROL Date modified]** | Data e ora dell’ultima modifica apportata all’avviso. |

<!-- 

When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul>

-->

Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per specificare quali colonne vuoi visualizzare.

### Barra delle azioni

È possibile eseguire azioni sugli avvisi utilizzando la barra delle azioni ➋. La barra delle azioni contiene le azioni seguenti:

| Icona | Azione | Descrizione |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Aggiungere un altro avviso utilizzando [Generatore di avvisi](alert-builder.md#alert-builder). |
| ![Ricerca](/help/assets/icons/Search.svg) | [!UICONTROL *Ricerca per titolo*] | Se nell&#39;elenco non è selezionato alcun avviso, cercare gli avvisi utilizzando questo campo di ricerca. |
| ![Etichetta](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Assegna tag agli avvisi selezionati. Nella finestra di dialogo **[!UICONTROL Tag Alert]**, seleziona o deseleziona i tag per gli avvisi selezionati. Selezionare **[!UICONTROL Save]** per salvare i tag per gli avvisi selezionati. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina gli avvisi selezionati. Viene richiesta una conferma. |
| ![Modifica](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Rinominare un singolo avviso selezionato. Se questa opzione è selezionata, è possibile rinominare l&#39;avviso in linea. |
| ![Copia](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Copia l’avviso selezionato. Vengono creati nuovi avvisi con lo stesso nome e suffisso `(Copy)`. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Enable]** o **[!UICONTROL Disable]** | Attiva o disattiva gli avvisi selezionati. |
| ![Aggiorna](/help/assets/icons/Refresh.svg) | **[!UICONTROL Renew]** | Rinnova la data di scadenza dell’avviso. La data di scadenza si estende per 1 anno dal giorno in cui è stata selezionata questa opzione, indipendentemente dalla data di scadenza originale. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Esporta gli avvisi in un file `Alerts List.csv`. |


### Barra dei filtri attivi

La barra dei filtri ➌ mostra i filtri attivi applicati dal pannello dei filtri all&#39;elenco degli avvisi (se presenti). Puoi rimuovere rapidamente un filtro utilizzando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se sono specificati più filtri, puoi rimuoverli tutti utilizzando **[!UICONTROL Remove all]**.


### Pannello dei filtri

Puoi filtrare l&#39;elenco degli avvisi utilizzando il ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** pannello sinistro ➍. Nel pannello dei filtri viene visualizzato il tipo di filtro e il numero di avvisi che rispettano il filtro specifico.


1. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per aprire il pannello dei Filtri. Se hai bisogno di più spazio per l&#39;elenco Avvisi, puoi selezionare ancora ![Filtro](/help/assets/icons/Filter.svg) per chiudere il pannello.
1. Seleziona i filtri da una qualsiasi delle sezioni disponibili.


#### Sezione filtro tag

{{tagfiltersection}}


#### Sezione filtro suite di rapporti

{{reportsuitefiltersection}}


#### Sezione filtro Proprietari

{{ownerfiltersection}}


#### Sezione filtro di stato abilitato

{{enabledstatusfiltersection}}


#### Sezione tipo di filtro

{{typefiltersection}}


#### Sezione filtro Altri filtri

{{otherfiltersfiltersection}}



## Modifica avvisi

È possibile modificare un avviso

* Nell&#39;elenco [[!UICONTROL Alert]](#alerts-list), selezionare il titolo dell&#39;avviso.

Per modificare l&#39;avviso, utilizzare [Generatore di avvisi](alert-builder.md#alert-builder).

## Risolvere i problemi relativi a un avviso

Durante la risoluzione di un problema relativo a un avviso, fornisci il numero JID (Job Instance ID) al supporto Adobe. Il numero JID si trova nella parte inferiore della notifica e-mail di avviso ricevuta.

![E-mail avviso](assets/alerts-email.PNG)


<!--

# Manage alerts

You can manage existing alerts in the Alerts manager. You can perform various management tasks on alerts, such as tagging, renaming, deleting, and more.

The Alerts manager is structured very much like the [Segment Manager](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=it) and the [Calculated Metric Manager](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=it).

 ![](assets/alert-manager.png)

## Create alerts

To create alerts from the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select [!UICONTROL **Add**] (or [!UICONTROL **Create new alert**] if you don't have any existing alerts).

1. Select the alert type that corresponds to the alert that you want to create:

   * [!UICONTROL **Analytics data alert**]: An alert to notify you when abnormal events occur in your data. 

     If you select this option, continue with [Create alerts](/help/components/c-alerts/alert-builder.md) for more details about creating alerts.

   * [!UICONTROL **Server call usage alert**]: An alert to notify you of the risk or occurrence of an overage in your server call consumption and commitment data. 

     If you select this option, continue with [Server call usage alerts](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >You must be an Analytics administrator or a user with the Server call usage permission in order to have access to server call usage. 

## Manage existing alerts

You can perform various actions on existing alerts, such as tagging, renaming, deleting, and so forth.

To manage existing alerts in the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select one or more alerts that you want to manage.

   ![](assets/alert-manager-tasks.png)

1. In the action bar, select any of the following options:

   | Action | Function | 
   |---------|----------|
   | [!UICONTROL **Tag**] | Apply a tag to an alert. This helps you to organize alerts for ease of use. | 
   | [!UICONTROL **Delete**] | Deletes the alert. | 
   | [!UICONTROL **Rename**] | Renames the alert. |
   | [!UICONTROL **Approve**] | Mark the alert as Approved. |
   | [!UICONTROL **Copy**] | Creates a copy (duplicate) of the alert. |
   | [!UICONTROL **Disable**] | Disables an alert that is currently enabled. |
   | [!UICONTROL **Enable**] | Enables an alert that is currently disabled. |
   | [!UICONTROL **Renew**] | Renews the alert expiration date. This extends the  expiration date to be 1 year from the day you selected this option, regardless of the original expiration date. |
   | [!UICONTROL **Export to CSV**] | Exports the alert to a .CSV file. |

## Edit an alert

To edit an existing alert:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select the alert name in the [!UICONTROL **Title and description**] column.

1. Edit the alert as desired. 

   Following are some of the things you can do when editing an alert:

   * Add alerts to other report suites
   * Add or modify the description
   * Modify the time granularity
   * Modify the recipients 
   * Modify the expiration date
   * Modify the metrics and filters

1. Select [!UICONTROL **Save**].

## Configure columns 

You can configure the information displayed for each alert in the Alerts manager by configuring the columns that are displayed.

To configure the visible columns in the Alerts manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Alerts]**. 

1. In the Alert manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Alerts manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Title and description | These values are provided in the Alert builder. To edit the title and description, select the title link to open the Alert builder.  |
   | Favorites  | Displays star icons next to each alert, allowing you to mark alerts as favorites. |
   | Type | Shows whether the alert is an Analytics data alert or a Server call usage alert. |
   | Enabled | Shows whether the alert is currently enabled or disabled. | 
   | Report suite | Indicates in which report suite the alert was last saved.  |
   | Owner | Indicates who owns the alert. As a non-admin, you can see only alerts you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the alert, either by you or by people who shared the alert with you.  |
   | Expiration date | Shows the date and time when the alert is set to expire. |
   | Date modified | Indicates the date when the alert was last modified.  |

   {style="table-layout:auto"}
   
   
    When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> 
   
-->

