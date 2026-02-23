---
title: Panoramica di Analysis Workspace
description: Scopri Analysis Workspace, lo strumento di analisi principale per Adobe Analytics. Utilizza progetti, pannelli, tabelle, visualizzazioni e altri componenti per dare vita ai dati e per curare e condividere le analisi.
feature: Workspace Basics
role: User, Admin
exl-id: de95551d-09ea-4461-9bb4-b4ef235e9cd2
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '1256'
ht-degree: 95%

---

# Panoramica di Analysis Workspace {#analysis-workspace-overview}

Analysis Workspace consente di realizzare rapidamente le analisi per raccogliere informazioni e quindi condividerle con altri utenti. Utilizzando l’interfaccia di trascinamento del browser, puoi creare analisi, aggiungere visualizzazioni per mettere in risalto i dati, curare un set di dati, condividere e pianificare [progetti](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) con chiunque desideri.

>[!BEGINSHADEBOX]

Per un video demo, guarda ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panoramica di Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-overview){target="_blank"}.

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
