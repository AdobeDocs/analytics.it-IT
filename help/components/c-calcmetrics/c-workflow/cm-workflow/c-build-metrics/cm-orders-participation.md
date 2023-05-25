---
description: Spiega come creare una metrica che mostra quali canali di marketing supportano gli ordini. Può essere adattato a qualsiasi dimensione o evento di successo di interesse.
title: Ordina metrica di assistenze
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: 4bf8397ee979614539baf21b36363eb03357567a
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Creare una metrica &quot;Order Assist&quot;

Le informazioni seguenti spiegano come creare una metrica che mostra quali canali di marketing supportano gli ordini. Può essere adattato a qualsiasi dimensione o evento di successo di interesse.

1. Inizia a creare una metrica calcolata, come descritto in [Creare metriche](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

1. Nel generatore di metriche calcolate, denomina la metrica &quot;Ordini assistiti&quot;.

1. Nell’area di lavoro Definizione, trascina una metrica Ordini. Quindi, regola il modello di attribuzione tramite l’ingranaggio delle impostazioni selezionando la **[!UICONTROL Use non-default attribution models]** casella di controllo.

   ![](assets/attr-model.png)

1. Seleziona **[!UICONTROL Custom]** come modello di attribuzione. Cambia i pesi in 0 (starter), 100 (player) e 0 (closer).

   ![](assets/custom-attr-model.png)

1. Seleziona [!UICONTROL **Applica**] > [!UICONTROL **Salva**].

1. In Analysis Workspace, crea una tabella a forma libera con la dimensione Canale di marketing Ordini e la nuova metrica Ordini assistiti.

   ![](assets/mktg-channel-assists.png)

   Questo è un modo semplice per capire quali canali di marketing hanno assistito negli ordini. In alternativa, da una tabella a forma libera, puoi fare clic con il pulsante destro del mouse su una metrica e regolare il modello di attribuzione direttamente dalla tabella.

1. (Facoltativo) Condividi la metrica con altri utenti dell’organizzazione, come descritto in [Condividere le metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md).
