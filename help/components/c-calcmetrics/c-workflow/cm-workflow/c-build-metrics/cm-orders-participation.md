---
description: Spiega come creare una metrica che mostra quali canali di marketing contribuiscono alla guida degli ordini. Questo può essere adattato a qualsiasi dimensione o evento di successo di interesse.
title: Ordina metrica di assistenze
uuid: 7c82227a-7fcc-486f-bef8-164ea84af77c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Ordina metrica di assistenze

Spiega come creare una metrica che mostra quali canali di marketing contribuiscono alla guida degli ordini. Questo può essere adattato a qualsiasi dimensione o evento di successo di interesse.

1. In Calculated Metrics Builder (Generatore di metriche calcolate), denominate la metrica "Assisted Orders" (Ordini assistiti).
1. Nell’area di lavoro Definizione, trascinare in una metrica Ordini. Quindi, regolate il modello di attribuzione tramite l'ingranaggio delle impostazioni selezionando la **[!UICONTROL Use non-default attribution models]** casella di controllo.

   ![](assets/attr-model.png)

1. Selezionare **[!UICONTROL Custom]** come modello di attribuzione. Modificate i pesi in 0 (antipasto), 100 (lettore) e 0 (più vicino).

   ![](assets/custom-attr-model.png)

1. Salva la metrica.
1. Crea una tabella a forma libera in Analysis Workspace con la dimensione Canale marketing, Ordini e la nuova metrica Ordini assistiti.

   ![](assets/mktg-channel-assists.png)

Questo è un modo facile per dire quali canali di marketing hanno aiutato negli ordini di guida. In alternativa, da una tabella a forma libera, puoi fare clic con il pulsante destro del mouse su una metrica e regolare il modello di attribuzione direttamente dalla tabella.
