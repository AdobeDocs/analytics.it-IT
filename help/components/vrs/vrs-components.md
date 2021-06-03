---
description: È possibile curare le suite di rapporti virtuali per includere ed escludere i componenti in Analysis Workspace.
title: Cura dei componenti di suite di rapporti virtuali
uuid: 6c6a4071-22ad-4e8c-b1ed-140b2aa04f76
exl-id: 19163829-328a-4064-b1be-8c09d1d94a0d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 10%

---

# Cura dei componenti di suite di rapporti virtuali

È possibile curare le suite di rapporti virtuali per includere ed escludere i componenti in Analysis Workspace.

>[!NOTE]
>
>Sono state apportate modifiche ai componenti che amministratori e non amministratori possono visualizzare nei progetti Workspace curati e nelle suite di report virtuali (VRS) curate. In precedenza, chiunque poteva vedere i componenti non curati facendo clic su **[!UICONTROL Show all Components]**. L’ [esperienza di cura aggiornata](/help/analyze/analysis-workspace/curate-share/curate.md) consente un controllo più dettagliato sui componenti visibili.

Per abilitare la cura dei componenti,

1. Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]** > **[!UICONTROL Create new virtual report suite]**.
1. Dopo aver definito la **[!UICONTROL Settings]**, fai clic sulla scheda **[!UICONTROL Components]** .

1. Seleziona la casella di controllo **[!UICONTROL Enable Customization of Virtual Report Suite Components]**:

   ![](assets/vrs-enable.png)

   >[!NOTE]
   >
   >Se è abilitata la personalizzazione dei componenti, la suite di rapporti virtuali è accessibile **solo in Analysis Workspace** e non è accessibile nei seguenti elementi:
   >
   >* [!UICONTROL Reports & Analytics]
   >* [!UICONTROL Data Warehouse]
   >* [!UICONTROL Report Builder]
   >* [!UICONTROL Activity Map]
   >* API di reportistica di Analytics


   Una volta selezionato, puoi aggiungere i componenti che desideri includere nella suite di rapporti virtuali trascinando i componenti applicabili dalla colonna &quot;Componenti esclusi&quot; alla colonna &quot;Componenti inclusi&quot;. I componenti che possono essere inclusi ed esclusi sono:

   * Dimensioni
   * Metriche
   * Segmenti
   * Intervalli di date

   >[!NOTE]
   >
   >Non è necessario *condividere* componenti curati (segmenti, metriche calcolate, intervalli di date). Saranno sempre visibili in Analysis Workspace se sono curati per la suite di rapporti virtuali, anche se non sono condivisi.

1. Inoltre, puoi filtrare o cercare i componenti e aggiungere l’intera selezione filtrata alla colonna inclusa facendo clic su **[!UICONTROL Add All]**.

   ![](assets/vrs-add-all.png)

## Rinomina componenti {#section_0F7CD9F684FE4765BC00A2AFED56550E}

È possibile modificare i nomi visualizzati dei componenti inclusi specifici della suite di rapporti virtuale. Ad esempio, se desideri includere Nome pagina nella suite di rapporti virtuali ma vuoi rinominarlo in un contesto più semplice per i dispositivi mobili, puoi modificarlo in App Screens. Il nuovo nome viene visualizzato in Analysis Workspace ogni volta che si utilizza questa suite di rapporti virtuale.

![](assets/vrs-rename-component.png)

In Analysis Workspace, fai clic sull’icona delle informazioni per qualsiasi componente incluso per visualizzare il nome originale del componente rinominato:

![](assets/vrs-aw-renamed.png)

## Gruppi di componenti {#section_483BEC76F49E46ADAAA03F0A12E48426}

Utilizza i gruppi di componenti per aggiungere componenti in massa alla suite di rapporti virtuale. Ad esempio, se desideri importare un set predefinito di componenti specifici per l’analisi delle app per dispositivi mobili, seleziona il gruppo di app per dispositivi mobili. Un set corrispondente di dimensioni e metriche (già rinominato) viene aggiunto automaticamente all’elenco Incluso nella suite di rapporti virtuali.

![](assets/vrs-comp-grp.png)

## Comportamento di Workspace {#section_6C32F8B642804C0097FCB14E21028D4A}

Per ulteriori informazioni sulla cura in Analysis Workspace, consulta [Cura e condivisione di un progetto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html).
