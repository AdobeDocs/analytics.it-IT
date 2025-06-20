---
description: Scopri
title: Tipo di metrica e attribuzione
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 07590d00341f9016ee0728970483e77cb8d38a9d
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 83%

---

# Tipo di metrica e attribuzione {#metric-type-attribution}

Puoi configurare il tipo di metrica e il [modello di attribuzione](#attribution-models) per una metrica in una definizione di metrica calcolata.

1. Seleziona ![Impostazione](/help/assets/icons/Setting.svg) nel componente metrica.
1. Nella finestra di dialogo popup:

   ![Tipo di metrica e attribuzione](assets/cm-type-alloc.png)

   * Specifica il **[!UICONTROL Metric type]**:

     | Tipi di metriche | Definizione |
     |---|---|
     | **[!UICONTROL Standard]** | Se una formula è costituita da una singola metrica standard, visualizza dati identici alla sua controparte metrica non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singolo elemento di riga. <p>Ad esempio, ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Visits]** prende gli ordini per quel particolare elemento e lo divide per il numero di visite per quel specifico elemento. |
     | **[!UICONTROL Grand total]** | Utilizza **[!UICONTROL Grand total]** per il periodo di reporting in ogni elemento di riga. Se una formula è costituita da una singola metrica Totale complessivo, la metrica calcolata visualizza lo stesso numero Totale complessivo su ogni elemento di riga. Le metriche del totale complessivo sono utili quando desideri creare metriche calcolate che si confrontano con i dati totali. <p>Ad esempio, ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Dividi](/help/assets/icons/Divide.svg) ![Evento](/help/assets/icons/Event.svg) **[!UICONTROL Total Visits]** mostra la proporzione degli ordini rispetto a tutte le visite, non solo alle visite all&#39;elemento riga specifico. In questo esempio, specifica **[!UICONTROL Grand Total]** per la metrica ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Visits]** nella metrica calcolata, che la trasformerà automaticamente in ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Visits]**. |

   * Specifica **[!UICONTROL Attribution]**.

      1. Puoi:

         * Disabilitare **[!UICONTROL Use non-default attribution model]** per utilizzare il modello di attribuzione colonna predefinito, ovvero Ultimo contatto, con un intervallo di lookback di 30 giorni.
         * Abilitare **[!UICONTROL Use non-default attribution model]**. Nella finestra di dialogo **[!UICONTROL Column attribution model]**

            * Seleziona **[!UICONTROL Model]** dai [modelli di attribuzione](#attribution-models).
            * Seleziona **[!UICONTROL Container]** dalle opzioni [container](#container).
            * Seleziona **[!UICONTROL Lookback window]** dalle opzioni dell&#39;[intervallo di lookback](#lookback-window). Se si seleziona **[!UICONTROL Custom Time]**, è possibile definire il periodo di tempo in **[!UICONTROL Minute(s)]** fino a **[!UICONTROL Quarter(s)]**.

      1. Seleziona **[!UICONTROL Apply]** per applicare il modello di attribuzione non predefinito. Seleziona Annulla per annullare.

     Se hai già definito un modello di attribuzione non predefinito, seleziona **[!UICONTROL Edit]** per modificare la selezione.

Consulta [Esempio](#example) per un esempio di utilizzo di un modello di attribuzione, un contenitore e un intervallo di lookback.


## Modelli di attribuzione {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Usa modello di attribuzione non predefinito"
>abstract="Abilita un modello di attribuzione non predefinito per la metrica selezionata."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modello"
>abstract="Seleziona un modello di attribuzione per la metrica."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Ultimo contatto"
>abstract="Il 100% del credito va all’ultimo valore di dimensione visualizzato da un visitatore."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Primo contatto"
>abstract="Il 100% del credito va al primo valore di dimensione visualizzato da un visitatore."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Lineare"
>abstract="Il credito è distribuito in modo uniforme tra tutti i valori di dimensione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Partecipazione"
>abstract="Il 100% del credito va a ogni valore di dimensione visualizzato da un visitatore.<br/>I totali delle colonne sono sovrastimati."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Stesso contatto"
>abstract="Il credito viene assegnato solo ai valori di dimensione che si verificano nello stesso evento come la conversione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Stesso contatto"
>abstract="Il credito viene assegnato solo ai valori di dimensione che si verificano nello stesso evento come la conversione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="A forma di U"
>abstract="Il 40% del credito va al primo valore di dimensione, il 40% all’ultimo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="Curva J"
>abstract="Il 60% del credito va all’ultimo valore di dimensione, il 20% al primo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="Curva J"
>abstract="Il 60% del credito va all’ultimo valore di dimensione, il 20% al primo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="J inversa"
>abstract="Il 60% del credito va al primo valore di dimensione, il 20% all’ultimo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="J inversa"
>abstract="Il 60% del credito va al primo valore di dimensione, il 20% all’ultimo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Decadimento nel tempo"
>abstract="Il merito maggiore viene attribuito ai valori di dimensione più vicini nel tempo a una conversione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personalizzato"
>abstract="Definisci una ponderazione di attribuzione basata sulla posizione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Personalizzato"
>abstract="Definisci una ponderazione di attribuzione basata sulla posizione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algoritmico"
>abstract="Il credito è determinato dinamicamente su un algoritmo statistico."

{{attribution-models-details}}


## Contenitore {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Contenitore"
>abstract="Seleziona un contenitore per impostare l’ambito desiderato per l’attribuzione."

{{attribution-container}}


## Intervallo di lookback {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Intervallo di lookback"
>abstract="Questa impostazione determina la finestra di attribuzione dei dati che verrà applicata a per ogni conversione."

{{attribution-lookback-window}}

## Esempio

{{attribution-example}}


<!--
When [building a calculated metric](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), you can specify the metric type and the attribution model.

## Metric type

To specify the metric type when building a calculated metric:

1. Select the gear icon next to the metric whose type you want to select.

   ![](assets/cm-type-alloc.png) 

1. Choose from the following options:

   |  Metric Type  | Definition  |
   |---|---|
   |  Standard  | These metrics are the same metrics used in standard [!DNL Analytics] reporting. If a formula consisted of a single standard metric, it displays identical data to its non-calculated-metric counterpart. Standard metrics are useful for creating calculated metrics specific to each individual line item. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item.  |
   |  Grand total  | Use Grand total for the reporting period in every line item. If a formula consisted of a single Grand total metric, it displays the same total number on every line item. Grand total metrics are useful for creating calculated metrics that compare against site total data. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item.  |

## How linear allocation works

[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) is how allocation models in calculated metrics are evaluated.

For a full list of non-default attribution models and lookback windows supported, see [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).

The following example illustrates how calculated metrics with linear allocations work in reporting: 

| | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 | Hit 6 | Hit 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
|Data Sent In|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|
|Last Touch eVar|PROMO A|PROMO A|PROMO A|PROMO B|PROMO B|PROMO C|$10|
|First Touch eVar|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|$10|
|Example prop|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|

In this example, the values A, B, and C were sent into a variable on hits 1, 3, 4, and 6 before a $10 purchase was made on hit 7. In the second row, those values persist across hits on a last touch visit basis. The third row illustrates a first-touch visit persistence. Finally, the last row illustrates how data would be recorded for a prop which does not have persistence.

-->