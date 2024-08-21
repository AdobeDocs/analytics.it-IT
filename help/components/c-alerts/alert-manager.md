---
description: Gestire gli avvisi.
title: Panoramica di Gestione avvisi
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 49324ef7fd45adeef2c31167d0444a7e67041d6d
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 23%

---

# Gestione avvisi

La gestione avvisi è strutturata in modo analogo alla [gestione segmenti](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=it) e alla [gestione metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=it).

![](assets/alert-manager.png)

## Accedere alla gestione degli avvisi

1. In Adobe Analytics, seleziona [!UICONTROL **Componenti**] > [!UICONTROL **Avvisi**].

## Azioni disponibili in Gestione avvisi

In Gestione avvisi puoi effettuare le seguenti operazioni:

* Accedere al generatore di avvisi facendo clic su **[!UICONTROL + Add]** (Crea nuovo avviso).
* Assegnare tag agli avvisi per agevolarne l’organizzazione
* Eliminare gli avvisi
* Rinominare gli avvisi
* Approvare gli avvisi
* Copiare gli avvisi
* Abilitare/disabilitare gli avvisi
* **Rinnovare** la data di scadenza di un avviso. Quando sono selezionati uno o più avvisi, è possibile rinnovarli facendo clic su **[!UICONTROL Renew]**. Questa funzione sposta le rispettive date di scadenza a 1 anno dal giorno in cui **[!UICONTROL Renew]** è stato fatto clic su, indipendentemente dalla data di scadenza originale.
* Esportare un avviso come file .CSV
* Modificare gli avvisi facendo doppio clic sul titolo
* Cercare gli avvisi
* Aggiungere degli avvisi ad altre suite per rapporti
* Specificare o cambiare il proprietario di un avviso
* Aggiungere altri filtri
* Definire la **data di scadenza** di un avviso

## Configurare le colonne

È possibile configurare le informazioni visualizzate per ogni avviso in Gestione avvisi configurando le colonne visualizzate.

Per configurare le colonne visibili in Gestione avvisi:

1. In Adobe Analytics, selezionare la scheda **[!UICONTROL Components]**, quindi selezionare **[!UICONTROL Alerts]**.

1. In Gestione avvisi, selezionare l&#39;icona **Personalizza colonne** ![Personalizza colonne icona](assets/customize-columns-icon.png), quindi selezionare le colonne che si desidera visualizzare in Gestione avvisi.

   Sono disponibili le seguenti colonne:

   | Titolo colonna | Descrizione |
   |---|---|
   | Titolo e descrizione | Questi valori vengono forniti nel generatore di avvisi. Per modificare il titolo e la descrizione, seleziona il collegamento del titolo per aprire il generatore di avvisi. |
   | Preferiti | Visualizza icone a forma di stella accanto a ogni avviso, che consentono di contrassegnare gli avvisi come preferiti. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Tipo | Mostra se l’avviso è un avviso di dati di Analytics o un avviso di utilizzo di chiamate al server. |
   | Abilitata | Indica se l&#39;avviso è attualmente abilitato o disabilitato. |
   | Suite di rapporti | Indica in quale suite di rapporti è stato salvato l’ultimo avviso. |
   | Proprietario | Indica il proprietario dell&#39;avviso. In qualità di non amministratore, puoi visualizzare solo gli avvisi di tua proprietà o quelli che sono stati condivisi con te. |
   | Tag | Mostra i tag applicati all&#39;avviso, da te o da altri utenti che lo hanno condiviso con te. |
   | Data di scadenza | Mostra la data e l’ora in cui l’avviso è impostato per scadere. |
   | Data di modifica | Indica la data dell’ultima modifica apportata all’avviso. |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->


