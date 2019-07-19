---
description: Spiega come creare una metrica che mostra quali canali Marketing contribuiscono a guidare gli ordini. Questo può essere adattato a qualsiasi dimensione o evento di successo di interesse.
seo-description: Spiega come creare una metrica che mostra quali canali Marketing contribuiscono a guidare gli ordini. Questo può essere adattato a qualsiasi dimensione o evento di successo di interesse.
seo-title: Ordina metrica
title: Ordina metrica
uuid: 7 c 82227 a -7 fcc -486 f-bef 8-164 ea 84 af 77 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Ordina metrica

Spiega come creare una metrica che mostra quali canali Marketing contribuiscono a guidare gli ordini. Questo può essere adattato a qualsiasi dimensione o evento di successo di interesse.

1. Nel Generatore metriche calcolate, assegna un nome alla metrica "Ordini ereditati".
1. Nel quadro Definizione, trascinate in una metrica Ordini. Then, adjust the attribution model through the settings gear by checking the **[!UICONTROL Use non-default attribution models]** checkbox.

   ![](assets/attr-model.png)

1. Select **[!UICONTROL Custom]** as the attribution model. Cambiate i segmenti in 0 (campione), 100 (lettore) e 0 (più vicino).

   ![](assets/custom-attr-model.png)

1. Salva la metrica.
1. Crea una tabella freeform in Analysis Workspace con la dimensione Canale marketing, Ordini e la nuova metrica Ordini predefiniti.

   ![](assets/mktg-channel-assists.png)

Questo è un modo semplice per sapere quali canali marketing hanno aiutato a guidare gli ordini. In alternativa, da una tabella a forma libera, puoi fare clic con il pulsante destro del mouse su una metrica e regolare il modello di attribuzione direttamente dalla tabella.
