---
title: Processo di consolidamento del set di classificazione
description: Processo completo di consolidamento dei set di classificazione.
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Processo di consolidamento del set di classificazione

Utilizzare questa interfaccia per creare un consolidamento del set di classificazione dall&#39;inizio alla fine.

## Creazione

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]** > **[!UICONTROL Add]**

Durante la creazione di un consolidamento sono disponibili i seguenti campi:

* **[!UICONTROL Name]**: nome del consolidamento.
* **[!UICONTROL Notify of issues]**: elenco delimitato da virgole di indirizzi e-mail a cui vengono notificati i problemi relativi a questo consolidamento.
* **[!UICONTROL Dataset to match]**: elenco a discesa di tutti i set di classificazione.

Dopo aver selezionato un set di classificazione, viene visualizzata una tabella con due colonne:

* La colonna di destra contiene tutti i set di classificazione da consolidare. Inizia con il set di classificazione selezionato utilizzando l’elenco a discesa precedente.
* La colonna sinistra contiene tutti i set di classificazione idonei all’unione con il set di dati selezionato originariamente. **Gli schemi devono corrispondere esattamente per essere idonei al consolidamento**. Se gli schemi non corrispondono al set di classificazione selezionato, non vengono visualizzati in questa colonna sinistra.

Trascina i set di classificazione desiderati dalla colonna disponibile a sinistra alla colonna di consolidamento a destra. Dopo aver assegnato un nome al consolidamento e aver aggiunto due o più set di classificazione nella colonna di destra, fare clic su **[!UICONTROL Save & Continue]**.

## Convalida

Dopo aver creato un consolidamento, a destra viene visualizzato un elenco di set di dati di origine. Il pulsante **[!UICONTROL Validate]** verifica che ogni singolo set di classificazione sia valido per questo consolidamento. Puoi riordinare i passaggi di classificazione qui per determinare la priorità in caso di valori di classificazione non corrispondenti. **Il set di classificazione più alto dell&#39;elenco sovrascrive eventuali valori non corrispondenti in altri set di classificazione.**

## Eseguire

Una volta convalidato, il consolidamento può essere eseguito. L&#39;esecuzione di un consolidamento fornisce un rapporto di somiglianza con le seguenti colonne di tabella:

* **[!UICONTROL Dataset name]**: nome del set di classificazione.
* **[!UICONTROL Mismatch]**: percentuale di righe in cui i valori chiave non corrispondono al set di classificazione di origine. Se la percentuale di mancata corrispondenza è elevata, è possibile che i dati di classificazione siano troppo diversi. Controlla e assicurati che i set di classificazione selezionati abbiano dati di classificazione simili.
* **[!UICONTROL Absent]**: percentuale di righe in cui i valori chiave si trovavano in tale set di classificazione ma non nel set di classificazione di origine. Tutte le righe assenti vengono aggiunte al set di classificazione consolidato.

## Approvazione

Agisce come ultima chiamata prima di rimuovere i singoli set di classificazione e creare un set di classificazione consolidato. Verificare che tutto sia corretto, quindi fare clic su **[!UICONTROL Approve]**.

Una volta approvato, viene creato il set di classificazione consolidato. Lo stato è impostato su [!UICONTROL Complete] e non sono necessarie ulteriori azioni per il consolidamento.
