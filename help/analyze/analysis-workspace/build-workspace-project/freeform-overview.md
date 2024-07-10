---
description: Scopri le nozioni di base per lavorare su un progetto Workspace.
keywords: Analysis Workspace
title: Panoramica dei progetti
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: f6bfded8b3a8346b912f34cf2f3ba9a4958eefa7
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 41%

---

# Panoramica dei progetti

Utilizzando i progetti Workspace, puoi combinare componenti dati, tabelle e visualizzazioni per sviluppare delle analisi da condividere con altri nella tua organizzazione. Prima di iniziare il primo progetto, scopri come accedere, navigare e gestire i progetti.

Ecco un video su come creare un progetto Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/334076/?quality=12)

## Elenco dei progetti {#project-list}

Quando scegli **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** per la prima volta, vengono elencati tutti i progetti di cui sei proprietario o a cui puoi accedere. Questa pagina è anche la pagina di destinazione di Adobe Analytics, a meno che tu non abbia precedentemente impostato una pagina di destinazione personalizzata.

La pagina Progetti contiene le informazioni riportate di seguito.

| Elemento | Descrizione |
|---|---|
| [Modifica preferenze](/help/analyze/analysis-workspace/user-preferences.md) | Gestisci le impostazioni di Analysis Workspace e dei relativi componenti per tutti i nuovi progetti o pannelli creati. |
| [Crea cartella](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | Aggiungi una nuova cartella o sottocartella all’elenco dei progetti e delle cartelle. |
| [Crea progetto](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) | Avvia un nuovo progetto da zero o da un rapporto. |
| Mostra altro | Questa selezione rivela le opzioni per la creazione di un progetto vuoto o di una scorecard per dispositivi mobili. [visualizzazione dei tutorial di formazione](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction), o [visualizzazione delle note sulla versione](/help/release-notes/latest.md). |
| ![Mostra filtri](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) | Per mostrare o nascondere i filtri. Puoi filtrare in base a tag, suite di rapporti, proprietari, tipo (progetto, cartella, scorecard per dispositivi mobili) e altri filtri. |
| ![Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | Utilizza il campo di ricerca per cercare cartelle, progetti Workspace o scorecard per dispositivi mobili. |
| Mostra cartelle e progetti | Scegli se visualizzare la struttura di cartelle dei progetti. Per ulteriori informazioni, consulta la sezione [Informazioni sulle cartelle in Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| ![Personalizza tabella](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) | Questa icona ti consente di personalizzare le colonne visualizzate per ciascun progetto nell’elenco dei progetti. |

L’elenco dei progetti può visualizzare le seguenti colonne:

| Colonna | Descrizione |
|---|---|
| [!UICONTROL Name] | Nome del progetto Workspace. Seleziona ![Info](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) per visualizzare una finestra a comparsa con ulteriori dettagli su un progetto o una cartella. Seleziona ![Altro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) per visualizzare le azioni disponibili. Consulta [Gestione progetti](#manage-projects) per ulteriori dettagli. |
| [!UICONTROL Type] | Indica se la voce è un progetto Workspace, una cartella o un [Scorecard per dispositivi mobili](https://experienceleague.adobe.com/en/docs/analytics/analyze/mobapp/home). |
| [!UICONTROL Tags] | Tag che sono stati applicati al progetto. |
| [!UICONTROL Scheduled] | Indica se i progetti sono programmati per essere inviati tramite e-mail ai destinatari. Consulta [Programmare progetti](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| Collegamento condiviso (chiunque) | I progetti possono essere condivisi con chiunque, anche con persone che non hanno accesso ad Analysis Workspace. Questa colonna mostra se i progetti sono stati condivisi in questo modo. Consulta [Condividere un progetto con altri utenti (accesso non richiesto)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md) per ulteriori informazioni. |
| [Ruolo progetto](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/share-projects) | Indica il tuo ruolo per il progetto, ossia se sei il proprietario o se sei autorizzato a modificarlo, duplicarlo o visualizzarlo. |
| [!UICONTROL Report suite] | La suite di rapporti a cui è associato il progetto. |
| [!UICONTROL Owner] | Autore del progetto (tu o l’utente che ha condiviso con te il progetto). |
| [!UICONTROL Shared with] | Utenti con cui il progetto è stato condiviso. |
| [!UICONTROL Last Modified] | Data e ora dell’ultima volta che il progetto è stato modificato. |
| [!UICONTROL Last Opened] | Data e ora dell’ultima apertura del progetto. |
| [!UICONTROL Last Used] | Data e ora dell’ultimo utilizzo del progetto. |
| [!UICONTROL Project ID] | ID del progetto. |
| [!UICONTROL Longest Date Range] | L’intervallo di date più lungo del progetto. |
| [!UICONTROL Number of Queries] | Numero totale di query contenute nel progetto. |
| [!UICONTROL Location] | Cartella in cui risiede il progetto. |

### Gestione progetti

Per gestire i progetti, seleziona uno o più progetti dall’elenco.

Dalla barra delle azioni blu, puoi selezionare le azioni seguenti:

| Azione | Descrizione |
|---|---|
| ![Elimina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) Elimina | Quando è selezionata, viene visualizzata una finestra di dialogo di conferma che richiede di confermare l’eliminazione di un progetto Workspace o di una scorecard per dispositivi mobili. Seleziona **[!UICONTROL OK]** per confermare. |
| ![Condividi](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg) Condividi | Questa azione ti consente di condividere il progetto. Consulta [Condividere progetti](../curate-share/share-projects.md). |
| ![Rinomina](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) Rinomina | Apre una **[!UICONTROL Rename: *nome *]**per rinominare il progetto. Seleziona **[!UICONTROL Save]**per salvare il nuovo nome del progetto. |
| ![Copia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) Copia | Copia immediatamente il progetto selezionato in un nuovo progetto denominato *nome originale* (Copia). |
| ![Fissa](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) Fissa | Aggiunge immediatamente il progetto all&#39;inizio dell&#39;elenco. Aggiunge il ![Fissa](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg) indicatore. |
| ![Tag](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Label_18_N.svg) Tag | Apre il **[!UICONTROL Tag Project]** . Puoi selezionare un tag esistente o aggiungerne di nuovi. Seleziona **[!UICONTROL Save]** per salvare i tag per il progetto. |
| ![(Annulla)Approva](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CheckmarkCircle_18_N.svg) Approva o Annulla approvazione | Approva o non approva il progetto. |
| ![Esporta CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) Esporta CSV | Scarica immediatamente un file contenente un elenco di valori dei progetti separati da virgole. |
| ![Sposta in](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FolderAddTo_18_N.svg) Sposta in | Questa azione ti consente di spostare il progetto in una cartella. In **[!UICONTROL Select Folder]** , seleziona una cartella dalla finestra di dialogo **[!UICONTROL Folder]** e seleziona **[!UICONTROL Move]**. |


## Barra dei menu {#menu-bar}

In un progetto, il menu fornisce le opzioni necessarie per gestirlo, aggiungervi dei componenti, cercare assistenza e altro ancora. È inoltre possibile accedere a ogni opzione di menu tramite tastiera [scelte rapide](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys).


| Opzione di menu | Descrizione |
|---|---|
| Progetto | Questo menu include azioni comuni per la gestione dei progetti, come Nuovo, Apri, Salva, Salva con nome e [Salva come rapporto aziendale](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). Puoi anche aggiornare l’intero progetto per recuperare i dati e le definizioni più recenti facendo clic su Refresh Project (Aggiorna progetto). Le opzioni [Download CSV and PDF](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/download-send) (Scarica CSV e PDF) consentono di esportare i dati da Workspace. [Project Info &amp; Settings](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) (Informazioni e impostazioni progetto) offre molte opzioni per la gestione del progetto. |
| Modificare | Annulla o ripristina l’ultima azione. Cancella tutto reimposta il progetto su un punto di partenza vuoto. |
| Inserisci | Con questo menu puoi inserire nuovi pannelli o visualizzazioni. Puoi anche inserire nuovi pannelli e visualizzazioni dalla barra a sinistra. |
| [Componenti](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components) | Crea dal progetto nuovi segmenti, metriche calcolate, intervalli di date o componenti di avviso. Puoi anche creare nuovi componenti dalla barra a sinistra. Se le definizioni dei componenti sono state recentemente modificate, Aggiorna componenti recupera le definizioni più recenti. |
| [Condividi](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files) | Curare, condividere e pianificare progetti PDF/CSV per i destinatari all’interno della tua organizzazione. |
| Aiuto | Accedi alla documentazione dell’Aiuto, ai video e alla [community di Experience League](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community) per Analytics. Gestisci la visibilità dei suggerimenti di Workspace e il [debugger](https://developer.adobe.com/analytics-apis/docs/2.0/). Trova dettagli su Workspace e sui fattori che influiscono sulle [prestazioni](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance) del progetto. |
| Pulsante Condividi o Proprietario | Se stai utilizzando il progetto in modalità Own (Proprietario) o Edit (Modifica), il pulsante Share (Condividi) in alto a destra consente di accedere con un solo clic ai destinatari del progetto e di gestirli. Se per il progetto hai il ruolo Duplica o Visualizza, viene visualizzato il nome del proprietario del progetto. |

### Informazioni e impostazioni progetto {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & settings]** fornisce informazioni a livello di progetto sul progetto attualmente attivo.

![Informazioni progetto](assets/projectinfo.png)

Le impostazioni includono:

| Impostazione | Descrizione |
|---|---|
| Nome progetto | Nome assegnato al progetto. Puoi fare doppio clic sul nome per modificarlo. |
| Proprietario | Nome del proprietario del progetto. |
| Ultima modifica | Data dell’ultima modifica apportata al progetto. |
| Tag | Elenca eventuali tag applicati a un progetto per facilitarne la categorizzazione. |
| Descrizione | La descrizione è utile per chiarire lo scopo di un progetto. Puoi fare doppio clic sulla descrizione per modificarla. |
| Conta istanze ripetute | Consente di specificare se conteggiare o meno, per i rapporti, le istanze ripetute. Ad esempio, questa impostazione (se attivata) tratta più visualizzazioni consecutive della stessa pagina come molteplici visualizzazioni di pagina. Se questa opzione è disattivata, vengono conteggiate come una singola visualizzazione di pagina (questa impostazione influisce solo su determinate metriche, come le visite a pagina singola). **Nota**: questa impostazione non si applica alle visualizzazioni Flusso o Abbandono. |
| [Mostra annotazioni](/help/analyze/analysis-workspace/components/annotations/overview.md) | Specifica se mostrare o meno le annotazioni nel progetto. |
| [Palette dei colori del progetto](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes) | Per cambiare la palette di colori utilizzata per le categorie in Workspace, puoi scegliere una delle palette predefinite ottimizzate per il daltonismo o specificarne una personalizzata. Questa funzione interessa numerosi elementi in Workspace, compresa la maggior parte delle visualizzazioni. |
| [Densità di visualizzazione](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density) | Consente di visualizzare più dati nella schermata riducendo la spaziatura verticale della barra a sinistra, tabelle a forma libera e tabelle a coorte. |

## Barra a sinistra {#left-rail}

All’interno di un progetto, nella barra a sinistra sono disponibili varie icone, ciascuna delle quali rappresenta uno strumento importante per la creazione del progetto:

| Icona | Funzionalità |
|---|---|
| ![icona pannelli](https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg) | [Pannelli](/help/analyze/analysis-workspace/c-panels/panels.md) |
| ![icona delle visualizzazioni](https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphBarVertical_18_N.svg) | [Visualizzazioni](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| ![icona dei componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) | [Componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| ![icona dizionario dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Bookmark_18_N.svg) | [Dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) |
| ![icona sommario](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ViewList_18_N.svg) | [Sommario](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) |

I componenti (dimensioni, metriche, segmenti, intervalli di date) nella barra a sinistra si riferiscono alla visualizzazione dati del pannello attivo. Il pannello attivo è identificato da un bordo blu e la suite di rapporti attiva è elencata nella parte superiore della barra dei componenti.


## Menu di scelta rapida

Video sull’utilizzo del menu di scelta rapida in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23981/?quality=12)

## Area di lavoro del progetto {#canvas}

Nell’area di lavoro del progetto puoi raccogliere i pannelli, le tabelle, le visualizzazioni e i componenti con cui intendi generare le analisi. Un progetto può contenere diversi pannelli, e ciascun pannello può contenere più tabelle e visualizzazioni.

I pannelli sono utili per organizzare i progetti in base a specifici periodi di tempo, suite di rapporti o casi di utilizzo di analisi. Il pannello attivo è evidenziato da un bordo colorato e determina quali componenti sono disponibili nella barra a sinistra.

A seconda del punto iniziale scelto per i progetti, è possibile: [tabella a forma libera](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) o un [pannello vuoto](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/blank-panel) nell’area di lavoro, per iniziare. Il modo più rapido per iniziare l’analisi consiste nel selezionare uno o più componenti e semplicemente trascinarli nell’area di lavoro del progetto. Viene creata automaticamente una tabella di dati. [Ulteriori informazioni](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table) informazioni sulle diverse opzioni per la creazione di una tabella o utilizza i [tutorial di formazione](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/home) per maggiori informazioni sulla creazione del primo progetto.

![](assets/canvas.png)
