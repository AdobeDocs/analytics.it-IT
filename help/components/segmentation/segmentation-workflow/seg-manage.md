---
description: Il Gestore segmenti offre diversi modi per curare i segmenti, ad esempio condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferiti.
title: Gestire i segmenti (Gestore segmenti)
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: 5819026bd3798cd936094f138cd236b1cb4b278e
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 21%

---

# Gestire segmenti


Puoi [condividere](t-seg-share.md), [segmento](t-seg-filter.md), [tag](seg-tag.md), [approvare](seg-approve.md), rinominare, [copiare](seg-copy.md), eliminare, esportare segmenti e contrassegnarli come [preferiti](t-seg-favorite.md) da un&#39;interfaccia di gestione [!UICONTROL Segment] centrale. Per gestire i segmenti:

* Seleziona **[!UICONTROL Components]** nell’interfaccia principale, quindi seleziona **[!UICONTROL Segments]**.


>[!NOTE]
>
>I segmenti rapidi creati all&#39;interno di un progetto Workspace specifico non vengono visualizzati nel gestore [!UICONTROL Segment], a meno che il segmento non sia stato reso disponibile per tutti i progetti.
>

## Gestore segmenti

Il Gestore segmenti dispone dei seguenti elementi dell’interfaccia:

![Interfaccia segmento](assets/segments-manager.png)

### Elenco segmenti

Nell&#39;elenco dei segmenti ➊ vengono visualizzati tutti i segmenti di tua proprietà, quelli con ambito in tutti i tuoi progetti e quelli condivisi con te. L’elenco dispone delle seguenti colonne:

| Colonna | Descrizione |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleziona questa opzione per favorire ![Star](/help/assets/icons/Star.svg) o per non favorire ![StarOutline](/help/assets/icons/StarOutline.svg) un segmento. Vedi [Segmento contrassegnato come preferito](t-seg-favorite.md) |
| **[!UICONTROL Title and description]** | Per modificare il segmento, seleziona il collegamento del titolo, che apre il [Generatore di segmenti](seg-build.md). Un segmento condiviso è indicato con ![Condividi](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Report suitew]** | La suite di rapporti a cui si applica questo segmento. |
| **[!UICONTROL Owner]** | Il proprietario del segmento. In qualità di utente, puoi visualizzare solo i segmenti di tua proprietà o le annotazioni condivise con te. |
| **[!UICONTROL Tags]** | I tag per questo segmento. |
| **[!UICONTROL Shared with]** | Quanti singoli utenti o gruppi hai condiviso il segmento con. Seleziona per aprire la finestra di dialogo **[!UICONTROL Share Component]**. Consulta [Condividi segmenti](t-seg-share.md) per ulteriori informazioni. |
| **[!UICONTROL Published]** | Indica se il segmento [ è pubblicato](seg-publish.md) in Experience Cloud. |
| **[!UICONTROL Date modified]** | La data e l’ora dell’ultima modifica apportata al segmento. |

Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per specificare quali colonne vuoi visualizzare.

### Barra delle azioni

È possibile eseguire azioni sui segmenti utilizzando la barra delle azioni ➋. La barra delle azioni contiene le azioni seguenti:

| Azione | Descrizione |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | Aggiungi un altro segmento utilizzando il [Generatore di segmenti](seg-build.md). |
| ![Ricerca](/help/assets/icons/Search.svg) [!UICONTROL *Ricerca per titolo*] | Se nell’elenco non è selezionato alcun segmento, cerca i segmenti utilizzando questo campo di ricerca. |
| ![Etichetta](/help/assets/icons/Label.svg) **[!UICONTROL Tag]** | Assegna tag ai segmenti selezionati. Nella finestra di dialogo **[!UICONTROL Tag Segment]**, seleziona o deseleziona i tag per i segmenti selezionati. Selezionare **[!UICONTROL Save]** per salvare i tag per i segmenti selezionati. Per ulteriori informazioni, consulta [Segmenti di tag](seg-tag.md). |
| ![Condividi](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share]** | Condividi i segmenti selezionati. Nella finestra di dialogo **[!UICONTROL Share Segment]**, puoi effettuare una ![Ricerca](/help/assets/icons/Search.svg) *Ricerca di singoli utenti o gruppi* oppure puoi selezionare **[!UICONTROL Organization]** o **[!UICONTROL Groups]**. Selezionare **[!UICONTROL Save]** per salvare i dettagli di condivisione per i segmenti selezionati. Consulta [Condividi segmenti](t-seg-share.md) per ulteriori informazioni. |
| ![Elimina](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]** | Elimina i segmenti selezionati. Viene richiesta una conferma. |
| ![Modifica](/help/assets/icons/Edit.svg) **[!UICONTROL Rename]** | Rinomina un singolo segmento selezionato. Se questa opzione è selezionata, è possibile rinominare il segmento in linea. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Approve]** | Approva i segmenti selezionati. Per ulteriori informazioni, consulta [Approvare segmenti](seg-approve.md). |
| ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copy]** | Copia il segmento selezionato. I nuovi segmenti vengono creati con lo stesso nome e suffisso `(Copy)`. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Export to CSV]** | Esporta i segmenti in un file `Segments List.csv`. |

### Barra dei filtri attivi

La barra dei filtri ➌ mostra i segmenti attivi applicati dal pannello dei filtri all&#39;elenco dei segmenti (se presenti). Puoi rimuovere rapidamente un filtro utilizzando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se sono specificati più filtri, è possibile rimuovere tutti utilizzando **[!UICONTROL Remove all]**.

### Pannello dei filtri

Puoi filtrare l&#39;elenco dei segmenti utilizzando il ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]** pannello sinistro ➍. Nel pannello dei filtri viene visualizzato il tipo di filtro e il numero di segmenti che rispettano il filtro specifico. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per attivare/disattivare la visualizzazione del pannello Filtro.

Vedi [Filtra l&#39;elenco dei segmenti](t-seg-filter.md) per ulteriori informazioni.


<!--

The Segment Manager offers many ways of curating segments, such as sharing, filtering, tagging, approving, copying, deleting, and marking as favorites.

The Analytics Segment Manager shows you all the segments you own and that have been shared with you. Admin-level users can see all segments in the organization. This overview presents the user interface and the capabilities of the Segment Manager. 

![Segments manager](assets/segments-manager.png)

## Access the Segment Manager

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**.

   Or 

   In an existing report, select the Segments icon ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) in the left navigation, then select **[!UICONTROL Manage]**.

## Available actions in the Segment Manager

In the Segment Manager, you can:

* [Filter segments](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Approve segments](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Tag segments](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Share segments](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Export a segment to a CSV file.

* [Copy segments](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Delete segments](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configure columns

You can configure the information displayed for each segment in the Segment Manager by configuring the columns that are displayed.

To configure the visible columns in the Segment Manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**. 

1. In the Segment Manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Segment Manager.

   The following columns are available:

   | Column title | Description  |
   |---|---|
   | Title and description | These values are provided in the Segment builder. To edit the title and description, select the title link to open the Segment builder.  |
   | Favorites  | Displays star icons next to each segment, allowing you to mark segments as favorites. For more information, see [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Report suites  | This column indicates in which report suite the segment was last saved.  |
   | Owner  | Indicates who owns the segment. As a non-Admin, you can see only segments you own or those that were shared with you.  |
   | Tags (not checked in column selector, hence column not appearing)  | Tags that were applied to the segment, either by you or by people who shared the segment with you.  |
   | Shared with  | Lists individuals or groups (Admin only) or All (Admin only) that you shared the segment with. <p>When a segment is being shared by you or with you, a share icon displays next to the segment name.</p>|
   | Date modified  | Shows the date that the segment was last modified.  |
   | Used in | Shows where segments are currently being used, and how many times they are being used in each area. <p>For example, if the segment is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**].</p> <p>Select the value in this column to see the breakdown of where the segments are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Alerts (2)**]). Furthermore, you can view the list of items where the segments are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of segments being used in that area:</p>  <ul><li>[!UICONTROL **Projects**]<p>Contains segments that were [created in the segment builder](/help/components/segmentation/segmentation-workflow/seg-build.md) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains segments that were [created as quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Alerts**]</li><li>[!UICONTROL **Calculated metrics**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a segment includes another segment in its definition, any use of that segment is not shown in the [!UICONTROL **Used in**] column. If a segment is included in the definition of another type of component (such as a calculated metric), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p>  |
   | Last used | Shows the date when the segment was last used in any of the following component types: <ul><li>Alerts</li><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li><li>Segments</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |
   
   {style="table-layout:auto"}

## How-To Video {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

This [Adobe Analytics video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=it) gives a short overview of how to use the Segment Manager.

-->