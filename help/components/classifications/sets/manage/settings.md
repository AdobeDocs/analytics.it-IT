---
title: Impostazioni set di classificazione
description: Scopri come modificare il nome, la descrizione, i tag, le notifiche di processo e gli abbonamenti di un set di classificazione esistente in Adobe Analytics.
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
feature: Classifications
TQID: https://experienceleague.adobe.com/D-6P27NSFWF5tHze-wopbkHrDMpMUQWA-zlEbZbzSzk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 211
ht-degree: 3%

---

# Impostazioni del set di classificazione

Puoi modificare le impostazioni di un set di classificazione, tra cui nome, descrizione, chi inviare la notifica e gli abbonamenti.

Per modificare le impostazioni per un set di classificazione:

1. Seleziona **[!UICONTROL Components]** dalla barra dei menu superiore di Adobe Analytics, quindi seleziona **[!UICONTROL Classification sets]**.
1. In **[!UICONTROL Classification Sets]**, selezionare la scheda **[!UICONTROL Classification sets]**.
1. Nel gestore **[!UICONTROL Classification sets]**, selezionare il set di classificazione per il quale si desidera modificare lo schema.
1. Nella finestra di dialogo **[!UICONTROL Classification Set: _set di classificazione_]**, seleziona la scheda **[!UICONTROL Settings]** per modificare le impostazioni:

   ![Set di classificazione - impostazioni](assets/classification-sets-settings.png)

   1. Modifica **[!UICONTROL Name]**.
   1. Modifica un **[!UICONTROL Description (optional)]**.
   1. Aggiungi uno o più **[!UICONTROL Tags (optional)]** al set di classificazione. Selezionare un tag esistente dal menu a discesa **[!UICONTROL Tags]** oppure immettere un nuovo tag. Utilizza ![CrossSize100](/help/assets/icons/CrossSize100.svg) per rimuovere un tag.
   1. Nella sezione **[!UICONTROL Job notifications]**, seleziona gli utenti a cui inviare la notifica in caso di errore o completamento dei processi del set di classificazione.
      * Per inviare una notifica agli utenti in caso di errore:
         1. abilita **[!UICONTROL Notify on failure]**.
         1. Specificare uno o più indirizzi e-mail separati da virgole in **[!UICONTROL Failure email recipients]**.
      * Per inviare una notifica agli utenti in caso di esito positivo:
         1. Abilita **[!UICONTROL Notify on success]**.
         1. Specificare uno o più indirizzi e-mail separati da virgole in **[!UICONTROL Success email recipients]**.
   1. Modifica **[!UICONTROL Subscriptions]**.
      * È possibile definire più combinazioni di **[!UICONTROL Report Suite]** e **[!UICONTROL Dimension]** in un set di classificazione.
      * Selezionare ![CrossSize400](/help/assets/icons/CrossSize400.svg) per eliminare una combinazione di **[!UICONTROL Report Suite]** e **[!UICONTROL Key Dimension]**.

      Per ulteriori dettagli, consulta [Creare un set di classificazione](/help/components/classifications/sets/manage-sets.md).
   1. Selezionare **[!UICONTROL Save]** per salvare le impostazioni. Seleziona **[!UICONTROL Cancel]** per annullare.
