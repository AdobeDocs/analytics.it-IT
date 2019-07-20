---
description: È possibile curare le suite di rapporti virtuali per includere ed escludere componenti. In Analysis Workspace.
seo-description: È possibile curare le suite di rapporti virtuali per includere ed escludere componenti. In Analysis Workspace.
seo-title: Cura componenti suite di rapporti virtuale
title: Cura componenti suite di rapporti virtuale
uuid: 6 c 6 a 4071-22 ad -4 e 8 c-b 1 ed -140 b 2 aa 04 f 76
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Cura componenti suite di rapporti virtuale

È possibile curare le suite di rapporti virtuali per includere ed escludere componenti. In Analysis Workspace.

>[!NOTE]
>
>Sono state apportate modifiche ai componenti che amministratori e non amministratori possono visualizzare nei progetti Workspace curati e nelle suite di report virtuali (VRS) curate. Previously, anyone could see non-curated components by clicking **[!UICONTROL Show all Components]**. The [updated curation experience](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/curate-projects-vrs.html) allows for more fine-grained control over which components are visible.

Per abilitare la cura dei componenti,

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Virtual Report Suites]** &gt; **[!UICONTROL Create new virtual report suite]**.
1. After defining the **[!UICONTROL Settings]**, click the **[!UICONTROL Components]** tab.

1. Select the checkbox **[!UICONTROL Enable Customization of Virtual Report Suite Components]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >If component customization is enabled, the virtual report suite is accessible **only in Analysis Workspace** and is not accessible in the following:

   * [!UICONTROL Reports & Analytics]
   * [!UICONTROL Ad Hoc Analysis]
   * [!UICONTROL Data Warehouse]
   * [!UICONTROL Report Builder]
   * API di reporting analisi
   Una volta attivato, puoi aggiungere i componenti che desideri includere nella suite di rapporti virtuale trascinando i componenti applicabili dalla colonna «componenti esclusi» alla colonna «Componenti inclusi». I componenti che possono essere inclusi ed esclusi sono:

   * Dimensioni
   * Metriche
   * Segmenti
   * Intervalli di date
   >[!NOTE]
   >
   >There is no need to *share* curated components (segments, calculated metrics, date ranges). Saranno sempre visibili in Analysis Workspace se sono curati per la suite di rapporti virtuali, anche se non sono condivisi.

1. Additionally, you can filter or search the components and add the entire filtered selection to the included column by clicking **[!UICONTROL Add All]**.

   ![](assets/vrs-add-all.png)

## Rename Components {#section_0F7CD9F684FE4765BC00A2AFED56550E}

Potete modificare i nomi visualizzati dei componenti inclusi per la suite di rapporti virtuale. Ad esempio, se desiderate includere Nome pagina nella suite di rapporti virtuali, ma desiderate rinominarlo in un contesto più semplice per dispositivi mobili, potete modificarlo in Schermi app. Il nuovo nome viene visualizzato in Analysis Workspace ogni volta che viene utilizzata questa suite di rapporti virtuale.

![](assets/vrs-rename-component.png)

In Analysis Workspace, fai clic sull'icona delle informazioni per qualsiasi componente incluso per visualizzare il nome originale del componente rinominato:

![](assets/vrs-aw-renamed.png)

## Component Groups {#section_483BEC76F49E46ADAAA03F0A12E48426}

Utilizzate i gruppi di componenti per aggiungere componenti in massa alla suite di rapporti virtuale. Ad esempio, se desideri importare un set predefinito di componenti specifici per l'analisi delle app mobili, seleziona il gruppo di app mobile. Un set corrispondente di dimensioni e metriche (già rinominate) viene aggiunto automaticamente all'elenco Suite di rapporti virtuale incluso.

![](assets/vrs-comp-grp.png)

## Workspace Behavior {#section_6C32F8B642804C0097FCB14E21028D4A}

For more information on curation in Analysis Workspace, see [Curate and Share a Project](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/curate.html).