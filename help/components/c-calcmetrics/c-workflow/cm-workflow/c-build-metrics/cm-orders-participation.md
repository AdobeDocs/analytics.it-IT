---
description: Spiega come creare una metrica che mostra quali canali di marketing supportano gli ordini. Può essere adattato a qualsiasi dimensione o evento di successo di interesse.
title: Ordina metrica di assistenze
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: bf58da2a39e8b9fd298356f23a9bf8f6c394d3de
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 0%

---

# Creare una metrica calcolata più complessa

Questo articolo spiega un esempio più complesso di metrica calcolata. Queste metriche calcolate mostrano quali canali di marketing forniscono assistenza per la gestione degli ordini. Questo tipo di metrica calcolata può essere adattata a qualsiasi dimensione o evento di successo.

1. Inizia a generare una metrica calcolata, come descritto in [Metriche di compilazione](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. Nel generatore di metriche calcolate, assegnare un nome alla metrica `Assisted Orders` o a un nome simile.

1. Selezionare la metrica **[!UICONTROL Online Orders]** dai componenti **[!UICONTROL Metrics]** e trascinarla nell&#39;area **[!UICONTROL Definition]**.

   1. Selezionare ![Impostazione](/help/assets/icons/Setting.svg) per la metrica.
   1. Seleziona **[!UICONTROL Use non-default attribution model]**.
   1. Regola il modello di attribuzione in **[!UICONTROL Column attribution model]**.
      1. Selezionare **[!UICONTROL Custom]** per **[!UICONTROL Model]**. Impostare **[!UICONTROL Starter]** su `0`, **[!UICONTROL Player]** su `100` e **[!UICONTROL Closer]** su `0`.
      1. Selezionare **[!UICONTROL Visitor]** per **[!UICONTROL Container]**.
      1. Selezionare **[!UICONTROL 30 Days]** per **[!UICONTROL Lookback window]**.

      1. Seleziona **[!UICONTROL Apply]**.

      ![Modello di attribuzione colonna](assets/complex-calculated-metric.png)

1. Selezionare **[!UICONTROL Save]** per salvare la metrica calcolata.

Per utilizzare la metrica calcolata:

1. In Analysis Workspace, crea una tabella a forma libera con la dimensione **[!UICONTROL Marketing Channel]**, **[!UICONTROL Online Orders]**, e la nuova metrica **[!UICONTROL Assisted Online Orders]**.

   ![Ordini online con assistenza per il canale di marketing](assets/marketing-channel-assists.png)

1. (Facoltativo) Condividi la metrica con altri utenti dell&#39;organizzazione, come descritto in [Condividi metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).

Questo è un modo semplice per capire quali canali di marketing hanno assistito negli ordini. In alternativa, da una tabella a forma libera, puoi fare clic con il pulsante destro del mouse su una metrica e regolare il modello di attribuzione direttamente dalla tabella.
