---
description: Scopri le funzioni di supporto per l’accessibilità di Analysis Workspace.
title: Accessibilità In Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: 2bacbee8-097c-4fc5-8be4-7e4f284db08c
source-git-commit: 70d87e62441f8d5c3c6041721353a07432fef912
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 94%

---


# Accessibilità di Analysis Workspace

Scopri il supporto per l’accessibilità in [!UICONTROL Analysis Workspace], lo strumento di analisi principale per Customer Journey Analytics.

Per accessibilità si intendono i prodotti utilizzabili da persone affette da disabilità visive, uditive, cognitive, motorie e di altro tipo. Gli esempi di funzioni di accessibilità per i prodotti software includono:

* supporto di assistenti vocali,
* equivalenti testuali per gli elementi grafici,
* scelte rapide da tastiera,
* modifica dei colori dello schermo per aumentare il contrasto,
* e altro ancora.

[!UICONTROL Analysis Workspace] fornisce alcuni strumenti che ne rendono accessibile l’utilizzo, tra cui:

## Navigazione tramite tastiera

La navigazione in [!UICONTROL Analysis Workspace] avviene dall’alto verso il basso e da sinistra a destra. I seguenti elementi di navigazione facilitano l’accessibilità:

* Il tasto **[!UICONTROL Tab]** consente di utilizzare scelte rapide per punti di riferimento e di spostarsi tra sezioni più grandi all’interno di Workspace. Nel pannello a sinistra, **[!UICONTROL Tab]** consente anche di passare da un’opzione trascinabile alla successiva.
* ◀︎ e ▶︎ spostano tra i singoli elementi dopo che la chiave **[!UICONTROL Tab]** ha evidenziato un elemento.
* Il tasto **[!UICONTROL F6]** consente di passare al primo pannello del progetto e di spostarsi tra le visualizzazioni all’interno di tale pannello. Quindi, consente di passare al pannello successivo del progetto e così via.
* Gli indicatori di attivazione vengono applicati in modo che gli utenti vedenti che utilizzano la tastiera abbiano un’indicazione chiara dell’elemento dell’interfaccia utente attualmente attivo. L’indicatore è un bordo blu per il pannello attivo. E lo sfondo grigio per la funzionalità selezionata di recente e la selezione all’interno della funzionalità. Nell’esempio, i [!UICONTROL Components] e la dimensione Pagina sono stati selezionati di recente.

  ![Tabella a forma libera che mostra un indicatore di stato attivo con un bordo blu attorno alla tabella a forma libera.](assets/focus-indicator.png)

### Navigazione tramite tastiera per la barra dei menu

1. Premi il tasto Tab fino ad arrivare alla barra dei menu.
1. Utilizza i tasti freccia per spostarti tra i menu e le voci di menu.
1. Premi **[!UICONTROL Enter]** per aprire un menu o selezionare una voce di menu.
1. Utilizza **[!UICONTROL Esc]** per chiudere un menu.

### Navigazione tramite tastiera per interazioni con trascinamento

[!UICONTROL Analysis Workspace] è un’interfaccia utente di trascinamento. Tuttavia, in alternativa, gli utenti possono aggiungere componenti utilizzando la tastiera:

1. Passa a un componente nel pannello a sinistra.
1. Premi **[!UICONTROL Enter]** per selezionare.
1. Utilizza i tasti freccia per passare all’area in cui desideri rilasciare il componente.
1. Premi **[!UICONTROL Enter]** per posizionare il componente.

### Scelte rapide da tastiera

[!UICONTROL Analysis Workspace] offre un set completo di [scelte rapide da tastiera](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) per un flusso di lavoro più semplice.

## Supporto per assistenti vocali e lenti di ingrandimento dello schermo

Un assistente vocale legge il testo visualizzato sullo schermo del computer. Vengono lette anche informazioni non testuali, come etichette di pulsanti o descrizioni delle immagini nell’applicazione.

## Palette di colori e contrasto

[!UICONTROL Analysis Workspace] si impegna per essere conforme a WCAG 2.1 AA, compresi i requisiti per il contrasto del colore.

Inoltre, gli utenti possono impostare la propria palette di colori preferita per un progetto in **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Project color palette](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md).

## Convalida richiesta

Quando crei un componente, una visualizzazione o un pannello, i campi obbligatori vengono convalidati al momento del salvataggio. Se un campo obbligatorio non supera la convalida, viene evidenziato in rosso con un’icona di errore. Una descrizione scritta spiega il problema che deve essere risolto.

![Generatore di segmenti e indicatore di convalida degli errori.](assets/error-validation.png)

## Supporto per le funzioni di accessibilità del sistema operativo

Analysis Workspace supporta funzioni incorporate di accessibilità di Windows e macOS come modalità ad alto contrasto, tasti permanenti e tasti lenti o filtro tasti. Fornisce inoltre informazioni sull’interfaccia utente del sistema operativo per consentire l’interazione con le tecnologie di assistenza, compresi gli assistenti vocali come VoiceOver per macOS e NVDA su Windows.


<!--

# Accessibility in Analysis Workspace

Learn about accessibility support in [!UICONTROL Analysis Workspace], the premier analysis tool for Adobe Analytics. 

Accessibility refers to making products usable for people with visual, auditory, cognitive, motor, and other disabilities. Examples of accessibility features for software products include screen reader support, text equivalents for graphics, keyboard shortcuts, change of display colors to high contrast, and so on. 

[!UICONTROL Analysis Workspace] provides some tools that make it accessible to use, including:

## Navigate [!UICONTROL Workspace] using the keyboard

Navigation in [!UICONTROL Analysis Workspace] works top > down, and left > right. The following navigational elements facilitate accessibility:

* The `Tab` key enables landmark shortcuts, moving between larger sections within Workspace. In the left rail, `Tab` also enables you to move from one draggable option to the next.
* The `left/right arrows` move between individual elements after `Tab` has highlighted it. 
* The `F6` navigates to the first panel in the project and  moves between the visualizations within that panel. Then, it moves to the next panel in the project and repeats. 
* We apply focus indicators so that sighted keyboard users have a clear indication of which UI element currently has focus. The indicator is a blue border around the selected element.

    ![Focus Indicator](assets/focus-indicator.png)

### Keyboard navigation for the menu bar 

1. Tab until you have reached the menu bar.
1. Use left/right arrow keys to navigate to the menu you want.
1. Press `Enter` to select the menu and show its options.
1. Use up/down arrow keys to navigate to the menu option you want.
1. Press `Enter` to select the option.

### Keyboard navigation for drag & drop interactions 

[!UICONTROL Analysis Workspace] is a drag & drop user interface. However, users can add components using the keyboard instead:

1. Tab to a component in the left rail.
1. Press `Enter` to select.
1. Use arrow keys to navigate to the area where you want to drop the component.
1. Press `Enter` to place the component.

### Keyboard shortcuts (hotkeys) 

[!UICONTROL Analysis Workspace] offers a rich set of [keyboard shortcuts](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=it) for a more seamless workflow. Some common shortcuts for navigation, analysis creation, and insight democratization are listed below. 

#### Navigation

| Shortcut | Action |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Jump to different rails: [!UICONTROL Panels], [!UICONTROL Visualizations], or [!UICONTROL Components] | 
| `[Alt + Left / Right]` | Navigate between panels |
| `[Alt + M]` | Collapse/expand all panels |
| `[Alt + Ctrl + M]` | Collapse/expand active panel |
| `[Ctrl + /]` | Search left rail |

#### Analysis creation

| Shortcut | Action |
| --- | --- |
| `[Alt + 1]` | New freeform table |
| `[Ctrl + Shift + C]` | New calculated metric |
| `[Ctrl + Shift + D]` | New date range |
| `[Ctrl + Shift + E]` | New segment |
| `[Ctrl + Z]` | Undo |
| `[Component drag + Shift]` | Create a drop-down filter |

#### Democratization

| Shortcut | Action |
| --- | --- |
| `[Ctrl + S]` | Save |
| `[Ctrl + Shift + G]` | Curate |
| `[Ctrl + G]` | Share |
| `[Alt + Shift + S]` | Schedule |
| `[Alt + L]` | Get link to project |
| `[Ctrl + Shift + B]` | Download PDF |

## Support for screen readers and screen magnifiers

A screen reader reads text that appears on the computer screen. It also reads non-textual information, such as button labels or image descriptions in the application, provided in accessibility tags or attributes.  

## Color palettes & contrast  

[!UICONTROL Analysis Workspace] strives for WCAG 2.1 AA conformance, including requirements for color contrast. 

In addition, users can set their own preferred color palette for a project under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Project color palette](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=it). 

## Required field validation in component builders 

When building a component, required fields are validated when you save. If a required field does not pass validation, it will be outlined in red with an error icon. A written description appears of the issue that needs to be fixed.  

Once a component is fully validated, pressing `Save` closes the builder. 

![Error validation](assets/error-validation.png)

## Support for operating system accessibility features  

Analysis Workspace supports built-in MS Windows and macOS accessibility features like high-contrast mode, sticky keys, and slow keys/filter keys. It also provides information about the user interface to the operating system to enable interaction with assistive technologies, including screen readers such as VoiceOver for macOS and NVDA on Windows.

-->