---
title: Creare E Modificare I Set Di Classificazione
description: Scopri come creare e modificare i set di classificazione in Adobe Analytics, inclusi i tipi di classificazione principali e di ricerca, gli abbonamenti e le notifiche di processo.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 9feefd318d5239812f62afd727836e8aa203a4b2
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 4%

---

# Creare e modificare i set di classificazione

Hai [creato](#create-a-classification-set) e [modificato](#edit-a-classification-set) i set di classificazione dal gestore dei set di classificazione.

## Creare un set di classificazione

Per creare un set di classificazione:

1. Seleziona **[!UICONTROL Components]** dalla barra dei menu superiore di Adobe Analytics, quindi seleziona **[!UICONTROL Classification sets]**.
1. In **[!UICONTROL Classification sets]**, selezionare la scheda **[!UICONTROL Classification sets]**.
1. Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]**.
1. Nella finestra di dialogo **[!UICONTROL Add New Classification Set]** (Crea elemento dati):

   ![Set di classificazione - Aggiungi nuovo set di classificazione](assets/classifications-sets-new.png)

   1. Immetti **[!UICONTROL Name]**. Ad esempio: `Classification Set Example`.
   1. Immetti **[!UICONTROL Description (optional)]**. Ad esempio: `Example classification set`.
   1. Seleziona **[!UICONTROL Type]** del set di classificazione. I tipi possibili sono:
      * **[!UICONTROL Primary]**. Un set di classificazione principale si applica alle dimensioni raccolte in Adobe Analytics. Le classificazioni primarie consentono di raggruppare (classificare) i valori delle dimensioni granulari in livelli di dati più significativi. Ad esempio, potrebbe essere utile raggruppare le parole chiave di ricerca interna in categorie di ricerca interna per comprendere i temi nei dati di ricerca. Oppure classifica le SKU dei prodotti per colore o categoria.
      * **[!UICONTROL Lookup]**. Una tabella di ricerca è una classificazione di una classificazione primaria, comunemente definita come figlio o sottoclassificazioni. Una ricerca è costituita da metadati relativi a un valore di classificazione, anziché alla dimensione originale. Ad esempio, una dimensione *Prodotto* potrebbe avere una classificazione primaria *Codice colore*. Una tabella di ricerca di *Nome colore* può quindi essere allegata al *Codice colore* per spiegare ogni codice colore.
1. Nella sezione **[!UICONTROL Job notifications]**, seleziona gli utenti a cui inviare la notifica in caso di errore o completamento dei processi del set di classificazione.
   * Per inviare una notifica agli utenti in caso di errore:
      1. Abilita **[!UICONTROL Notify on failure]**.
      1. Specificare uno o più indirizzi e-mail separati da virgole in **[!UICONTROL Failure email recipients]**.
   * Per inviare una notifica agli utenti in caso di esito positivo:
      1. Abilita **[!UICONTROL Notify on success]**.
      1. Specificare uno o più indirizzi e-mail separati da virgole in **[!UICONTROL Success email recipients]**.
1. Nella sezione **[!UICONTROL Subscriptions]**, se hai selezionato **[!UICONTROL Primary]**, immetti uno o più **[!UICONTROL Subscriptions]**.  È possibile definire più combinazioni di **[!UICONTROL Report Suite]** e **[!UICONTROL Dimension]** in un set di classificazione.

   * Selezionare ![CrossSize400](/help/assets/icons/CrossSize400.svg) per eliminare una combinazione di **[!UICONTROL Report Suite]** e **[!UICONTROL Key Dimension]**.

   Se aggiungi una combinazione di **[!UICONTROL Report Suite]** e **[!UICONTROL Key Dimension]** già esistente in un altro set di classificazione, viene visualizzato un messaggio di colore rosso.
Puoi:
   * Selezionare **[!UICONTROL Add to existing]** per aprire l&#39;altro set di classificazione e [aggiungere classificazioni allo schema](manage/schema.md) per l&#39;altro set di classificazione.
   * Cambia **[!UICONTROL Report Suite]** e **[!UICONTROL Key Dimension]** in una combinazione che non è già abbonata a un altro set di classificazione.
1. Selezionare **[!UICONTROL Save]** per salvare il set di classificazione. Selezionare **[!UICONTROL Cancel]** per annullare la definizione.

Per definire lo schema per il set di classificazione, seleziona il set di classificazione appena creato dal gestore **[!UICONTROL Classification Sets]** per [modificare il set di classificazione](#edit-a-classification-set).


## Modificare un set di classificazione

Per modificare un set di classificazione:

1. Seleziona **[!UICONTROL Components]** dalla barra dei menu superiore di Adobe Analytics, quindi seleziona **[!UICONTROL Classification sets]**.
1. In **[!UICONTROL Classification Sets]**, selezionare la scheda **[!UICONTROL Classification Sets]**.
1. Seleziona il nome del set di classificazione.
1. Nella finestra di dialogo **[!UICONTROL Classification Set: _nome set di classificazione_]**, puoi definire le [impostazioni](manage/settings.md) e lo [schema](manage/schema.md) per il set di classificazione.
1. Al termine, seleziona **[!UICONTROL Save]** per salvare le modifiche. Seleziona **[!UICONTROL Cancel]** per annullare.
