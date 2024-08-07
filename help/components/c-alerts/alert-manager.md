---
description: Gestire gli avvisi.
title: Panoramica di Gestione avvisi
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 9a6c2e7c2f83882f6df630f975b0c44e75a2ed7a
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 21%

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
   | Preferiti | Visualizza icone a forma di stella accanto a ogni avviso, che consentono di contrassegnare gli avvisi come preferiti. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Titolo e descrizione | Questi valori vengono forniti nel generatore di avvisi. Per modificare il titolo e la descrizione, seleziona il collegamento del titolo per aprire il generatore di avvisi. |
   | Suite di rapporti | Indica in quale suite di rapporti è stato salvato l’ultimo avviso. |
   | Proprietario | Indica il proprietario dell&#39;avviso. In qualità di non amministratore, puoi visualizzare solo gli avvisi di tua proprietà o quelli che sono stati condivisi con te. |
   | Tag | Mostra i tag applicati all&#39;avviso, da te o da altri utenti che lo hanno condiviso con te. |
   | Condiviso con | Elenca singoli utenti o gruppi (solo amministratori) o tutti coloro (solo amministratori) con cui hai condiviso l’avviso. |
   | Data di modifica | Indica la data dell’ultima modifica apportata all’avviso. |
   | Ultimo utilizzo | Mostra la data dell’ultimo utilizzo dell’avviso. <p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, prendi in considerazione quanto segue:</p><ul><li>Queste informazioni non includono l’utilizzo da API, Report Builder o Data Warehouse.</li><li>Per alcuni componenti, questa colonna potrebbe non contenere dati se il componente è stato utilizzato l’ultima volta prima di settembre 2023.</li></ul> |

   {style="table-layout:auto"}
