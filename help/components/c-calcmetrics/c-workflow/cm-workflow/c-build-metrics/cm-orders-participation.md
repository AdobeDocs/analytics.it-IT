---
description: Spiega come creare una metrica che mostra quali canali di marketing supportano gli ordini. Può essere adattato a qualsiasi dimensione o evento di successo di interesse.
title: Ordina metrica di assistenze
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 3%

---

# Ordina metrica di assistenze

Spiega come creare una metrica che mostra quali canali di marketing supportano gli ordini. Può essere adattato a qualsiasi dimensione o evento di successo di interesse.

1. Nel Generatore di metriche calcolate, assegna alla metrica il nome &quot;Ordini assistiti&quot;.
1. Nell’area di lavoro Definizione, trascina una metrica Ordini. Quindi, regola il modello di attribuzione tramite l’ingranaggio delle impostazioni selezionando la **[!UICONTROL Use non-default attribution models]** casella di controllo.

   ![](assets/attr-model.png)

1. Seleziona **[!UICONTROL Custom]** come modello di attribuzione. Cambia i pesi in 0 (starter), 100 (player) e 0 (closer).

   ![](assets/custom-attr-model.png)

1. Salva la metrica.
1. Crea una tabella a forma libera in Analysis Workspace con la dimensione Canale di marketing, Ordini e la nuova metrica Ordini assistiti.

   ![](assets/mktg-channel-assists.png)

Questo è un modo semplice per capire quali canali di marketing hanno assistito negli ordini. In alternativa, da una tabella a forma libera, puoi fare clic con il pulsante destro del mouse su una metrica e regolare il modello di attribuzione direttamente dalla tabella.
