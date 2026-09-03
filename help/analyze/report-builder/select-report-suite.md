---
title: Selezionare Una Suite Di Rapporti In Report Builder
description: Scopri come selezionare una suite di rapporti in Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 96e24d5d-78fb-4e5c-8513-c5fe221d0aeb
TQID: https://experienceleague.adobe.com/eqAH1gQYgJ05VVa7THd7taOB7S3mhzyOk-29zQHoIxM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 1%

---

# Seleziona una suite di rapporti

Puoi selezionare una suite di rapporti dal menu a discesa oppure selezionare una suite di rapporti da una cella e aggiornare automaticamente il blocco di dati con una nuova suite di rapporti.

## Seleziona suite di rapporti da una cella

La selezione di una suite di rapporti da una cella semplifica l’aggiornamento dei blocchi di dati utilizzando suite di rapporti diverse. Invece di creare rapporti completamente nuovi con blocchi di dati separati, puoi aggiornare i blocchi di dati con una suite di rapporti selezionata da una cella.

La selezione di una suite di rapporti da una cella è utile quando:

* Più suite di rapporti simili o identiche nella struttura.
* Formati di blocchi di dati complessi che includono componenti e layout personalizzati.

Per selezionare una suite di rapporti da una cella, crea prima un blocco di dati e assegna più suite di rapporti a una cella al di fuori del blocco di dati. Quindi, utilizza il pannello **[!UICONTROL Report suite from cell]** per aggiornare i blocchi di dati da suite di rapporti diverse.

1. Crea un blocco di dati. Per informazioni sulla creazione di un blocco di dati, vedere [Creare un blocco di dati](/help/analyze/report-builder/create-a-data-block.md).

1. Selezionare ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) in **[!UICONTROL Report suites]**.

1. Selezionare una cella utilizzando ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) all&#39;esterno del blocco di dati.

1. Aggiungi una o più suite di rapporti da **[!UICONTROL Select report suites to add to report suite from cell]** tramite trascinamento della selezione. In alternativa, è possibile selezionare una suite di rapporti per aggiungerla all&#39;elenco **[!UICONTROL Report suites included]**.

   * Puoi usare ![Cerca](/help/assets/icons/Search.svg) **[!UICONTROL _Seleziona suite di rapporti_]** per cercare suite di rapporti.
   * Utilizza ![MoreSmall](/help/assets/icons/MoreSmall.svg) per aprire un menu di scelta rapida in modo da poter spostare le suite di rapporti verso l&#39;alto o verso il basso nell&#39;elenco **[!UICONTROL Report suites included]**.
   * Utilizza ![CrossSize75](/help/assets/icons/CrossSize75.svg) per eliminare una suite di rapporti dall&#39;elenco **[!UICONTROL Report suites included]**.

   ![Seleziona suite di rapporti da una cella](assets/dataviews-from-a-cell.png){zoomable="yes"}

1. Selezionare **[!UICONTROL Apply]** per applicare le suite di rapporti selezionate alla cella selezionata.


## Modificare la suite di rapporti da una cella

1. Seleziona la posizione della cella della suite di rapporti nel foglio.
1. Nell&#39;hub Report Builder selezionare il collegamento **[!UICONTROL Report suites from cell]** in **[!UICONTROL Quick edit]**.
1. Selezionare una suite di rapporti dal menu a discesa **[!UICONTROL Report suite]**.

   ![Modifica suite di rapporti da una cella](assets/change-data-view-from-cell.png){zoomable="yes"}
1. Facoltativo, selezionare **[!UICONTROL Refresh data block(s) upon change]**.

1. Seleziona **[!UICONTROL Apply]**. Report Builder aggiorna il blocco di dati in base alla suite di rapporti selezionata.
