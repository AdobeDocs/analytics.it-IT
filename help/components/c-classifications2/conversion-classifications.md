---
description: Le classificazioni vengono utilizzate per suddividere i valori in gruppi e generare rapporti a livello di gruppo. Ad esempio, potete classificare tutte le campagne Search Search in una categoria come i termini musicali pop-up e segnalare il successo della categoria rispetto a metriche quali istanze (click-through) e conversione in eventi di successo.
seo-description: Le classificazioni vengono utilizzate per suddividere i valori in gruppi e generare rapporti a livello di gruppo. Ad esempio, potete classificare tutte le campagne Search Search in una categoria come i termini musicali pop-up e segnalare il successo della categoria rispetto a metriche quali istanze (click-through) e conversione in eventi di successo.
seo-title: Classificazioni conversione
solution: Analytics
subtopic: Classificazioni
title: Classificazioni conversione
topic: Strumenti di amministrazione
uuid: 4 c 8726 c 9-f 527-44 e 1-be 01-8 c 7 b 3 b 5 c 20 f 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Classificazioni conversione

Le classificazioni vengono utilizzate per suddividere i valori in gruppi e generare rapporti a livello di gruppo. Ad esempio, potete classificare tutte le campagne Search Search in una categoria come i termini musicali pop-up e segnalare il successo della categoria rispetto a metriche quali istanze (click-through) e conversione in eventi di successo.

## Conversion classifications {#concept_B4B1478A8CB540599AC9D4A58CA4B6FE}

Le classificazioni vengono utilizzate per suddividere i valori in gruppi e generare rapporti a livello di gruppo. For example, you can classify all Paid Search campaigns into a category like *pop music terms* and report on the success of that category relative to metrics like Instances (click-throughs), and conversion to success events.

Le classificazioni di conversione consentono di classificare le variabili di conversione. Una volta classificati, qualsiasi rapporto che è possibile generare utilizzando i dati chiave può essere generato anche utilizzando le proprietà dei dati associate.

After enabling classifications, use the [Classification Importer](../../components/c-classifications2/c-classifications-importer/c-working-with-saint.md#concept_08ED8C7A86C64E7DA5DE3044BB94B2EA) to assign specific values to the appropriate classification.

## Conversion Classifications Descriptions {#section_4A98DD5F5C314B9DAEE710AEE4EE51D4}

<table id="table_0B72C485467348E2A34BF913441F4AF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nome</span> </td> 
   <td colname="col2"> Il nome della classificazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Data abilitata (solo testo)</span> </td> 
   <td colname="col2"> <p>Indica se la classificazione del testo è un intervallo di date per le variabili della campagna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Opzioni (solo testo)</span> </td> 
   <td colname="col2">Crea un elenco di valori di classificazione disponibili per questa classificazione. Use <span class="wintitle"> Options</span> with campaign variables to provide users with a list of supported values for the classification in the <span class="wintitle"> Campaign Manager</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Tipo di numero (solo numerico)</span> </td> 
   <td colname="col2">Specifica il tipo di numero nella classificazione numerica. Options include <span class="wintitle"> Numeric</span>, <span class="wintitle"> Percent</span>, and <span class="wintitle"> Currency</span>. </td> 
  </tr> 
 </tbody> 
</table>

## Add conversion classifications {#task_D535D09E3EAF4CD1A15A6B93C0BB1BB5}

<!-- 

t_classification_conversion.xml

 -->

Procedura che descrive come aggiungere classificazioni conversione in Amministratore.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Seleziona una suite di rapporti.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**.
1. From the **[!UICONTROL Select Classification Type]** drop-down list, select the variable where you want to add a classification.

   ![Informazioni passo](assets/sub_class_create.png)

1. Mouse over the **[!UICONTROL Edit Classification]** icon, then select **[!UICONTROL Add Classification]**.
1. In the **[!UICONTROL Select Type]** field, select the type of classification you want to add to the variable.

   Options include **[!UICONTROL Text]** and **[!UICONTROL Numeric]**. For more information on classification types, see [About Classifications](../../components/c-classifications2/c-classifications.md#concept_4CEC7FF1A9E24204A7DA6B9AC70709DE).
1. In the **[!UICONTROL Text Classifications]** dialog box, configure the classification as desired.

   See [Conversion Classifications Descriptions](../../components/c-classifications2/conversion-classifications.md#section_4A98DD5F5C314B9DAEE710AEE4EE51D4) for information about these elements.

1. In the **[!UICONTROL Dropdown List]** dialog box, add or remove options.

   L'aggiunta di opzioni crea un elenco di valori di classificazione disponibili per questa classificazione. Potete utilizzare questa opzione con le variabili Campagna per fornire agli utenti un elenco di valori supportati per la classificazione in Gestione campagna. Utilizzate questa opzione per le dimensioni di classificazione in cui è presente un numero limitato di valori consentiti, raramente o mai modificati. Ad esempio, puoi eseguire campagne diverse mirate a diversi livelli di fedeltà cliente: Argento, Gold e Platinum. È quindi possibile utilizzare l'elenco a discesa per verificare che gli unici valori accettati siano quelli che corrispondono ai tre livelli. Se qualcuno tenta di utilizzare un altro valore, viene eliminato.
1. Fai clic su **[!UICONTROL Save]**.

## Delete a conversion classification {#task_566651BC245944618A6A833E58211FDE}

<!-- 

t_classification_delete_conversion.xml

 -->

Eliminate una classificazione di conversione quando non è più necessaria.

1. Open the Report Suite Manager by clicking **[!UICONTROL Admin]**&gt; **[!UICONTROL Report Suites]** in the Suite header.
1. Seleziona una suite di rapporti.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Conversion Classifications]**.
1. From the **[!UICONTROL Select Classification Type]** drop-down list, select the variable where you want to delete a classification.
1. Mouse over the **[!UICONTROL Edit Classification]** icon, then select **[!UICONTROL Delete Classification]**.
1. In the Delete Classification dialog box, click **[!UICONTROL Delete]**.
