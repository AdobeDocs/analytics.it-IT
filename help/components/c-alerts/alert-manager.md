---
description: Gestire gli avvisi.
title: Panoramica di Gestione avvisi
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 637f498c8abee0f3c83780bccd0447f2e3a804e3
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 24%

---

# Gestione avvisi

La gestione degli avvisi è strutturata in modo analogo alla [Gestore segmenti](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=it) e [Gestione metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=it).

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
* **Rinnovare** la data di scadenza di un avviso. Quando sono selezionati uno o più avvisi, è possibile rinnovarli facendo clic su **[!UICONTROL Renew]**.Questa funzione sposta le rispettive date di scadenza a 1 anno dal giorno **[!UICONTROL Renew]** è stato cliccato, indipendentemente dalla data di scadenza originale.
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

1. In Adobe Analytics, seleziona la **[!UICONTROL Components]** , quindi seleziona **[!UICONTROL Alerts]**.

1. In Gestione avvisi, seleziona la **Personalizza colonne** icona ![Icona Personalizza colonne](assets/customize-columns-icon.png), quindi selezionare le colonne che si desidera visualizzare in Gestione avvisi.

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
   | Ultimo utilizzo | **Nota:** Questa funzionalità si trova nella fase di test limitato del rilascio e potrebbe non essere ancora disponibile nell’ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sulla procedura di rilascio del Customer Journey Analytics, consulta [Rilasci di funzioni del Customer Journey Analytics](/help/release-notes/releases.md).<p>Mostra la data dell’ultimo utilizzo dell’avviso.</p> <p>Queste informazioni possono essere utili per determinare se un avviso è utile per gli utenti dell’organizzazione o se deve essere eliminato.</p><p>Queste informazioni non includono l’utilizzo da API, Report Builder o Data Warehouse.</p> |

   {style="table-layout:auto"}
