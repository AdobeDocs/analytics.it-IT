---
description: Utilizza le visualizzazioni Numero di riepilogo e Variazione di riepilogo per visualizzare punti dati importanti in un progetto.
title: Numero Di Riepilogo E Variazione Di Riepilogo
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 92%

---

# Numero e variazione di riepilogo

>[!BEGINSHADEBOX]

_Questo articolo documenta le visualizzazioni Numero riepilogo e Modifica riepilogo in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Consulta [Numero di riepilogo e Variazione di riepilogo](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change) per_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** versione di questo articolo._

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Per un video dimostrativo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualizzazione numero riepilogo e modifica riepilogo](https://video.tv.adobe.com/v/3416889/?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]

## Numero di riepilogo {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Numero di riepilogo"
>abstract="Crea una visualizzazione che mostra i totali e i subtotali."

<!-- markdownlint-enable MD034 -->

Utilizza la visualizzazione ![Riepilogo](/help/assets/icons/123.svg) **[!UICONTROL Summary number]** per evidenziare un numero elevato importante in un progetto. Questa visualizzazione si comporta come segue, utilizzando l’origine dati associata:

* Se non è selezionata alcuna cella, viene selezionato il totale della colonna.
* Se è selezionata una cella, viene visualizzato il riepilogo per tale cella.
* Se sono selezionate più celle, viene visualizzata la prima cella selezionata.
* Se è selezionata la colonna, viene preso il valore della prima cella della colonna.

![Visualizzazione Numero di riepilogo](asses/../assets/summary-number.png)

Come parte delle impostazioni di visualizzazione, sono disponibili opzioni specifiche per il numero di Riepilogo.

| Opzione | Definizione |
|--- |--- |
| **[!UICONTROL Abbreviate value]** | Seleziona **[!UICONTROL Abbreviate value]** per abbreviare in modo intelligente il valore numerico. Se questa opzione è selezionata, immetti un numero per definire la quantità di abbreviazione. Ad esempio:<br/><table><tr><td>**Valore originale**</td><td>**Valore abbreviazione**</td><td>**Risultato**</td></tr><tr><td>12.011.141,25 $</td><td>Non selezionato</td><td  align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `0`</td><td align="right">12 milioni $</td></tr><tr><td>12.011.141,25 $</td><td> Selezionato, impostato su `1`</td><td  align="right">12,0 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `2`</td><td align="right">12,01 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `3`</td><td align="right">12,011 milioni $</td></tr></table> |
| **[!UICONTROL Summarize value by]** | Scegli di visualizzare il massimo, il minimo, la media, la mediana o la somma per una selezione di dati. |

## Variazione di riepilogo {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="Variazione di riepilogo"
>abstract="Crea una visualizzazione che mostra il delta (variazione) tra due numeri"

<!-- markdownlint-enable MD034 -->


Utilizza la visualizzazione ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Summary Change]** per visualizzare il delta (variazione) tra due numeri. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](/help/admin/tools/success-events/success-event.md) or a calculated metric's [Show Upward Trend As](/help/components/calculated-metrics/workflow/cm-build-metrics.md) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md.md) or a calculated metric's [Show Upward Trend As](/help/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.md) option.
-->

Questa visualizzazione si comporta come segue:

* Se non è selezionata alcuna cella, vengono confrontati i valori delle prime due celle della colonna.
* Se è selezionata una cella, viene riportato 0 perché il valore della cella viene confrontato con se stesso e quindi non si verifica alcuna variazione nei valori.
* Se sono selezionate due celle, la prima cella selezionata funge da numeratore e la seconda da denominatore.
* Se sono selezionate più celle, per il confronto vengono considerate solo le prime due celle.
* Se è selezionato un intervallo di celle, vengono confrontate la prima e l’ultima cella selezionata nell’intervallo.
* Se è selezionata la colonna, il primo valore viene confrontato con se stesso, e la variazione risulta quindi pari a 0.


![Visualizzazione delle modifiche di riepilogo che mostra il delta tra due numeri.](assets/summary-change.png)


Come parte delle impostazioni di visualizzazione, sono disponibili **[!UICONTROL Summary change options]** specifiche.

| Opzione | Definizione |
|--- |--- |
| **[!UICONTROL Show percent change]** | Mostra la variazione percentuale tra i 2 numeri. |
| **[!UICONTROL Show raw difference]** | Mostra la differenza grezza tra i 2 numeri. Con questa opzione è inoltre possibile abbreviare i valori e visualizzare fino a 3 posizioni decimali. |
| **[!UICONTROL Abbreviate value]** | Seleziona **[!UICONTROL Abbreviate value]** per abbreviare in modo intelligente il valore modificato. Se questa opzione è selezionata, immetti un numero per definire la quantità di abbreviazione. Ad esempio:<br/><table><tr><td>**Valore originale**</td><td>**Valore abbreviazione**</td><td>**Risultato**</td></tr><tr><td>12.011.141,25 $</td><td>Non selezionato</td><td  align="right">12.011.141,25 $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `0`</td><td align="right">12 milioni $</td></tr><tr><td>12.011.141,25 $</td><td> Selezionato, impostato su `1`</td><td  align="right">12,0 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `2`</td><td align="right">12,01 milioni $</td></tr><tr><td>12.011.141,25 $</td><td>Selezionato, impostato su `3`</td><td align="right">12,011 milioni $</td></tr></table> |

>[!MORELIKETHIS]
>
>[Aggiungere una visualizzazione a un pannello](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Impostazioni di visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menu di scelta rapida della visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
