---
description: Le suite di rapporti virtuali possono essere curate per includere ed escludere i componenti.in Analysis Workspace.
title: Cura dei componenti della suite di rapporti virtuali
feature: VRS
exl-id: 19163829-328a-4064-b1be-8c09d1d94a0d
TQID: https://experienceleague.adobe.com/j86dD5Yzd6GIoQOzhHsU8YbShQiODtbU8aCdM3UxRMg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 10%

---

# Cura dei componenti della suite di rapporti virtuali

Le suite di rapporti virtuali possono essere curate per includere ed escludere i componenti.in Analysis Workspace.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cura dei componenti](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/components/virtual-report-suites/component-curation-in-virtual-report-suites){target="_blank"}.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Sono state apportate modifiche ai componenti che amministratori e non amministratori possono visualizzare nei progetti Workspace curati e nelle suite di rapporti virtuali (VRS) curate. In precedenza, chiunque poteva vedere i componenti non curati facendo clic su **[!UICONTROL Show all Components]**. La [esperienza di gestione aggiornata](/help/analyze/analysis-workspace/curate-share/curate.md) consente un controllo più dettagliato sui componenti visibili.

Per abilitare la cura dei componenti:

1. Passa a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual report suites]** > **[!UICONTROL Create new virtual report suite]**.
1. Dopo aver definito **[!UICONTROL Settings]**, fare clic sulla scheda **[!UICONTROL Components]**.

1. Selezionare la casella di controllo **[!UICONTROL Enable Customization of Virtual report suite components]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >Se è abilitata la personalizzazione dei componenti, la suite di rapporti virtuali è accessibile **solo in Analysis Workspace** e non nei seguenti elementi:
   >
   >* [!UICONTROL Data Warehouse]
   >* [!UICONTROL Report Builder]
   >* [!UICONTROL Activity Map]
   >* API di reportistica di Analytics

   Una volta selezionata, puoi aggiungere i componenti da includere nella suite di rapporti virtuali trascinando i componenti applicabili dalla colonna &quot;componenti esclusi&quot; alla colonna &quot;componenti inclusi&quot;. I componenti che possono essere inclusi ed esclusi sono:

   * Dimensioni
   * Metriche
   * Segmenti
   * Intervalli di date

   >[!NOTE]
   >
   >Non è necessario *condividere* componenti curati (segmenti, metriche calcolate, intervalli di date). Saranno sempre visibili in Analysis Workspace se sono curati per la suite di rapporti virtuale, anche se non sono condivisi.

1. È inoltre possibile filtrare o cercare i componenti e aggiungere l&#39;intera selezione filtrata alla colonna inclusa facendo clic su **[!UICONTROL Add All]**.

   ![](assets/vrs-add-all.png)

## Rinomina componenti {#section_0F7CD9F684FE4765BC00A2AFED56550E}

Puoi modificare i nomi visualizzati dei componenti inclusi specifici della suite di rapporti virtuale. Ad esempio, se desideri includere il nome della pagina nella suite di rapporti virtuali, ma vuoi rinominarlo in un contesto più mobile, puoi cambiarlo in App Screens. Il nuovo nome viene visualizzato in Analysis Workspace ogni volta che si utilizza questa suite di rapporti virtuale.

![](assets/vrs-rename-component.png)

In Analysis Workspace, fai clic sull’icona delle informazioni di qualsiasi componente incluso per visualizzare il nome originale del componente rinominato:

![](assets/vrs-aw-renamed.png)

## Gruppi di componenti {#section_483BEC76F49E46ADAAA03F0A12E48426}

Utilizza i gruppi di componenti per effettuare aggiunte in blocco di componenti alla suite di rapporti virtuale. Ad esempio, se desideri importare un set predefinito di componenti specifici per l’analisi delle app mobili, seleziona il gruppo di app mobili. Un set corrispondente di dimensioni e metriche (già rinominato) viene aggiunto automaticamente all’elenco delle suite di rapporti virtuali incluse.

![](assets/vrs-comp-grp.png)

## Comportamento di Workspace {#section_6C32F8B642804C0097FCB14E21028D4A}

Per ulteriori informazioni sulla cura in Analysis Workspace, consulta [Curare e condividere un progetto](/help/analyze/analysis-workspace/curate-share/curate.md).
