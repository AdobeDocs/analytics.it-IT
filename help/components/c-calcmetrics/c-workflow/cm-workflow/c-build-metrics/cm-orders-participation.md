---
description: Spiega come creare una metrica che mostri quali canali di marketing contribuiscono agli ordini di guida. Questo può essere adattato a qualsiasi dimensione o evento di successo di interesse.
title: Ordina metrica di assistenze
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 3%

---

# Ordina metrica di assistenze

Spiega come creare una metrica che mostri quali canali di marketing contribuiscono agli ordini di guida. Questo può essere adattato a qualsiasi dimensione o evento di successo di interesse.

1. Nel generatore di metriche calcolate, denomina la metrica &quot;Ordini assistiti&quot;.
1. Nell’area di lavoro Definizione, trascina una metrica Ordini . Quindi, regola il modello di attribuzione tramite l’ingranaggio delle impostazioni selezionando la **[!UICONTROL Use non-default attribution models]** casella di controllo.

   ![](assets/attr-model.png)

1. Seleziona **[!UICONTROL Custom]** come modello di attribuzione. Cambiare i pesi in 0 (antipasto), 100 (lettore) e 0 (più vicino).

   ![](assets/custom-attr-model.png)

1. Salva la metrica.
1. Crea una tabella a forma libera in Analysis Workspace con la dimensione Canale di marketing, Ordini e la nuova metrica Ordini assistiti .

   ![](assets/mktg-channel-assists.png)

Questo è un modo semplice per capire quali canali di marketing hanno aiutato negli ordini di guida. In alternativa, da una tabella a forma libera, puoi fare clic con il pulsante destro del mouse su una metrica e regolare il modello di attribuzione direttamente dalla tabella.
