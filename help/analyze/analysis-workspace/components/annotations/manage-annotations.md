---
title: Gestire le annotazioni
description: Scopri come gestire le annotazioni in Analysis Workspace.
role: User, Admin
feature: Annotations
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 87%

---

# Gestire le annotazioni

Puoi condividere, filtrare, assegnare tag, approvare, copiare, eliminare annotazioni e contrassegnarle come preferite da un’interfaccia di gestione centrale delle [!UICONTROL Annotations]. Per gestire le annotazioni:

* Seleziona **[!UICONTROL Components]** nell’interfaccia principale, quindi seleziona **[!UICONTROL Annotations]**.


>[!NOTE]
>
>Le annotazioni create all’interno di un progetto Workspace specifico non vengono visualizzate nella Gestione [!UICONTROL Annotations], a meno che l’annotazione non sia stata resa disponibile per tutti i progetti.
>

## Gestione annotazioni

La Gestione annotazioni dispone dei seguenti elementi dell’interfaccia:

![Interfaccia Annotazioni](assets/annotations-manager.png)

### Elenco annotazioni

Nell&#39;elenco delle annotazioni ➊ vengono visualizzate tutte le annotazioni di cui sei proprietario, le annotazioni definite nell&#39;ambito di tutti i tuoi progetti e le annotazioni condivise con te. L’elenco dispone delle seguenti colonne:

| Colonna | Descrizione |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleziona per contrassegnare come preferita ![Star](/help/assets/icons/Star.svg) o non preferita ![StarOutline](/help/assets/icons/StarOutline.svg) un’annotazione. |
| **[!UICONTROL Title and description]** | Forniti nella Generatore di annotazioni. Per modificare il titolo e la descrizione, seleziona il collegamento del titolo e verrà aperto il [Generatore di annotazioni](/help/analyze/analysis-workspace/components/annotations/create-annotations.md#annotation-builder). Un’annotazione condivisa è indicata con ![Condividi](/help/assets/icons/ShareAlt.svg). |
| **[!UICONTROL Report suite]** | Le suite di rapporti a cui si applica questa annotazione. |
| **[!UICONTROL Owner]** | Il proprietario dell’annotazione. In quanto utente, puoi visualizzare solo le annotazioni che possiedi o quelle che sono state condivise con te. |
| **[!UICONTROL Applied date range]** | Data o intervallo di date a cui viene applicata l’annotazione. |
| **[!UICONTROL Tags]** | I tag per questa annotazione. |
| **[!UICONTROL Shared with]** | I singoli utenti o gruppi con cui hai condiviso l’annotazione. Seleziona per aprire la finestra di dialogo **[!UICONTROL Share Component]**. |
| **[!UICONTROL Date modified]** | Mostra la data e l’ora dell’ultima modifica apportata all’annotazione. |

{style="table-layout:auto"}

Utilizza ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) per specificare quali colonne vuoi visualizzare.

### Barra delle azioni

È possibile eseguire azioni sulle annotazioni utilizzando la barra delle azioni ➋. La barra delle azioni contiene le azioni seguenti:

| Icona | Azione | Descrizione |
|:--:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL Add]** | Aggiungi un’altra annotazione utilizzando il [Generatore di annotazioni](create-annotations.md#annotation-builder). |
| ![Ricerca](/help/assets/icons/Search.svg) | [!UICONTROL *Ricerca per titolo*] | Se nell’elenco non è selezionata alcuna annotazione, cerca le annotazioni utilizzando questo campo di ricerca. |
| ![Etichetta](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Assegna tag alle annotazioni selezionate. Nella finestra di dialogo **[!UICONTROL Tag Component]**, seleziona o deseleziona i tag per le annotazioni selezionate. Seleziona **[!UICONTROL Save]** per salvare i tag per le annotazioni selezionate. |
| ![Condividi](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Share]** | Condividi le annotazioni selezionate. Nella finestra di dialogo **[!UICONTROL Share Component]**, puoi effettuare una ![Ricerca](/help/assets/icons/Search.svg) *Ricerca di singoli utenti o gruppi* oppure puoi selezionare **[!UICONTROL Organization]** o **[!UICONTROL Groups]**. Seleziona **[!UICONTROL Save]** per salvare i dettagli di condivisione per le annotazioni selezionate. Per altre informazioni consulta [Condividere le annotazioni](#share-annotations). |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina le annotazioni selezionate. Viene richiesta una conferma. |
| ![Modifica](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Rinomina una singola annotazione selezionata. Se questa opzione è selezionata, puoi rinominare l’annotazione direttamente nel testo. |
| ![Copia](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Copia le annotazioni selezionate. Le nuove annotazioni vengono create con lo stesso nome e suffisso (Copia) |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export to CSV]** | Esporta le annotazioni in un file `Annotations List.csv`. |

### Barra dei filtri attivi

La barra dei filtri ➌ mostra i filtri attivi (se presenti). Puoi rimuovere rapidamente un filtro utilizzando ![CrossSize75](/help/assets/icons/CrossSize75.svg). Se sono specificati più filtri, puoi rimuoverli tutti utilizzando **[!UICONTROL Remove all]**.

### Pannello dei filtri

È possibile filtrare le annotazioni utilizzando il pannello sinistro **[!UICONTROL Filter]** di ➍. Nel pannello dei filtri viene visualizzato il tipo di filtro e il numero di annotazioni che lo rispettano. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per attivare o disattivare la visualizzazione del pannello dei filtri.

Per filtrare l’elenco dei filtri:

1. Seleziona ![Filtro](/help/assets/icons/Filter.svg) per aprire il pannello dei Filtri. Se hai bisogno di più spazio per l’elenco dei Filtri, puoi selezionare di nuovo ![Filtro](/help/assets/icons/Filter.svg) per chiudere il pannello.
1. Puoi filtrare le annotazioni utilizzando una qualsiasi delle [sezioni filtro](#filter-sections) disponibili.

   >[!INFO]
   >
   >Gli *Elementi* fanno riferimento agli elementi di annotazione visualizzati nell’[Elenco annotazioni](manage-annotations.md#annotations-list).
   > 

#### Sezioni filtro

{{tagfiltersection}}
{{reportsuitefiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


L’[elenco Annotazioni](manage-annotations.md#annotations-list) viene aggiornato automaticamente in base alla configurazione del filtro. Puoi visualizzare i filtri configurati nella [barra dei filtri attivi](manage-annotations.md#active-filter-bar).


## Modificare le annotazioni

Puoi modificare un’annotazione in due modi:

* In un progetto Workspace, utilizza l’icona [Informazioni componenti](/help/analyze/analysis-workspace/components/use-components-in-workspace.md#component-info).

* Nell’elenco [[!UICONTROL Annotations] &#x200B;](#annotations-list), seleziona il titolo dell’annotazione.

Per modificare l’annotazione utilizza il [Generatore di annotazioni](/help/analyze/analysis-workspace/components/annotations/create-annotations.md#annotation-builder).

## Condividere le annotazioni

Quando si condividono annotazioni o si utilizzano annotazioni condivise con l’utente, si applica quanto segue:

* Le annotazioni di sola progettazione in un progetto condiviso con altri utenti vengono visualizzate per tali utenti. Gli utenti non possono modificare o eliminare queste annotazioni di sola progettazione.
* Se salvi un’annotazione e la condividi direttamente con un utente, l’utente può modificarla o eliminarla solo se dispone dei diritti di amministratore.

* Se un progetto è condiviso con te, le annotazioni create in quel progetto vengono visualizzate solo in tale progetto. Se un’annotazione viene condivisa direttamente con te, l’annotazione viene visualizzata in tutti i progetti in cui è possibile visualizzarla.

## Annotazioni e fusi orari

Tutte le annotazioni vengono create con una marca temporale, ma senza informazioni relative all’ora o al fuso orario. Al momento del rapporto, viene utilizzato il fuso orario della suite di rapporti configurata per il pannello.


<!--
# Manage annotations

The [!UICONTROL Annotations manager] shows you all of the annotations that you own or that have been shared with you. Project-specific annotations do not appear here. You can use this interface to share, filter, tag, copy, delete, and favorite your annotations. Administrators can manage and approve annotations.

**[!UICONTROL Components]** > **[!UICONTROL Annotations]**

## Annotations Manager user interface

![](assets/annotation-mgr.png)

| UI Element | Description |
| --- | --- | 
| [!UICONTROL Title and Description] | Provided in the Annotations Builder. To edit the title and description, click the title link - this takes you back to the Annotations Builder.  |
| [!UICONTROL Report Suite] | The report suites that this annotation applies to.  | 
| [!UICONTROL Owner] | Indicates who owns the annotation. As a non-Admin, you can see only annotations that you own or those that were shared with you. |
| [!UICONTROL Applied Date Range] | The date or date range that this annotation applies to. |
| [!UICONTROL Shared with] | Lists how many individuals or groups that you shared the annotation with. Click for more detail. |
| [!UICONTROL Date Modified] | Shows the date and time that the annotation was last modified. |

{style="table-layout:auto"}

## Edit annotations

Editing an annotation means that you can adjust date ranges, colors, scope, or whether it applies to all report suites or projects. You can edit annotations in two ways:

* In a line chart, hover over the annotation and click the pencil icon within the popover.
* In the [!UICONTROL Annotations Manager], click the title of the annotation.

Both of these options land you back in the [!UICONTROL Annotations Builder]. There, you can make the necessary adjustments and save the new version.

## Share annotations

When sharing annotations or working with annotations that were shared with you, keep this in mind:

* If you create a project with project-only annotations, then share the project with another user, annotations cannot be edited or deleted by anyone that you share the project with.
* If you save an annotation and share it directly with a user, they can edit/delete the annotation only if they have admin rights.
* If a project is shared with you with a project-only annotation, it shows up only in that project. If the annotation is shared directly with you, it shows up in all projects where that annotation can be displayed. 

## Annotations and time zones

All annotations are created with a timestamp, but no hours or timezone information. At report time, the timezone of the panel's report suite is always applied. For example, an annotation created for Christmas Day happens on December 25 no matter what report suite timezone you are in. 

## Other annotation tasks

The Annotations manager lets Administrators edit, add, tag, delete, rename, approve, copy, export, and filter annotations. It is not visible to non-Admin users. 

Additional options are available when you select at least one annotation:

| Task | Description |
| --- | --- |
| [!UICONTROL Add] | Takes you to the Annotations builder where you can create annotations. |
| [!UICONTROL Tag] | All users can create tags for annotations and apply one or more tags to an annotation. However, you can see tags only for annotations that you own. |
| [!UICONTROL Delete] | Deleting an annotation removes it from any project in your organization. |
| [!UICONTROL Rename] | Renaming an annotation renames it in all projects that it was applied to. |
| [!UICONTROL Copy] | Creates a distinct copy with its own annotation ID, but with the same name and definition.|
| [!UICONTROL Export to CSV] | Export the annotation definition to a .csv file.|
| [!UICONTROL Filter] (left rail) | Filter by tags, report suite, owners, and other filters (Mine, Approved, Favorites, Shared with me, and Show All).|

{style="table-layout:auto"}

-->