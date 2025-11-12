---
description: 'Scopri come utilizzare i progetti in Analysis Workspace. Utilizza Gestione progetti per gestire i progetti: puoi crearli, eliminarli, spostarli, condividerli, approvarli, fissarli, copiarli e assegnarvi dei tag.'
keywords: Analysis Workspace
title: Panoramica dei progetti
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1541'
ht-degree: 91%

---

# Panoramica dei progetti

Con i progetti Workspace puoi combinare pannelli, visualizzazioni e componenti per preparare analisi da condividere con altri utenti nella tua organizzazione. Prima di iniziare il tuo primo progetto, scopri come poter accedere ai progetti, gestirli e sportarti al loro interno.

Per accedere ai progetti in Adobe Analytics, selezionare **[!UICONTROL Workspace]**.  Gestione **[!UICONTROL Projects]** elenca tutti i progetti di tua proprietà o che sono stati condivisi con te. Il Project manager con l’elenco Progetto è anche la pagina di destinazione predefinita per Adobe Analytics, a meno che tu non abbia configurato diversamente in Preferenze.

![Pagina di destinazione Progetti con l’elenco dei progetti.](assets/projects.png)


## Area del titolo

Dall’area del titolo ➊ puoi creare un progetto o una cartella, modificare le preferenze e mostrare o nascondere un pannello con sezioni aggiuntive.

* Per mostrare o nascondere un pannello a sinistra che consente di selezionare tra **[!UICONTROL Projects]** e **[!UICONTROL Learning]**, seleziona ![Barra](/help/assets/icons/Rail.svg).
* Il titolo mostra Progetti, a cui può essere aggiunto un percorso alla cartella selezionata. Ad esempio: [!UICONTROL Projects] > **[!UICONTROL Company Folder]**. Selezionando una singola sottocartella, puoi passare direttamente alla cartella desiderata.
* Per visualizzare i riquadri per [**[!UICONTROL Blank project]**](create-projects.md), [**[!UICONTROL Blank mobile scorecard]**](/help/analyze/mobile-app/create-scorecard.md), **[!UICONTROL Open the documentation]** e **[!UICONTROL Open release notes]**, selezionare ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Show more]**. Per nascondere l’area con i riquadri, seleziona ![ChevronDown](/help/assets/icons/ChevronDown.svg)**[!UICONTROL Show less]**.
* In base a quello che hai scelto di visualizzare, utilizzando il selettore [Mostra](#show-selector) puoi modificare le preferenze ed eseguire azioni sulla cartella corrente visibile in **[!UICONTROL Projects]**:

  | Azione | Descrizione |
  |---|---|
  | **[!UICONTROL Create project]** | Seleziona per [creare un nuovo progetto](create-projects.md). |
  | **[!UICONTROL Create folder]** | Seleziona per [creare una nuova cartella](workspace-folders/create-folders.md). |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Edit preferences]** | [Modifica le preferenze](/help/analyze/analysis-workspace/user-preferences.md) per tutti i tuoi progetti. Quando la breadcrumb restituisce uno spazio limitato, questa azione fa parte del sottomenu ![Altro](/help/assets/icons/More.svg). |
  | **[!UICONTROL Add projects]** | Seleziona per [aggiungere progetti](workspace-folders/add-projects.md) alla cartella corrente. Quando la breadcrumb restituisce uno spazio limitato, questa azione fa parte del sottomenu ![Altro](/help/assets/icons/More.svg). |
  | **[!UICONTROL Rename folder]** | [Rinomina](workspace-folders/manage-folders.md#rename-folders) la cartella corrente. |
  | **[!UICONTROL Move folder]** | [Sposta](workspace-folders/manage-folders.md#move-folders) la cartella corrente. |
  | **[!UICONTROL Delete folder]** | [Elimina](workspace-folders/manage-folders.md#delete-folders) la cartella corrente. |




## Elenco dei progetti


L’elenco progetti ➋ mostra tutti i progetti di tua proprietà e che sono stati condivisi con te. L’elenco dispone delle seguenti colonne:

| Colonna | Descrizione |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Se sono selezionati uno o più progetti, nella parte bassa dell’interfaccia Progetti viene visualizzata una barra blu delle azioni. Per ulteriori dettagli, consulta [Azioni](#actions). |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Seleziona per contrassegnare come preferito ![Star](/help/assets/icons/Star.svg) o non preferito ![StarOutline](/help/assets/icons/StarOutline.svg) un progetto. |
| **[!UICONTROL Title and description]** | Per modificare il progetto, seleziona il collegamento del titolo, che apre il [progetto Workspace](/help/analyze/analysis-workspace/home.md). I progetti condivisi con te sono contrassegnati con l’icona ![Condividi](/help/assets/icons/ShareAlt.svg). Seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per visualizzare un menu popup con ulteriori dettagli sul progetto. Seleziona ![Altro](/help/assets/icons/More.svg) per aprire un menu di scelta rapida con alcune azioni. Per ulteriori dettagli, consulta [Azioni](#actions). |
| **[!UICONTROL Type]** | Un progetto Workspace, una cartella ![FolderUser](/help/assets/icons/FolderUser.svg) o una [scorecard per dispositivi mobili](/help/analyze/mobile-app/home.md). |
| **[!UICONTROL Tags]** | I tag applicati al progetto. |
| **[!UICONTROL Scheduled]** | Indica se un progetto è programmato per essere inviato tramite e-mail ai destinatari. Le opzioni sono ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL On]** o ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Off]**. Consulta [Inviare dati di progetto ad altri](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| **[!UICONTROL Shared link (anyone)]** | Se un progetto è condiviso con altri, anche con persone che non hanno accesso ad Analysis Workspace. Le opzioni sono ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Active]** o ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Inactive]**. Consulta [Condividere un progetto con qualcuno (accesso non richiesto)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) in [Condividere i progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md) per ulteriori informazioni. |
| **[!UICONTROL Project Role]** | Il tuo ruolo nel progetto. Le opzioni sono: Modifica, Duplica, Visualizza. Consulta [Ruoli di progetto](/help/analyze/analysis-workspace/curate-share/curate.md) per ulteriori informazioni. |
| **[!UICONTROL Report Suite]** | La suite di rapporti a cui è associato il progetto. |
| **[!UICONTROL Owner]** | Autore del progetto (tu o l’utente che ha condiviso con te il progetto). |
| **[!UICONTROL Shared with]** | Utenti con cui il progetto è stato condiviso. |
| **[!UICONTROL Last Modified]** | Data e ora dell’ultima volta che il progetto è stato modificato. |
| **[!UICONTROL Last Opened]** | Data e ora dell’ultima apertura del progetto. |
| **[!UICONTROL Component ID]** | ID del componente. |
| **[!UICONTROL Longest Date Range]** | L’intervallo di date più lungo tra i pannelli o le visualizzazioni del progetto. |
| **[!UICONTROL Number of Queries]** | Il numero totale di query contenute nel progetto. |
| **[!UICONTROL Location]** | La cartella in cui risiede il progetto. |

Passa il puntatore su un’intestazione di colonna per visualizzare ![ChevronDown](/help/assets/icons/ChevronDown.svg) e seleziona dal menu di scelta rapida:

* **[!UICONTROL Sort Ascending]**
* **[!UICONTROL Sort Descending]**
* **[!UICONTROL Resize column]**. Viene visualizzata una linea blu che ti aiuta a ridimensionare la colonna.

### Azioni

Puoi eseguire azioni su uno o più progetti utilizzando il menu di scelta rapida ![Altro](/help/assets/icons/More.svg) o la barra delle azioni blu.

| Icona | Azione | Descrizione |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selezionato]** | Deseleziona i progetti e le cartelle selezionati e rimuovi la barra blu delle azioni. |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina uno o più progetti o cartelle. Viene richiesta una conferma. <p>I progetti eliminati:</p><ul><li>Non possono essere recuperati</li><li>Vengono rimossi dall’elenco dei progetti</li><li>Non è più possibile accedervi con il rispettivo URL</li><li>Non sono più inclusi nelle consegne pianificate, nei casi in cui erano precedentemente configurate per le consegne pianificate<br/>Per informazioni sulle consegne pianificate, consulta [Progetti pianificati](/help/components/scheduled-projects-manager.md).  </p> |
| ![Condividi](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Share]** | Condividi un progetto. Per ulteriori informazioni, consulta [Condividere un progetto](/help/analyze/analysis-workspace/curate-share/share-projects.md). |
| ![Modifica](/help/assets/icons/Edit.svg) | **[!UICONTROL Rename]** | Rinomina un progetto. Si apre una finestra di dialogo **[!UICONTROL Rename: *del nome del progetto *]**. Immetti un nuovo nome e seleziona **[!UICONTROL Save]**. |
| ![Copia](/help/assets/icons/Copy.svg) | **[!UICONTROL Copy]** | Copia uno o più progetti. Al progetto vengono assegnati lo stesso nome e suffisso `(Copy)`. |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL Pin]** o **[!UICONTROL Unpin]** | Fissa o sposta uno o più progetti o cartelle. I progetti e le cartelle fissati vengono visualizzati nella parte superiore dell’elenco e ignorano l’ordinamento specificato. |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL Move up]** | Sposta un progetto o una cartella fissati verso l’alto nell’elenco dei progetti. |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL Move down]** | Sposta un progetto o una cartella fissati verso il basso nell’elenco dei progetti. |
| ![Etichetta](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Consente di assegnare tag a uno o più progetti o cartelle. Viene visualizzata la finestra di dialogo **[!UICONTROL Tag Components]** in cui è possibile selezionare uno o più tag. Seleziona **[!UICONTROL Save]** per salvare i tag per i progetti o le cartelle selezionate. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Approve]** o **[!UICONTROL Unapprove]** | Consente di approvare o annullare l’approvazione di un progetto. Solo gli amministratori possono approvare i progetti. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Export CSV]** | Consente di esportare i progetti selezionati in un file CSV denominato `Project List.csv`. |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL Add Projects]** | Consente di aggiungere uno o più progetti a una cartella selezionata. In **[!UICONTROL Add Projects]** è possibile selezionare uno o più progetti. Seleziona **[!UICONTROL Add]** per aggiungere i progetti alla cartella. Per ulteriori informazioni, consulta [Aggiungere progetti alle cartelle](workspace-folders/add-projects.md#from-inside-a-folder). |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL Move to]** | Consente di spostare in una cartella uno o più progetti selezionati. In **[!UICONTROL Select Folder]** seleziona la cartella in cui spostare il progetto selezionato e seleziona **[!UICONTROL Move]**. Per ulteriori informazioni, consulta [Aggiungere progetti alle cartelle](workspace-folders/add-projects.md#from-the-project-list). |



## Mostra selettore

Puoi cambiare il look and feel dell’interfaccia Progetti utilizzando i selettori **[!UICONTROL Show]** ➌. Il selettore **[!UICONTROL Show]** consente di definire le opzioni disponibili nell’[area del titolo](#title-area) e le colonne visualizzate nell’[elenco dei progetti](#project-list).

* Per modificare le opzioni disponibili per l’[area del titolo](#title-area), seleziona **[!UICONTROL Show]** **[!UICONTROL All projects]** o **[!UICONTROL Show]** **[!UICONTROL Folders & Projects]**.

* Per definire le colonne da visualizzare nell’[elenco dei progetti](#project-list), seleziona ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) e nella finestra di dialogo **[!UICONTROL Customize table]** seleziona o deseleziona le colonne desiderate. Seleziona **[!UICONTROL Apply]** per applicare la personalizzazione. Per ulteriori dettagli sulle colonne, consulta [Elenco dei progetti](#project-list).

## Pannello dei filtri

Puoi filtrare i progetti e le cartelle presenti nell’[elenco dei progetti](#project-list) utilizzando il pannello dei filtri ➍. Per mostrare o nascondere il pannello dei filtri, utilizza l’icona ![Filtro](/help/assets/icons/Filter.svg).

Il pannello dei filtri è costituito dalle sezioni seguenti.

### Tag

| Tag | Descrizione |
|---|---|
| ![Tag](assets/projects-filters-tags.png){width="300"} | La sezione **[!UICONTROL Tags]** consente di filtrare in base ai tag. <ul><li>Puoi utilizzare ![Ricerca](/help/assets/icons/Search.svg) *Ricerca tag* per cercare i tag in base ai quali applicare il filtro.</li><li>Puoi selezionare più di un tag. I tag disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**2︎⃣**: numero di tag disponibili per i progetti, risultanti dal filtro corrente.</li><li>7︎⃣: numero di progetti associati al tag specifico.</li></ul></li></ul> |


### Suite di rapporti

| Suite di rapporti | Descrizione |
|---|---|
| ![Suite di rapporti](assets/projects-filters-reportsuites.png){width="300"} | La sezione **[!UICONTROL Report Suites]** ti consente di filtrare in base alle suite di rapporti. <ul><li>Puoi utilizzare ![Cerca](/help/assets/icons/Search.svg) *Cerca suite di rapporti* per cercare le suite di rapporti che desideri utilizzare per filtrare.</li><li>Puoi selezionare più di una suite di rapporti. Le suite di rapporti disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**3︎⃣**: numero di suite di rapporti disponibili per i progetti risultanti dal filtro corrente.</li><li>4︎⃣: numero di progetti associati alla suite di rapporti specifica.</li></ul></li></ul> |


### Proprietari

| Proprietario | Descrizione |
|---|---|
| ![Proprietari](assets/projects-filters-owners.png){width="300"} | La sezione **[!UICONTROL Owner]** consente di filtrare in base ai proprietari. <ul><li>Puoi utilizzare ![Ricerca](/help/assets/icons/Search.svg) *Ricerca proprietari* per cercare i proprietari da utilizzare per filtrare.</li><li>Puoi selezionare più di un proprietario. I proprietari disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**3︎⃣**: numero di proprietari disponibili per i progetti, risultanti dal filtro corrente.</li><li>4︎⃣: numero di progetti associati al proprietario specifico.</li></ul></li></ul> |


### Tipo

| Tipo | Descrizione |
|---|---|
| ![Tipo](assets/projects-filters-type.png){width="300"} | La sezione **[!UICONTROL Type]** consente di filtrare in base al tipo di progetti o cartelle.<ul><li>È possibile scegliere una o più delle opzioni seguenti:<ul><li> **[!UICONTROL folder]**</li><li>**[!UICONTROL Workspace project]**</li><li>**[!UICONTROL Mobile scorecard]**</li></ul> <li>Puoi selezionare più di un altro filtro. Gli altri filtri disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**5︎⃣**: numero di altri filtri disponibili per i progetti risultanti dal filtro corrente.</li><li>4︎⃣: numero di progetti associati all’altro filtro specifico.</li></ul></li></ul> |


### Altri filtri

| Altri filtri | Descrizione |
|---|---|
| ![Altri filtri](assets/projects-filters-others.png){width="300"} | La sezione **[!UICONTROL Other filters]** ti consente di filtrare in base ad un altro filtro predefinito.<ul><li>È possibile scegliere una o più delle opzioni seguenti:<ul><li> **[!UICONTROL Show all]**</li><li>**[!UICONTROL Shared with me]**</li><li>**[!UICONTROL Mine]**</li><li>**[!UICONTROL Approved]**</li><li>**[!UICONTROL Favorites]**</li></ul> Ciò che puoi selezionare dipende dal tuo ruolo e dalle autorizzazioni.</li><li>Puoi selezionare più di un altro filtro. Gli altri filtri disponibili dipendono dalle selezioni effettuate in altre sezioni nel pannello dei filtri.</li><li>I numeri indicano:<ul><li>**5︎⃣**: numero di altri filtri disponibili per i progetti risultanti dal filtro corrente.</li><li>4︎⃣: numero di progetti associati all’altro filtro specifico.</li></ul></li></ul> |

## Ricerca

Utilizza l’area di ricerca ➎ per cercare progetti e cartelle utilizzando il campo ![Ricerca](/help/assets/icons/Search.svg). Inizia a digitare e l’[elenco progetti](#project-list) filtra automaticamente l’input della ricerca.

L’area Ricerca mostra anche i filtri applicati dal pannello Filtro.

* Per rimuovere un filtro, seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) nel filtro.
* Per rimuovere tutti i filtri, seleziona Cancella tutto.

Se lo spazio è limitato alla visualizzazione dei singoli filtri, visualizzerai **[!UICONTROL Segmenting by *x *filtri]**.

* Per rimuovere un filtro:

   1. Utilizza **[!UICONTROL *x *filtri]**![ChevronDown](/help/assets/icons/ChevronDown.svg) per aprire un menu di scelta rapida in cui sono elencati i tipi di filtri e i singoli filtri.
   1. Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un filtro.


<!--

# Projects overview

Workspace projects allow you to combine data components, tables and visualizations to craft your analysis and share with anyone in your organization. Before starting your first project, learn about how to access, navigate and manage your projects. 

Here is a video on how to build a Workspace project:


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Build a Workspace project](https://video.tv.adobe.com/v/334076?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Project list {#project-list}

When you first go to **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, the page lists all the projects you own or have been shared to you. This page is also the landing page for Adobe Analytics, unless you have previously set a custom landing page. 

The Projects page contains the following information: 

|  Element  | Description  |
|---|---|
| [Edit preferences](/help/analyze/analysis-workspace/user-preferences.md) | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create.  |
| [Create folder](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)  | Add a new folder or subfolder to the list of projects and folders. |
| [Create project](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)  | Start a new project from scratch or from a report.  |
|  Show more  | This selection reveals options for creating a blank project or mobile scorecard, [viewing training tutorials](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction), or [viewing release notes](/help/release-notes/latest.md).  |
| ![Show filters](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) | To show or hide filters. You can filter on tags, report suite, owners, type (project, folder, mobile scorecard), and other filters. |
| ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Use the search field to search for folders, Workspace projects or mobile scorecards. |
| Show Folders & Projects| Choose whether to show the folder structure of projects. For more information, see [About Folders in Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
|  ![Customize table](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) | This icon allows you to customize the columns you see for each project in the projects list.  |

The list of projects can display the following columns:

|  Column  | Description  |
|---|---|
| [!UICONTROL Name]  | Name of the Workspace project. Select ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) to show a popup with more details on a project or folder. Select ![More](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) to show actions available. See [Manage projects](#manage-projects) for more details.  |
| [!UICONTROL Type] | Indicates whether this entry is a Workspace project, a folder, or a [Mobile scorecard](/help/analyze/mobile-app/home.md). |
| [!UICONTROL Tags]  |Tags that were applied to the project.  |
| [!UICONTROL Scheduled] | Indicates whether projects are scheduled to be emailed to recipients. See [Schedule projects](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| Shared link (anyone) | Projects can be shared with anyone, even with people who don't have access to Analysis Workspace. This column shows whether projects have been shared in this way. See [Share a project with anyone (no login required)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md) for more information. |
| [Project Role](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Indicates your role for the project - owners, edit, duplicate, view. |
| [!UICONTROL Report suite] | The report suite that the project is associated with. |
| [!UICONTROL Owner]  | The person who created this project (either you or someone who shared the project with you.)  |
| [!UICONTROL Shared with]  | Users that the project has been shared with.  |
| [!UICONTROL Last Modified]  | Date and time when the project was last modified.  |
| [!UICONTROL Last Opened]  | Date and time when the project was last opened.  |
| [!UICONTROL Last Used] | Date and time when the project was last used. |
| [!UICONTROL Project ID]  | The ID of the project.  |
| [!UICONTROL Longest Date Range]  | The longest date range of the project.  |
| [!UICONTROL Number of Queries]  | The total number of queries contained in the project.  |
| [!UICONTROL Location]  | The folder where the project resides.  |

### Manage projects

To manage projects, select one or more projects from the project list. 

From the blue action bar, you can select the following actions:

| Action | Description |
|---|---|
| ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) Delete | When selected, a confirmation dialog prompts you to confirm the deletion of a Workspace project or Mobile scorecard. Select **[!UICONTROL OK]** to confirm. |
| ![Share](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg) Share | This action allows you to share your project. See [Share projects](../curate-share/share-projects.md).|
| ![Rename](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) Rename | Opens up a **[!UICONTROL Rename: *name*]** dialog to rename your project. Select **[!UICONTROL Save]** to save the new name for the project. |
| ![Copy](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) Copy | Immediately copies the selected project to a new project with name *original name* (Copy).  |
| ![Pin](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) Pin | Immediately pins the project to the top of the list. Adds the ![Pin](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) indicator. |
| ![Tag](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Label_18_N.svg) Tag | Opens up the **[!UICONTROL Tag Project]** dialog. You can select an existing tag or add new tags. Select **[!UICONTROL Save]** to save the tags for the project. |
| ![(Un-)Approve](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CheckmarkCircle_18_N.svg) Approve or Unapprove |  Approves or unapproves the project.  |
| ![Export CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) Export CSV | Immediately downloads a file containing a comma-separated value list of the projects. |
| ![Move to](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FolderAddTo_18_N.svg) Move to | This action allows you to move the project to a folder. In the **[!UICONTROL Select Folder]** dialog, select a folder from the **[!UICONTROL Folder]** list, and select **[!UICONTROL Move]**. |


## Menu bar {#menu-bar}

Within a project, the menu provides options for managing your project, adding components, finding help, and more. You can also access each menu option by keyboard [shortcuts](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).


|  Menu item  | Description  |
|---|---|
|  Project  | This menu includes common actions for project management, including New, Open, Save, Save as, and [Save as company report](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). You can also refresh the entire project to retrieve the most recent data and definitions by clicking Refresh Project. [Download CSV and PDF](/help/analyze/analysis-workspace/curate-share/download-send.md) options enable you to export data from Workspace. [Project Info & Settings](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) offers many options for managing your project.  |
|  Edit  | Undo or redo your last action. Clear All resets your project to a blank starting point. |
|  Insert  | Insert new panels or visualizations from this menu. You can also insert new panels and visualizations from the left rail.  |
|  [Components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)  | Create new segment, calculated metric, date range, or alert components from your project. You can also create new components from the left rail. If your component definitions have recently changed, Refresh Components retrieves the latest definitions. |
|  [Share](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md)  | Curate, share and schedule PDF/CSV projects to recipients in your organization.  |
|  Help  | Access help documentation, videos, and the Analytics [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Manage the visibility of Workspace tips as well as the [debugger](https://developer.adobe.com/analytics-apis/docs/2.0/). Find details about Workspace and factors that impact project [performance](/help/analyze/analysis-workspace/workspace-faq/optimizing-performance.md).  |
|  Share button or Owner  | If you are in an Own or Edit for the project, the Share button in the top-right gives you one-click access to manage your project recipients. If you are in a Duplicate or View role for the project, you see the project owner's name. |

### Project Info & Settings {#info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Count repeat instances"
>abstract="Specifies whether repeat instances are counted in reports.<br/><br/>Note: this setting does not apply to Flow or Fallout visualizations."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Count repeat instances"
>abstract="Specifies whether repeat instances are counted in reports.<br/>Note: this setting does not apply to Flow or Fallout visualizations."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Allow commenting"
>abstract="When enabled, a comments area is available in the right rail of the project in Analysis Workspace."



**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & settings]** provides project-level information on the currently active project.

![Project Info](assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project Name  | The name given to the project. You can double-click the name to edit it.  |
|  Owner  | Project owner name  |
|  Last Modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances  | Specifies whether repeat instances are counted in reports. For example, this setting (when activated) treats multiple consecutive pages views to the same page as multiple page views. With it off, they count as a single page view (this setting only affects certain metrics, such as Single Page Visits). **Note**: This setting does not apply to Flow or Fallout visualizations.  |
| [Show annotations](/help/analyze/analysis-workspace/components/annotations/overview.md) | Specify whether to show annotations in the project or not. |
|  [Project color palette](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | Lets you see more data on the screen by reducing the vertical padding of the left rail, freeform tables and cohort tables. |

## Left rail {#left-rail}

Within a project, various icons are available in the left rail, and each represents important tools to build your project:

| Icon | Functionality |
|---|---|
| ![panels icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg) | [Panels](/help/analyze/analysis-workspace/c-panels/panels.md) |
| ![visualizations icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphBarVertical_18_N.svg) |[Visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| ![components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) | [Components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| ![data dictionary icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Bookmark_18_N.svg) | [Data dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) |
| ![toc icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ViewList_18_N.svg) | [Table of contents](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) |

Components (dimensions, metrics, segments, date ranges) in the left rail relate to the active panel data view. A blue border identifies the active panel, and the active report suite is listed at the top of the component rail.


## Right-click menu

Here is a video on using the right-click menu in Analysis Workspace:


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Using the context menu](https://video.tv.adobe.com/v/23981?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Project canvas {#canvas}

The project canvas is where you bring together panels, tables, visualizations, and components to build your analysis. A project can contain many panels, and each panel can contain many tables and visualizations.

Panels are helpful when you want to organize your projects according to time periods, report suites, or analysis use case. The active panel has a colored border around it, and determines what components are available in the left rail.

Depending on the starting point you chose for your projects, you either have a [freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) or a [blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md) in the canvas to begin with. The quickest way to start analyzing is to select one or many components and simply drag & drop them into the project canvas. A table of data is rendered automatically for you. [Learn more](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) about the different options for building a table, or leverage the available [training tutorial](/help/analyze/analysis-workspace/home.md) for more guidance on building your first project.

![](assets/canvas.png)

-->