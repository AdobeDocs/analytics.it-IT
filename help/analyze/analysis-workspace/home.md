---
title: Panoramica di Analysis Workspace
description: Scopri Analysis Workspace, lo strumento di analisi principale per Adobe Analytics. Utilizza progetti, pannelli, tabelle, visualizzazioni e altri componenti per dare vita ai dati e per curare e condividere le analisi.
feature: Workspace Basics
role: User, Admin
exl-id: de95551d-09ea-4461-9bb4-b4ef235e9cd2
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1255'
ht-degree: 95%

---

# Panoramica di Analysis Workspace {#analysis-workspace-overview}

Analysis Workspace consente di realizzare rapidamente le analisi per raccogliere informazioni e quindi condividerle con altri utenti. Utilizzando l’interfaccia di trascinamento del browser, puoi creare analisi, aggiungere visualizzazioni per mettere in risalto i dati, curare un set di dati, condividere e pianificare [progetti](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) con chiunque desideri.

>[!BEGINSHADEBOX]

Per un video demo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panoramica di Analysis Workspace](https://video.tv.adobe.com/v/26266/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]

## Interfaccia

L’immagine seguente e la tabella associata illustrano gli elementi principali dell’interfaccia utente di Analysis Workspace:

![Finestra di Analysis Workspace che evidenzia le varie sezioni dell’interfaccia](assets/analysis-workspace-overview.png)

| Posizione | Nome e funzione |
|:---------:|----------|
| A | Contiene il nome del progetto, una struttura di menu per accedere alle funzionalità, un pulsante ![Indietro](/help/assets/icons/ChevronLeft.svg) per tornare all’elenco dei progetti e un pulsante **[!UICONTROL Share]** per [condividere il progetto Workspace](/help/analyze/analysis-workspace/curate-share/share-projects.md). <br/>Seleziona il nome del progetto (ad esempio: Nuovo progetto) in qualsiasi momento per modificare il nome. <br/>Seleziona ![Unfavor](/help/assets/icons/StarOutline.svg) per contrassegnare il progetto come progetto preferito ![Favor](/help/assets/icons/Star.svg). |
| B | **Pannello pulsanti:** contiene i pulsanti per accedere alle [funzionalità](#features) chiave di Analysis Workspace:<ul><li>![WebPage](/help/assets/icons/WebPage.svg) [[!UICONTROL Panels]](/help/analyze/analysis-workspace/c-panels/panels.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL Visualizations]](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![Cura](/help/assets/icons/Curate.svg) [[!UICONTROL Components]](/help/components/home.md)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL Table of contents]](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![Segnalibro](/help/assets/icons/Bookmark.svg) [[!UICONTROL Data Dictionary]](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **Pannello a sinistra:** quest’area contiene pannelli singoli, visualizzazioni, componenti o elenchi. Il contenuto dipende dal pulsante selezionato nel pannello pulsante. |
| D | **Area di lavoro:** area principale in cui trascini il contenuto dal pannello a sinistra per creare il progetto. Il progetto viene aggiornato dinamicamente quando aggiungi pannelli, visualizzazioni ai pannelli e componenti alle visualizzazioni. Puoi creare più pannelli e, all’interno di ogni pannello, creare più visualizzazioni.<br/>Ogni pannello si basa su una suite di rapporti selezionata. La suite di rapporti selezionata determina i componenti disponibili, come metriche e dimensioni. Per ulteriori informazioni, consulta [Pannelli - Suite di rapporti](/help/analyze/analysis-workspace/c-panels/panels.md#report-suite). |

## Funzioni

Le funzioni chiave di Analysis Workspace sono disponibili tramite il pannello pulsante:

| Icona | Funzione | Descrizione |
|:---:|---|---|
| ![WebPage](/help/assets/icons/WebPage.svg) | **[!UICONTROL Panels]** | I [pannelli](/help/analyze/analysis-workspace/c-panels/panels.md) servono per organizzare l’analisi all’interno di un progetto e possono contenere diverse tabelle e visualizzazioni. Molti dei pannelli forniti in Analysis Workspace generano un intero set di analisi basate su alcuni input dell’utente. |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL Visualizations]** | [Visualizzazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md), ad esempio un grafico a barre o a linee che può essere utilizzato per mettere visivamente in risalto i dati. Nel pannello all’estrema sinistra, seleziona l’icona **[!UICONTROL Visualizations]** centrale per ottenere l’elenco completo delle visualizzazioni disponibili. |
| ![Cura](/help/assets/icons/Curate.svg) | **[!UICONTROL Components]** | I [Componenti](/help/components/home.md) includono i seguenti elementi:<ul><li>![Dimensioni](/help/assets/icons/Dimensions.svg) [Dimensioni](/help/components/dimensions/overview.md)</li><li>![Evento](/help/assets/icons/Event.svg) [Metriche](/help/analyze/analysis-workspace/components/apply-create-metrics.md)</li><li>![Segmentazione](/help/assets/icons/Segmentation.svg) [Segmenti](/help/components/segmentation/seg-overview.md)</li><li>![Calendario](/help/assets/icons/Calendar.svg) [Intervalli di date](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL Table of contents]** | Il [sommario](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) organizza tutti i pannelli e le visualizzazioni inclusi nel progetto in un elenco comprimibile, consentendo di accedere rapidamente a un pannello o a una visualizzazione specifica. |
| ![Segnalibro](/help/assets/icons/Bookmark.svg) | **Dizionario dati** | Il [Dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) aiuta sia agli utenti che agli amministratori a tenere traccia e comprendere meglio i componenti nell’ambiente Analytics. |


## Menu

La maggior parte delle funzionalità di Analysis Workspace è disponibile tramite trascinamento e menu di scelta rapida all’interno di pannelli, visualizzazioni e componenti.

La funzionalità è anche disponibile tramite il menu di Workspace e i tasti di scelta rapida. I tasti di scelta rapida variano a seconda del sistema operativo su cui è in esecuzione il browser. Per una panoramica, consulta le seguenti tabelle.

Sulla tastiera possono essere utilizzati i seguenti simboli:

- **⇧** per **[!UICONTROL *Maiusc *]**.
- **⌘** per **[!UICONTROL *Comando *]**(comando).
- **⌃** per **[!UICONTROL *Ctrl *]**(controllo).
- **⌥** per **[!UICONTROL *Opzione *]**(opzione).
- **⎇** per **[!UICONTROL *Alt *]**(alternativo).

Per una panoramica dei menu disponibili, consulta le seguenti tabelle.

| **[!UICONTROL Project]** | Scelta rapida da tastiera per Mac | Scelta rapida da tastiera per Windows | Descrizione |
|---|---|---|---|
| **[!UICONTROL Create project]** | **[!UICONTROL *Maiusc+Comando+p *]** | **[!UICONTROL *Maiusc+Ctrl+p *]** | Crea un nuovo progetto. |
| **[!UICONTROL Create a mobile scorecard]** | | | [Crea una scorecard per dispositivi mobili](/help/analyze/mobile-app/create-scorecard.md). |
| **[!UICONTROL Open...]** | **[!UICONTROL *Comando+o *]** | **[!UICONTROL *Ctrl+o *]** | [Apri un progetto esistente](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-another-project). |
| **[!UICONTROL Open previous version...]** | **[!UICONTROL *Opzione+Comando+o *]** | **[!UICONTROL *Alt+Ctrl+o *]** | [Apri le versioni precedenti del progetto](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version). |
| **[!UICONTROL Save]** | **[!UICONTROL *Comando+s *]** | **[!UICONTROL *Ctrl+s *]** | [Salva il progetto](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-projects). |
| **[!UICONTROL Save with notes...]** | **[!UICONTROL *Opzione+Comando+s *]** | **[!UICONTROL *Alt+Ctrl+s *]** | [Aggiungi note alla versione del progetto salvata](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Save as...]** | **[!UICONTROL *Maiusc+Comando+s *]** | **[!UICONTROL *Maiusc+Ctrl+s *]** | [Salva il progetto utilizzando un nome e dettagli diversi](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Refresh project]** | **[!UICONTROL *Opzione+r *]** | **[!UICONTROL *Alt+r *]** | Aggiorna il progetto. |
| **[!UICONTROL Download CSV]** | **[!UICONTROL *Maiusc+Comando+v *]** | **[!UICONTROL *Maiusc+Ctrl+v *]** | Esporta il proggetto come file CSV. |
| **[!UICONTROL Download PDF]** | **[!UICONTROL *Maiusc+Comando+b *]** | **[!UICONTROL *Maiusc+Ctrl+b *]** | Scarica il progetto come documento PDF. |
| **[!UICONTROL Project info & settings]** | | | Definisci le impostazioni per i progetti, ad esempio nome, tag, palette di colori e altro ancora. |
| **[!UICONTROL User settings]** | | | [Configura le preferenze per l’utilizzo di Analysis Workspace](/help/analyze/analysis-workspace/user-preferences.md). |


| **[!UICONTROL Edit]** | Scelta rapida da tastiera per Mac | Scelta rapida da tastiera per Windows | Descrizione |
|---|---|---|---|
| **[!UICONTROL Undo]** | **[!UICONTROL *Comando+z *]** | **[!UICONTROL *Ctrl+z *]** | Annulla l’azione precedente. |
| **[!UICONTROL Redo]** | **[!UICONTROL *Comando+Maiusc+z *]** | **[!UICONTROL *Ctrl+Maiusc+z *]** | Ripristina l’azione precedente. |
| **[!UICONTROL Clear all]** | **[!UICONTROL *Opzione+w *]** | **[!UICONTROL *Alt+w *]** | Cancella tutti i pannelli nel progetto corrente. |

| **[!UICONTROL Insert]** | Scelta rapida da tastiera per Mac | Scelta rapida da tastiera per Windows | Descrizione |
|---|---|---|---|
| **[!UICONTROL Blank panel]** | **[!UICONTROL *Opzione+b *]** | **[!UICONTROL *Alt+b *]** | Inserisci un [pannello vuoto](/help/analyze/analysis-workspace/c-panels/blank-panel.md). |
| **[!UICONTROL Media concurrent viewers]** | **[!UICONTROL *Opzione+h *]** | **[!UICONTROL *Alt-h *]** | Inserisci un pannello [Visualizzatori simultanei contenuti multimediali](/help/analyze/analysis-workspace/c-panels/media-concurrent-viewers.md). |
| **[!UICONTROL Media playback time spent]** | **[!UICONTROL *Opzione+i *]** | **[!UICONTROL *Alt+i *]** | Inserisci un pannello [Tempo trascorso su contenuti multimediali](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md). |
| **[!UICONTROL Media average minute audience]** | **[!UICONTROL *Opzione+m *]** | **[!UICONTROL *Alt+m *]** | Inserisci un pannello per [Pubblico medio per minuto del file multimediale](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md). |
| **[!UICONTROL Attribution]** | **[!UICONTROL *Opzione+e *]** | **[!UICONTROL *Alt+e *]** | Inserisci un pannello [Attribuzione](/help/analyze/analysis-workspace/c-panels/attribution.md). |
| **[!UICONTROL Freeform]** | **[!UICONTROL *Opzione+a *]** | **[!UICONTROL *Alt+a *]** | Inserisci un pannello [A forma libera](/help/analyze/analysis-workspace/c-panels/freeform-panel.md). |
| **[!UICONTROL Quick insights]** | **[!UICONTROL *Opzione+j *]** | **[!UICONTROL *Alt+j *]** | Inserisci un pannello [Quick Insights](/help/analyze/analysis-workspace/c-panels/quickinsight.md). |
| **[!UICONTROL Freeform table]** | **[!UICONTROL *Opzione+1 *]** | **[!UICONTROL *Alt+1 *]** | Inserisci una visualizzazione [Tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). |
| **[!UICONTROL Line]** | **[!UICONTROL *Opzione+2 *]** | **[!UICONTROL *Alt+2 *]** | Inserisci una visualizzazione [A linee](/help/analyze/analysis-workspace/visualizations/line.md). |
| **[!UICONTROL Bar]** | **[!UICONTROL *Opzione+3 *]** | **[!UICONTROL *Alt+3 *]** | Inserisci una visualizzazione [A barre](/help/analyze/analysis-workspace/visualizations/bar.md). |
| **[!UICONTROL Combo]** | **[!UICONTROL *Opzione+4 *]** | **[!UICONTROL *Alt+4 *]** | Inserisci una visualizzazione [Combinato](/help/analyze/analysis-workspace/visualizations/combo-charts.md). |


| **[!UICONTROL Components]** | Scelta rapida da tastiera per Mac | Scelta rapida da tastiera per Windows | Descrizione |
|---|---|---|---|
| **[!UICONTROL Create segment...]** | **[!UICONTROL *Maiusc+Comando+e *]** | **[!UICONTROL *Maiusc+Ctrl+e *]** | Crea un nuovo [segmento](/help/components/segmentation/segmentation-workflow/seg-create.md). |
| **[!UICONTROL Create metric...]** | **[!UICONTROL *Maiusc+Comando+c *]** | **[!UICONTROL *Maiusc+Ctrl+c *]** | Crea una nuova [metrica calcolata](/help/components/calculated-metrics/cm-overview.md). |
| **[!UICONTROL Create date range...]** | **[!UICONTROL *Maiusc+Comando+d *]** | **[!UICONTROL *Maiusc+Ctrl+d *]** | Crea un nuovo [intervallo di date](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md). |
| **[!UICONTROL Create annotation...]** | **[!UICONTROL *Maiusc+Comando+o *]** | **[!UICONTROL *Maiusc+Ctrl+o *]** | Crea una nuova [annotazione](/help/analyze/analysis-workspace/components/annotations/overview.md). |
| **[!UICONTROL Refresh components]** | **[!UICONTROL *Opzione+Maiusc+r *]** | **[!UICONTROL *Alt+Maiusc+r *]** | Aggiorna i componenti nel progetto. |

| **[!UICONTROL Share]** | Scelta rapida da tastiera per Mac | Scelta rapida da tastiera per Windows | Descrizione |
|---|---|---|---|
| **[!UICONTROL Share with Workspace users]** | **[!UICONTROL *Comando+h *]** | **[!UICONTROL *Ctrl+h *]** | [Condividi il progetto con altri utenti di Workspace](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization). |
| **[!UICONTROL Share with anyone]** | **[!UICONTROL *Opzione+l *]** | **[!UICONTROL *Alt+l *]** | [Condividi una versione di sola lettura del progetto con un altro utente](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project). |
| **[!UICONTROL Send file]** | **[!UICONTROL opt+s]** | **[!UICONTROL *Alt+s *]** | [Invia il progetto come file CSV o PDF ad altri destinatari](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Schedule file export]** | **[!UICONTROL *Maiusc+Opzione+s *]** | **[!UICONTROL *Maiusc+Alt+s *]** | [Invia il progetto secondo una pianificazione come file CSV o PDF ad altri destinatari](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Curate project data]** | **[!UICONTROL *Maiusc+Comando+g *]** | **[!UICONTROL *Maiusc+Ctrl+g *]** | [Cura i dati del progetto](/help/analyze/analysis-workspace/curate-share/curate.md). |

| Aiuto | Descrizione |
|---|---|
| **[!UICONTROL Videos]** | Apri il canale YouTube di Customer Journey Analytics in una nuova scheda del browser. |
| **[!UICONTROL Help documentation]** | Apri la documentazione (quella che stai leggendo in questo momento) in una nuova scheda del browser. |
| **[!UICONTROL Help forum]** | Apri il forum delle community Experience League per Adobe Analytics in una nuova scheda del browser. |
| **[!UICONTROL Hotkeys]** | Mostra una panoramica dei tasti di scelta rapida che è possibile utilizzare in Workspace. |
| **[!UICONTROL Enable debugger]** | Abilita il debugger. Il progetto verrà ricaricato. |
| **[!UICONTROL Disable debugger]** | Disabilita il debugger. Il progetto verrà ricaricato. |
| **[!UICONTROL Performance]** | Mostra una finestra di dialogo che visualizza le metriche di **[!UICONTROL Analysis Workspace performance]**. Utilizza **[!UICONTROL Download as CSV]** per scaricare un file CSV delle metriche delle prestazioni. |
| **[!UICONTROL About Workspace]** | Mostra una finestra di dialogo **[!UICONTROL About Analysis Workspace]** con informazioni sulla versione, i livelli di accesso alle funzioni e i flag delle funzioni attivi. |

## Origini dati

Sincronizza le visualizzazioni per controllare quale tabella dati oppure origine dati corrisponde a una visualizzazione. Per ulteriori informazioni, consulta come [gestire le origini dati](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md).

## Utilizzare Analysis Workspace


Per iniziare a utilizzare Analysis Workspace:

1. Accedi ad [Adobe Experience Cloud](https://experience.adobe.com).
1. Seleziona **[!UICONTROL Customer Journey Analytics]** dal selettore di app ![App](/help/assets/icons/Apps.svg) in alto a destra nell’interfaccia.
1. La pagina **[!UICONTROL Projects]** di Analysis Workspace viene mostrata per impostazione predefinita. Se è stato selezionato per un progetto specifico o hai lavorato sul progetto di recente, questo viene mostrato per impostazione predefinita.

### Creare un progetto

Un’analisi in Analysis Workspace è definita come [progetto](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

Puoi creare un progetto in Analysis Workspace come descritto in [Creare progetti](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

I progetti possono essere organizzati in cartelle e sottocartelle, come descritto in [Cartelle in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Salvare e condividere un progetto

Quando crei un’analisi in Analysis Workspace, il lavoro viene [salvato automaticamente](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

Una volta che il progetto è stato completato e sta raccogliendo informazioni approfondite fruibili, altri potrebbero volerlo utilizzare. Puoi condividere il progetto con utenti e gruppi dell’organizzazione o anche con persone esterne a questa. Per informazioni sulla condivisione di un progetto, consulta [Condividere progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md).

## Risorse aggiuntive {#resources}

- Adobe offre centinaia di [tutorial di formazione video per Analytics](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/overview).
- Per aggiornamenti sulle nuove funzioni, consulta [Note sulla versione di Adobe Experience Cloud](https://experienceleague.adobe.com/it/docs/release-notes/experience-cloud/current).



<!--
# Analysis Workspace overview {#analysis-workspace-overview}

Analysis Workspace allows you to build analyses quickly to gather insights and then share those insights with others. Using the drag-and-drop browser interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, and share and schedule [projects](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) with anyone you choose.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis workspace overview](https://video.tv.adobe.com/v/26266/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Interface

The following image and accompanying table explain the main elements in the Analysis Workspace user interface:

![Analysis Workspace window highlighting the various sections of the interface](assets/analysis-workspace-overview.png)

| Location | Name and function |
|:---------:|----------|
| A | Contains the name of the project, a menu structure to access functionality, a button ![Back button](/help/assets/icons/ChevronLeft.svg) to return back to your Project list, and a **[!UICONTROL Share]** button to [share your Workspace project](/help/analyze/analysis-workspace/curate-share/share-projects.md). <br/>Select the name of your project (for example: New project) at any time to change the name. <br/>Select ![Unfavor](/help/assets/icons/StarOutline.svg) to mark your project as a favorite project ![Favor](/help/assets/icons/Star.svg). |
| B | **Button panel:** Contains buttons for accessing the key [features](#features) of Analysis Workspace:<ul><li>![WebPage](/help/assets/icons/WebPage.svg) [[!UICONTROL Panels]](/help/analyze/analysis-workspace/c-panels/panels.md)</li><li>![Guided Analysis](/help/assets/icons/GuidedAnalysis.svg) [[!UICONTROL Guided Analysis]](/help/guided-analysis/overview.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL Visualizations]](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![Curate](/help/assets/icons/Curate.svg) [[!UICONTROL Components]](/help/components/overview.md)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL Table of contents]](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![Bookmark](/help/assets/icons/Bookmark.svg) [[!UICONTROL Data Dictionary]](/help/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **Left panel:** This area contains individual panels, visualizations, components, or lists. The content depends on the button selected in the button panel.  |
| D | **Canvas:** The main area where you drag content from the left panel to build your project. The project dynamically updates as you add panels, add visualizations to panels, and add components to visualizations. You can create multiple panels, and within each panel you can create multiple visualizations.<br/>Each panel is based on a selected data view. The selected data view determines available components like metrics and dimensions. See [Panels - Data view](/help/analyze/analysis-workspace/c-panels/panels.md#data-view) for more information. |

## Features

The key features of Analysis Workspace are available through the button panel:

| Icon | Feature | Description |
|:---:|---|---|
| ![WebPage](/help/assets/icons/WebPage.svg) | **[!UICONTROL Panels]** | [Panels](/help/analyze/analysis-workspace/c-panels/panels.md) are used to organize your analysis within a project and can contain many tables & visualizations. Many of the panels provided in Analysis Workspace generate a full set of analyses based on a few user inputs. |
| ![Guided Analysis](/help/assets/icons/GuidedAnalysis.svg) | **[!UICONTROL Guided Analysis]** | [Guided analysis](../guided-analysis/overview.md) allows you to self-serve high quality data and insights about the customer journey through guided workflows. You can create an analysis for inclusion in your Workspace project, or include an existing analysis previously saved. |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL Visualizations]** | [Visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md), such as a bar or line chart, can be used to bring data visually to life. On the far left panel, select the middle **[!UICONTROL Visualizations]** icon to see the full list of visualizations available. |
| ![Curate](/help/assets/icons/Curate.svg) | **[!UICONTROL Components]** | [Components](/help/components/overview.md) include the following elements:<ul><li>![Dimensions](/help/assets/icons/Dimensions.svg) [Dimensions](/help/components/dimensions/overview.md)</li><li>![Event](/help/assets/icons/Event.svg) [Metrics](/help/components/apply-create-metrics.md)</li><li>![Segmentation](/help/assets/icons/Segmentation.svg) [Segments](/help/components/segments/seg-overview.md)</li><li>![Calendar](/help/assets/icons/Calendar.svg) [Date ranges](/help/components/date-ranges/overview.md)</li></ul> |
| ![ViewList](/help/assets/icons/ViewList.svg) | **[!UICONTROL Table of contents]** | The table of contents organizes all panels and visualizations included in the project into a collapsible list, allowing you to access a specific panel or visualization quickly. |
|![Bookmark](/help/assets/icons/Bookmark.svg) | **Data dictionary** | The [Data dictionary](/help/components/data-dictionary/data-dictionary-overview.md) helps both users and administrators keep track of and better understand the components in their Analytics environment. |


## Menu

Most of the functionality of Analysis Workspace is available through drag and drop, and trough context menus within panels, visualizations and components.

Functionality is also available through the Workspace menu and shortcuts or hotkeys. Shortcut keys differ depending on the operating system that your browser is running on. See the tables below for an overview.  

Note that on your keyboard the following symbols might be used:

- **⇧** for **[!UICONTROL *shift*]**.
- **⌘** for **[!UICONTROL *cmd*]** (command).
- **⌃** for **[!UICONTROL *ctrl*]** (control).
- **⌥** for **[!UICONTROL *opt*]** (option).
- **⎇** for **[!UICONTROL *alt*]** (alternate).

See the tables below for an overview of the available menus.  

| **[!UICONTROL Project]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Create project]** | **[!UICONTROL *shift+cmd+p*]** | **[!UICONTROL *shift+ctrl+p*]** | Create a new project. |
| **[!UICONTROL Create a mobile scorecard]** | | | [Create a new mobile scorecard](/help/mobile-app/create-scorecard.md). |
| **[!UICONTROL Open...]** | **[!UICONTROL *cmd+o*]** | **[!UICONTROL *ctrl+o*]** | [Open an existing project](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-another-project). |
| **[!UICONTROL Open previous version...]** | **[!UICONTROL *opt+cmd+o*]** | **[!UICONTROL *alt+ctrl+o*]** | [Open earlier versions of your project](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version). |
| **[!UICONTROL Save]** | **[!UICONTROL *cmd+s*]** | **[!UICONTROL *ctrl+s*]** | [Save your project](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-projects). |
| **[!UICONTROL Save with notes...]** | **[!UICONTROL *opt+cmd+s*]** | **[!UICONTROL *alt+ctrl+s*]** | [Add notes to the project version that you save](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Save as...]** | **[!UICONTROL *shift+cmd+s*]** | **[!UICONTROL *shift+ctrl+s*]** | [Save the project using a different name and details](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Refresh project]** | **[!UICONTROL *opt+r*]** | **[!UICONTROL *alt+r*]** | Refresh the project. |
| **[!UICONTROL Download CSV]** | **[!UICONTROL *shift+cmd+v*]** | **[!UICONTROL *shift+ctrl+v*]** | Download the project as a CSV file. |
| **[!UICONTROL Download PDF]**| **[!UICONTROL *shift+cmd+b*]** | **[!UICONTROL *shift+ctrl+b*]** | Download the project as a PDF document. |
| **[!UICONTROL Project info & settings]** | | | Define settings for your projects, such as name, tags, color palette, and more. |
| **[!UICONTROL User settings]** | | | [Configure preferences for using Analysis Workspace](/help/analyze/analysis-workspace/user-preferences.md). |


| **[!UICONTROL Edit]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Undo]** | **[!UICONTROL *cmd+z*]** | **[!UICONTROL *ctrl+z*]** | Undo the previous action. |
| **[!UICONTROL Redo]** | **[!UICONTROL *cmd+shift+z*]** | **[!UICONTROL *ctrl+shift+z*]** | Redo the previous action. |
| **[!UICONTROL Clear all]** | **[!UICONTROL *opt+w*]** | **[!UICONTROL *alt+w*]** | Clear all panels in the current project. |

| **[!UICONTROL Insert]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Blank panel]** | **[!UICONTROL *opt+b*]** | **[!UICONTROL *alt+b*]** |  Insert a [Blank panel](/help/analyze/analysis-workspace/c-panels/blank-panel.md). |
| **[!UICONTROL Media concurrent viewers]** | **[!UICONTROL *opt+h*]** | **[!UICONTROL *alt-h*]** |  Insert a [Media concurrent viewers](/help/analyze/analysis-workspace/c-panels/media-concurrent-viewers.md) panel. |
| **[!UICONTROL Media playback time spent]** | **[!UICONTROL *opt+i*]** | **[!UICONTROL *alt+i*]** |  Insert a [Media playback time spent](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) panel. |
| **[!UICONTROL Media average minute audience]** | **[!UICONTROL *opt+m*]** | **[!UICONTROL *alt+m*]** |  Insert a [Media average minute audience](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md) panel. |
| **[!UICONTROL Attribution]** | **[!UICONTROL *opt+e*]** | **[!UICONTROL *alt+e*]** |  Insert an [Attribution](/help/analyze/analysis-workspace/c-panels/attribution.md) panel. |
| **[!UICONTROL Freeform]** | **[!UICONTROL *opt+a*]** | **[!UICONTROL *alt+a*]** |  Insert a [Freeform](/help/analyze/analysis-workspace/c-panels/freeform-panel.md) panel. |
| **[!UICONTROL Quick insights]** | **[!UICONTROL *opt+j*]** | **[!UICONTROL *alt+j*]** |  Insert a [Quick insights](/help/analyze/analysis-workspace/c-panels/quickinsight.md) panel. |
| **[!UICONTROL Experimentation]** |**[!UICONTROL *opt+x*]** | **[!UICONTROL *alt+x*]** |  Insert an [Experimentation](/help/analyze/analysis-workspace/c-panels/experimentation.md) panel. |
| **[!UICONTROL Freeform table]** | **[!UICONTROL *opt+1*]** | **[!UICONTROL *alt+1*]**|  Insert a [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) visualization. |
| **[!UICONTROL Line]** | **[!UICONTROL *opt+2*]** | **[!UICONTROL *alt+2*]** |  Insert a [Line](/help/analyze/analysis-workspace/visualizations/line.md) visualization. |
| **[!UICONTROL Bar]** | **[!UICONTROL *opt+3*]** | **[!UICONTROL *alt+3*]** |  Insert a [Bar](/help/analyze/analysis-workspace/visualizations/bar.md) visualization. |
| **[!UICONTROL Combo]** | **[!UICONTROL *opt+4*]**| **[!UICONTROL *alt+4*]** |  Insert a [Combo](/help/analyze/analysis-workspace/visualizations/combo-charts.md) visualization. |


| **[!UICONTROL Components]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Create segment...]** | **[!UICONTROL *shift+cmd+e*]** | **[!UICONTROL *shift+ctrl+e*]** | Create a new [segment](/help/components/segments/seg-create.md). |
| **[!UICONTROL Create metric...]** | **[!UICONTROL *shift+cmd+c*]** | **[!UICONTROL *shift+ctrl+c*]** | Create a new [calculated metric](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Create date range...]** | **[!UICONTROL *shift+cmd+d*]** | **[!UICONTROL *shift+ctrl+d*]** | Create a new [date range](/help/components/date-ranges/overview.md). |
| **[!UICONTROL Create annotation...]** | **[!UICONTROL *shift+cmd+o*]** | **[!UICONTROL *shift+ctrl+o*]** | Create a new [annotation](/help/components/annotations/overview.md). |
| **[!UICONTROL Create audience...]** | **[!UICONTROL *shift+cmd+u*]** | **[!UICONTROL *shift+ctrl+u*]** | Create a new [audience](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Refewsh components]** | **[!UICONTROL *opt+shift+r*]** | **[!UICONTROL *alt+shift+r*]** | Refresh the components in the project. |

| **[!UICONTROL Share]** | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Share with Workspace users]** | **[!UICONTROL *cmd+h*]** | **[!UICONTROL *ctrl+h*]** | [Share the project with other Workspace users](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization). |
| **[!UICONTROL Share with anyone]** | **[!UICONTROL *opt+l*]** | **[!UICONTROL *alt+l*]**| [Share a read-only version of the project with anyone](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project). |
| **[!UICONTROL Send file]** | **[!UICONTROL opt+s]** | **[!UICONTROL *alt+s*]** | [Send the project as a CSV or PDF file to other recipients](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Schedule file export]** | **[!UICONTROL *shift+opt+s*]** | **[!UICONTROL *shift+alt+s*]** | [Send the project on a schedule as a CSV or PDF file to other recipients](/help/analyze/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Curate project data]** | **[!UICONTROL *shift+cmd+g*]** | **[!UICONTROL *shift+ctrl+g*]** | [Curate the project data](/help/analyze/analysis-workspace/curate-share/curate.md). |

| Help | Shortcut Mac | Shortcut Windows | Description |
|---|---|---|---|
| **[!UICONTROL Videos]** | | | Open the Customer Journey Analytics YouTube channel in a new browser tab. |
| **[!UICONTROL Help documentation]** | | | Open the documentation (you are actually reading just now...) in a new browser tab. |
| **[!UICONTROL Help forum]** | | | Open the Adobe Analytics Experience League communities forum in a new browser tab. |
| **[!UICONTROL Hotkeys]** | | | Show an overview of the hotkeys (shortcuts) you can use in Workspace. |
| **[!UICONTROL Enable debugger]** |  | | Enable the debugger. Your project will reload. |
| **[!UICONTROL Disable debugger]** | | | Disable the debugger. Your project will reload. |
| **[!UICONTROL Performance]** | | | Show a dialog displaying metrics on the **[!UICONTROL Analysis Workspace performance]**. Use **[!UICONTROL Download as CSV]** to download a CSV file of the performance metrics. |
| **[!UICONTROL About Workspace]** | | | Show an **[!UICONTROL About Analysis Workspace]** dialog with version information, feature access levels and active feature flags. |

## Data sources

You synchronize visualizations to control which data table or data source corresponds to a visualization. See [manage data sources](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md) for more information.

## Use Analysis Workspace


To start using Analysis Workspace: 

1. Log in to [Adobe Experience Cloud](https://experience.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** from the app switcher ![App](/help/assets/icons/Apps.svg) at the top right of the interface.
1. The **[!UICONTROL Projects]** page of Analysis Workspace is shown by default. If a specific project has been selected for you or you have been working on recently, then that project is shown by default.

### Create a project

An analysis in Analysis Workspace is referred to as a [project](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md). 

You can create a project in Analysis Workspace as described in [Create projects](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

Projects can be organized into folders and subfolders, as described in [Folders in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Save and share a project

As you create an analysis in Analysis Workspace, your work is [automatically saved](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). 

When you finish building out the project and it's gathering actionable insights, others might want to consume the project. You can share the project with users and groups in your organization, or even with people outside your organization. For information about sharing a project, see [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md).

## Additional resources {#resources}

- The [Learning landing](/help/getting-started/landing.md#learning) page in Customer Journey Analytics. This page is  great way to become acquainted with Analysis Workspace. Especially the Learning Workspace Fundamental. This template walks you through common terminology and steps for building your first analysis in Workspace
- Adobe offers hundreds of [Analytics video training tutorials](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/overview).
- See [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/it/docs/release-notes/experience-cloud/current) for updates about new features.



<!--
# Analysis Workspace overview

Analysis Workspace allows you to quickly build analyses to gather insights and then share those insights with others. Using the drag-and-drop browser interface, you can craft your analysis, add visualizations to bring data to life, curate a dataset, and share and schedule projects with anyone you choose.

The following video provides a brief overview with examples of what is possible.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace overview](https://video.tv.adobe.com/v/26266/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Areas of Analysis Workspace

The following image and accompanying table explain some of the main areas in Analysis Workspace:

![Analysis Workspace overview](assets/analysis-workspace-overvew.png)

| Location in image | Name and function |
|---------|----------|
| A | **Far left rail:** Contains tabs for adding panels, visualizations, and components to Analysis Workspace. Also contains the Data Dictionary icon that is used to open the Data Dictionary. |
| B | **Left rail:** Depending on which tab is selected in the far left rail, this area contains individual panels, visualizations, or components. |
| C | **Canvas:** This is the main area where you drag content from the left rails to build your project. The project dynamically updates as you add panels, visualizations, and components to the canvas. |
| D | **Report suite drop-down menu:** For each panel in Analysis Workspace, the report suite drop-down menu allows you to choose the report suite that you want to use as your data source. |

## Features in Analysis Workspace {#analysis}

Following are some of the key features available in Analysis Workspace: 

### Panels

**Panels** are used to organize your analysis within a project and can contain many tables & visualizations. Many of the panels provided in Analysis Workspace generate a full set of analyses based on a few user inputs. On the far left rail, select the top **[!UICONTROL Panels]** icon to see a full list of panels available.

To learn more about panels, see [Panels overview](/help/analyze/analysis-workspace/c-panels/panels.md).

![](assets/build-panels.png)

### Visualizations

**Visualizations**, such as a bar or line chart, can be used to visually bring data to life. On the far left rail, select the middle **[!UICONTROL Visualizations]** icon to see the full list of visualizations available. 

To learn more about visualizations, see [Visualizations overview](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

![](assets/build-visualizations.png)

### Components

Components in Analysis Workspace consist of the following:

* Dimensions

* Metrics

* Segments

* Date ranges

To learn more about each of these component types, see [Components overview](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). 

Each of these component types can be added to a visualization (such as a Freeform table) to start answering your business questions. 

After you understand component terminology, you can drag components into visualizations (including Freeform tables) to [build your analysis](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

![](assets/build-components.png)

### Data Dictionary

The Data Dictionary in Analysis Workspace helps both users and administrators keep track of and better understand the components in their Analytics environment.

To learn more about the Data Dictionary, see [Data Dictionary overview](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

### Data Sources

Synchronizing visualizations lets you control which data table or data source corresponds to a visualization. Here is more information on how you can [manage data sources](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md).

## Start using Analysis Workspace

### Log in to Adobe Analytics {#login}

To start using Analysis Workspace, log in to Adobe Analytics by going to [experience.adobe.com/analytics](https://experience.adobe.com/analytics). The Projects page of Analysis Workspace is shown by default. If a specific project has been selected for you, that project is shown by default.

### Create a project {#new-project}

An analysis in Analysis Workspace is referred to as a [project](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).  

You can create a project in Analysis Workspace as described in [Create projects](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

Projects can be organized into folders and subfolders, as described in [Folders in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Save and share a project

As you create an analysis in Analysis Workspace, your work is [automatically saved](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). 

When you finish building out the project and it's gathering actionable insights, the project is ready to be consumed by others. You can share the project with users and groups in your organization, or even with people outside your organization. For information about sharing a project, see [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md).

## Additional resources {#resources}

* Adobe offers hundreds of [Analytics video training tutorials](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/overview.html?lang=it).
* See [Adobe Experience Cloud release notes](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=it#analytics) for updates about new features.
* A great way to become acquainted with Analysis Workspace is through the Analysis Workspace Training Tutorial template. This template walks you through common terminology and steps for building your first analysis in Workspace. To begin the tutorial:
  1. On the [!UICONTROL **Workspace**] tab in Adobe Analytics, select **[!UICONTROL Learning]** on the left.
  1. Select **[!UICONTROL Open Tutorial]**.
     ![](assets/training-tutorial.png)

-->