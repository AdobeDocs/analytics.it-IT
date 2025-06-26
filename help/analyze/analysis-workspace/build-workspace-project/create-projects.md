---
description: Scopri le nozioni di base sulla creazione di un progetto in Analysis Workspace
title: Creare progetti
feature: Workspace Basics
role: User, Admin
exl-id: 24193013-1361-43fc-b129-c44f207d9101
source-git-commit: 2bfc9c1d38957c997e78ee7d6a9550d173063109
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 92%

---

# Creare progetti {#create-projects}


I [progetti](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace consentono di creare e visualizzare le analisi business-critical.  Queste analisi possono essere condivise con gli stakeholder all’interno o all’esterno dell’organizzazione.

1. In Adobe Analytics, selezionare **[!UICONTROL Workspace]**.

1. Seleziona **[!UICONTROL Projects]** nel pannello a sinistra, quindi seleziona **[!UICONTROL Create project]**.

1. Seleziona **Progetto Workspace vuoto** per creare il tuo progetto Workspace utilizzando un browser.

   Consulta [Scorecard per dispositivi mobili vuota](/help/analyze/mobile-app/curator.md) per ulteriori informazioni su come creare un progetto di scorecard per dispositivi mobili che puoi condividere con altre parti interessate utilizzando un&#39;app per dispositivi mobili.

1. Seleziona [!UICONTROL **Crea**].


Dopo aver creato un progetto Workspace vuoto, assicurati di avere familiarità con l’interfaccia utente di [Analysis Workspace](/help/analyze/analysis-workspace/home.md). Una volta acquisita la familiarità necessaria, puoi creare il progetto. A tale scopo, effettua le seguenti operazioni:

![Progetto di esempio](assets/example-project.png)

* Aggiungi dei [pannelli](/help/analyze/analysis-workspace/c-panels/panels.md) al progetto. Ad esempio, **[!DNL Example Panel]** ➊.

* Aggiungi [visualizzazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ai pannelli. Ad esempio:
   * **[!DNL Line]** Visualizzazione [a linee](/help/analyze/analysis-workspace/visualizations/line.md) ➋
   * **[!DNL US States]** Visualizzazione [tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) ➌
* Aggiungi [componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) alle visualizzazioni. Ad esempio:
   * **[!DNL US States]** [Dimensione](/help/components/dimensions/overview.md) ➍
   * **[!DNL Unique Visitors]** [Metrica](/help/analyze/analysis-workspace/components/apply-create-metrics.md) ➎
   * **[!DNL Average Revenue Per Order]** [Metrica calcolata](/help/components/c-calcmetrics/cm-overview.md) ➏
   * **[!DNL Visits from Mobile Devices]** [Segmento](/help/components/segmentation/seg-overview.md) ➐
   * **[!DNL Last Month]** [Intervallo di date](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) ➑
   * **[!DNL Example]** [Annotazione](/help/analyze/analysis-workspace/components/annotations/overview.md) ➒


## Informazioni e impostazioni progetto {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Conta istanze ripetute"
>abstract="Specifica se le istanze ripetute vengono conteggiate o meno nei rapporti.<br/><br/>Nota: questa impostazione non si applica alle visualizzazioni Flusso o Fallout."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Conta istanze ripetute"
>abstract="Specifica se le istanze ripetute vengono conteggiate o meno nei rapporti.<br/>Nota: questa impostazione non si applica alle visualizzazioni Flusso o Fallout."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Consenti commenti"
>abstract="Quando questa opzione è abilitata, nella barra a destra del progetto in Analysis Workspace è disponibile un’area commenti."


Impostazioni progetto offre informazioni a livello di progetto sul progetto attualmente attivo.

![Finestra Informazioni e impostazioni progetto.](./assets/projectinfo.png)

Le impostazioni includono:

| Impostazione | Descrizione |
|---|---|
| Nome progetto | Nome assegnato al progetto. Puoi fare doppio clic sul nome per modificarlo. |
| Proprietario | Nome del proprietario del progetto. |
| Ultima modifica | Data dell’ultima modifica apportata al progetto. |
| Tag | Elenca eventuali tag applicati a un progetto per facilitarne la categorizzazione. |
| Descrizione | La descrizione è utile per chiarire lo scopo di un progetto. Puoi fare doppio clic sulla descrizione per modificarla. |
| Conta istanze ripetute | Specifica se le istanze ripetute sono conteggiate o meno nei rapporti. Nota: questa impostazione non si applica alle visualizzazioni Flusso o Abbandono. |
| Mostra annotazioni | Specifica se le annotazioni per questo progetto sono visualizzate o meno. |
| [Palette dei colori del progetto](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md) | Per cambiare la palette di colori utilizzata per le categorie in Workspace, puoi scegliere una delle palette predefinite ottimizzate per il daltonismo o specificarne una personalizzata. Questa funzione interessa numerosi elementi in Workspace, compresa la maggior parte delle visualizzazioni. |
| [Densità di visualizzazione](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | Consente di visualizzare più dati nella schermata riducendo la spaziatura verticale del pannello a sinistra, delle tabelle a forma libera e delle tabelle a coorte. |



<!--
# Create projects in Analysis Workspace

[Projects](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace allow you to view business-critical analyses that can be shared with stakeholders inside or outside your organization. 

For general information about how to get started using Analysis Workspace, see [Analysis Workspace overview](/help/analyze/analysis-workspace/home.md).

The following sections describe how to create a project and start adding the key building blocks for any Analysis Workspace project: panels, visualizations, and components.

## Create a project from a blank project or a report

1. In Adobe Analytics, select [!UICONTROL **Workspace**].

1. Choose whether to create a blank project or to create a project from a report:

   +++Create a blank project

   1. On the [!UICONTROL **Workspace**] tab, select the [!UICONTROL **Projects**] tab on the left side of the page, then select [!UICONTROL **Create project**].

   1. Choose whether to create a blank project or a blank mobile scorecard

      * **Blank project** if you plan to share your analysis from the browser 
      * [**Blank mobile scorecard**](/help/analyze/mobile-app/curator.md) if you plan to share your analysis from the Adobe Analytics dashboards mobile app.

   1. Select [!UICONTROL **Create**].

   +++

   +++Create a project from a report
   
      1. On the [!UICONTROL **Workspace**] tab, select the [!UICONTROL **Reports**] tab on the left side of the page.

      1. Search for or navigate to the report you want to use, then select it when it appears.

          A set of standard reports is available by default. In addition, your organization might have created custom reports for you to choose from.
          
      1. Select [!UICONTROL **Project**] > [!UICONTROL **Save**] to save the report as a new project.

          For more information about reports, see "Navigate the Reports tab" in [Adobe Analytics landing page](/help/analyze/landing.md).

   +++

1. Next, you need to add panels, visualizations, and components to your project. First, add panels to your project in Analysis Workspace, as described in [Add panels to the project](#add-panels-to-the-project). You can then add visualizations to any panels. Finally, you can add components to any panels or visualizations.

## Add panels to the project {#panels}

[Panels](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html) are the foundation to any project in Analysis Workspace. Panels are used to organize the content (visualizations and components) of a project. 

Many of the panels provided in Analysis Workspace generate a full set of analyses based on a few user inputs. 

To add a panel:

1. Select the [!UICONTROL **Panels**] icon in the left rail.

   ![](assets/build-panels.png)

1. Search for the panel you want to add. When it appears in the left rail, drag it into your project.

1. Add visualizations to your panel, as described in [Add visualizations to the project](#add-visualizations-to-the-project). 

   Alternatively, you can add components directly to a panel, as described in [Add components to the project](#add-components-to-the-project).

## Add visualizations to the project

[Visualizations](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) (such as a freeform table, a bar chart, or a line chart) can be used to visually bring data to life. 

>[!TIP]
>
>Freeform tables are the most common type of visualization, and are the foundation for interactive data analysis. For more details about how to work with Freeform tables in Analysis Workspace, see [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md).

To add a visualization:

1. Select the **[!UICONTROL Visualizations]** icon in the left rail.

   ![](assets/build-visualizations.png)

1. Search for the visualization you want to add. When it appears in the left rail, drag it to a panel within your project. 

1. Add components to the visualization, as described in [Add components to the project](#add-components-to-the-project).

## Add components to the project

[Components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) make up the actual data of any project. You can add components to visualizations or to panels.

>[!TIP]
>
>For information about each component, select the Info icon next to a component's name in the left rail, or see the [Analytics Components Guide](/help/components/home.md).

Following is basic information about how to add a component to a project in Analysis Workspace. For more detailed information about adding the various types of components (dimensions, metrics, segments, and date ranges), see [Use components in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

To add a component to a project in Analysis Workspace:

1. Select the **[!UICONTROL Components]** icon in the left rail.

   ![](assets/build-components.png)

1. Scroll to or search for the component you want to add, then drag it to a panel or visualization within your project. 

   For example, you can drag a segment to the segment drop zone in a panel header.

   ![drop a segment in the drop zone](assets/segment-dropzone.png)

   For more information about adding components to projects, see [Use components in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

1. (Optional) Share the project as described in [Save and share the project](#save-and-share-the-project).

## Save and share the project

As you create an analysis in Analysis Workspace, your work is [automatically saved](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). 

When you finish building out the project and it's gathering actionable insights, the project is ready to be consumed by others. You can share the project with users and groups in your organization, or even with people outside your organization. For information about sharing a project, see [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md).
-->