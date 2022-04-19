---
description: Pannello che mostra gli elementi dimensionali successivi o precedenti per una dimensione specifica.
title: Pannello elemento successivo o precedente
feature: Panels
role: User, Admin
source-git-commit: 2a16410a1a9ece301844ef0f242d09e3a16318c0
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 3%

---


# Pannello elemento successivo o precedente

La [!UICONTROL Next or previous item] pannello avviato come rapporto in Reports &amp; Analytics, in [!UICONTROL Reports] > [!UICONTROL Most popular] > [!UICONTROL Next page/Previous page]. Questo pannello Workspace contiene diverse tabelle e visualizzazioni per identificare facilmente l’elemento dimensionale successivo o precedente per una dimensione specifica. Esempio,

## Accedere al pannello

Puoi accedere al pannello da [!UICONTROL Reports] o [!UICONTROL Workspace].

| Punto di accesso | Descrizione |
| --- | --- |
| [!UICONTROL Reports] | <ul><li>Il pannello è già stato rilasciato in un progetto.</li><li>La barra a sinistra viene ridotta.</li><li>Se hai selezionato [!UICONTROL Next page], le impostazioni predefinite sono già state applicate, ad esempio [!UICONTROL Page] per [!UICONTROL Dimension]e nella pagina superiore come [!UICONTROL Dimension Item], [!UICONTROL Next] per [!UICONTROL Direction] e [!UICONTROL Visit] per [!UICONTROL Container]. Puoi modificare tutte queste impostazioni.</li></ul>![Pannello successivo/precedente](assets/next-previous.png) |
| Workspace | Crea un nuovo progetto e seleziona l’icona Pannello nella barra a sinistra. Quindi trascina la [!UICONTROL Next or previous item] sopra la tabella a forma libera. Tieni presente che [!UICONTROL Dimension] e [!UICONTROL Dimension Item] i campi vengono lasciati vuoti. Seleziona una dimensione dal menu a discesa. [!UICONTROL Dimension items] vengono compilati in base ai [!UICONTROL dimension] ha scelto. Viene aggiunto l’elemento di dimensione superiore, ma puoi selezionare un altro elemento.<p>![Pannello successivo/precedente](assets/next-previous2.png) |

## Input del pannello {#Input}

Puoi configurare le [!UICONTROL Next or previous item] pannello con le seguenti impostazioni di input:

| Impostazione | Descrizione |
| --- | --- |
| Zona di rilascio del segmento (o altro componente) | Puoi trascinare segmenti o altri componenti per filtrare ulteriormente i risultati del pannello. |
| Dimensione | La dimensione per la quale desideri esplorare gli elementi successivi o precedenti. |
| Elemento Dimension | Elemento |
| Direzione | Specifica se stai cercando il [!UICONTROL Next] o [!UICONTROL Previous] elemento dimensione. |
| Contenitore | [!UICONTROL Visit] o [!UICONTROL Visitor] (Impostazione predefinita) determina l&#39;ambito della richiesta. |

Fai clic su **[!UICONTROL Build]** per creare il pannello .

## Output del pannello {#output}

La [!UICONTROL Next or previous item] Il pannello restituisce un set completo di dati e visualizzazioni per consentirti di comprendere meglio quali occorrenze seguono o precedono specifici elementi dimensionali.

![Uscita pannello successivo/precedente](assets/next-previous-output.png)

![Uscita pannello successivo/precedente](assets/next-previous-output2.png)

