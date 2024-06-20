---
description: Scopri le nozioni di base per lavorare su un progetto Workspace.
keywords: Analysis Workspace
title: Panoramica dei progetti
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: 08f3926bfa621ce3678da6db0f0a30ac5302b757
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 68%

---

# Panoramica dei progetti

Utilizzando i progetti Workspace, puoi combinare componenti dati, tabelle e visualizzazioni per sviluppare delle analisi da condividere con altri nella tua organizzazione. Prima di iniziare il primo progetto, scopri come accedere, navigare e gestire i progetti.

Ecco un video su come creare un progetto Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/334076/?quality=12)

## Elenco dei progetti {#project-list}

Quando scegli **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** per la prima volta, vengono elencati tutti i progetti di cui sei proprietario o a cui puoi accedere. Questa è anche la pagina di destinazione per Adobe Analytics, a meno che tu non abbia precedentemente impostato una pagina di destinazione personalizzata.

![](assets/sample-project.png)

La pagina Progetti contiene le informazioni riportate di seguito.

>[!NOTE]
>
>Alcune colonne non vengono visualizzate per impostazione predefinita. Per personalizzare le colonne visualizzate, fare clic su **Personalizza tabella** icona ![Personalizza tabella](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg).


| Elemento | Descrizione |
|---|---|
| [Modifica preferenze](/help/analyze/analysis-workspace/user-preferences.md) | Gestisci le impostazioni di Analysis Workspace e dei relativi componenti per tutti i nuovi progetti o pannelli creati. |
| [Crea cartella](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | Aggiungi una nuova cartella o sottocartella all’elenco dei progetti e delle cartelle. |
| [Crea progetto](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) | Avvia un nuovo progetto da zero o da un rapporto. |
| Mostra altro | Mostra le opzioni per la creazione di un progetto vuoto o di una scorecard per dispositivi mobili. [visualizzazione dei tutorial di formazione](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html?lang=it), o [visualizzazione delle note sulla versione](/help/release-notes/latest.md). |
| Mostra cartelle e progetti | Scegli se visualizzare la struttura di cartelle dei progetti. Per ulteriori informazioni, consulta la sezione [Informazioni sulle cartelle in Analytics](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| Personalizza tabella (icona) | Consente di personalizzare le informazioni visualizzate per ciascun progetto nella pagina Progetti. |
| Nome | Nome del progetto Workspace. |
| Tipo | Indica se si tratta di un progetto Workspace, una cartella o un [Scorecard per dispositivi mobili](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=it). |
| Tag | Tag che sono stati applicati al progetto. |
| Pianificato | Indica se i progetti sono programmati per essere inviati tramite e-mail ai destinatari in base a una pianificazione. Consulta [Programmare progetti](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| Collegamento condiviso (chiunque) | I progetti possono essere condivisi con chiunque, anche con persone che non hanno accesso ad Analysis Workspace. Questa colonna mostra se i progetti sono stati condivisi in questo modo. Consulta [Condividere un progetto con altri utenti (accesso non richiesto)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Condividere progetti](/help/analyze/analysis-workspace/curate-share/share-projects.md) per ulteriori informazioni. |
| Suite di rapporti | La suite di rapporti a cui è associato il progetto. |
| [Ruolo progetto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=it) | Indica il tuo ruolo per il progetto, ossia se sei il proprietario o se sei autorizzato a modificarlo, duplicarlo o visualizzarlo. |
| Proprietario | Autore del progetto (tu o l’utente che ha condiviso con te il progetto). |
| Condiviso con | Utenti con cui il progetto è stato condiviso. |
| Ultima modifica | Data e ora dell’ultima volta che il progetto è stato modificato. |
| Ultima apertura | Data e ora dell’ultima apertura del progetto. |
| ID Progetto | ID del progetto. |
| Intervallo date più lungo | L’intervallo di date più lungo del progetto. |
| Numero di query | Numero totale di query contenute nel progetto. |
| Posizione | Cartella in cui risiede il progetto. |

## Barra dei menu {#menu-bar}

In un progetto, il menu fornisce le opzioni necessarie per gestirlo, aggiungervi dei componenti, cercare assistenza e altro ancora. È inoltre possibile accedere a ogni opzione del menu tramite [scelte rapide](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=it) da tastiera.

![](assets/menu.png)

| Opzione di menu | Descrizione |
|---|---|
| Progetto | Include azioni comuni per la gestione dei progetti, come Nuovo, Apri, Salva, Salva con nome e [Salva come rapporto aziendale](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). Puoi anche aggiornare l’intero progetto per recuperare i dati e le definizioni più recenti facendo clic su Refresh Project (Aggiorna progetto). Le opzioni [Download CSV and PDF](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=it) (Scarica CSV e PDF) consentono di esportare i dati da Workspace. [Project Info &amp; Settings](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html?lang=it#info-settings) (Informazioni e impostazioni progetto) offre molte opzioni per la gestione del progetto. |
| Modificare | Annulla o ripristina l’ultima azione. Con Clear All (Cancella tutto) puoi ripristinare il progetto e tornare al progetto vuoto iniziale. |
| Inserisci | Con questo menu puoi inserire nuovi pannelli o visualizzazioni. Puoi anche inserire nuovi pannelli e visualizzazioni dalla barra a sinistra. |
| [Componenti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=it) | Crea dal progetto nuovi segmenti, metriche calcolate, intervalli di date o componenti di avviso. Puoi anche creare nuovi componenti dalla barra a sinistra. Se le definizioni dei componenti sono state recentemente modificate, usa Refresh Components (Aggiorna componenti) per recuperare le definizioni più recenti. |
| [Condividi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html?lang=it) | Puoi curare, condividere e pianificare progetti PDF/CSV per i destinatari all’interno della tua organizzazione. |
| Aiuto | Accedi alla documentazione dell’Aiuto, ai video e alla [community di Experience League](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community) per Analytics. Gestisci la visibilità dei suggerimenti di Workspace e il [debugger](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md). Trova dettagli su Workspace e sui fattori che influiscono sulle [prestazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html?lang=it) del progetto. |
| Pulsante Condividi o Proprietario | Se stai utilizzando il progetto in modalità Own (Proprietario) o Edit (Modifica), il pulsante Share (Condividi) in alto a destra consente di accedere con un solo clic ai destinatari del progetto e di gestirli. Se invece utilizzi il progetto con un ruolo Duplicate (Duplica) o View (Visualizza), viene visualizzato il nome del proprietario del progetto. |

### Informazioni e impostazioni progetto {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & settings]** fornisce informazioni a livello di progetto sul progetto attualmente attivo.

![](assets/projectinfo.png)

Le impostazioni includono:

| Impostazione | Descrizione |
|---|---|
| Nome progetto | Nome assegnato al progetto. Puoi fare doppio clic sul nome per modificarlo. |
| Creato da | Nome del proprietario del progetto. |
| Ultima modifica | Data dell’ultima modifica apportata al progetto. |
| Tag | Elenca eventuali tag applicati a un progetto per facilitarne la categorizzazione. |
| Descrizione | La descrizione è utile per chiarire lo scopo di un progetto. Puoi fare doppio clic sulla descrizione per modificarla. |
| Conteggio istanze ripetute nel progetto | Consente di specificare se conteggiare o meno, per i rapporti, le istanze ripetute. Ad esempio, questa impostazione (se attivata) tratta più visualizzazioni consecutive della stessa pagina come molteplici visualizzazioni di pagina. Se questa opzione è disattivata, vengono invece conteggiate come una singola visualizzazione della pagina (influisce solo su determinate metriche, come le visite a pagina singola). **Nota**: questa impostazione non si applica alle visualizzazioni Flusso o Abbandono. |
| [Palette dei colori del progetto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=it) | Per cambiare la palette di colori utilizzata per le categorie in Workspace, puoi scegliere una delle palette predefinite ottimizzate per il daltonismo o specificarne una personalizzata. Questa funzione interessa numerosi elementi in Workspace, compresa la maggior parte delle visualizzazioni. |
| [Densità di visualizzazione](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=it) | Consente di visualizzare più dati nella schermata riducendo la spaziatura verticale della barra a sinistra, tabelle a forma libera e tabelle a coorte. |

## Barra a sinistra {#left-rail}

All’interno di un progetto, nella barra a sinistra sono disponibili varie icone, ciascuna delle quali rappresenta parti importanti di un progetto:

* [Pannelli](/help/analyze/analysis-workspace/c-panels/panels.md) ![icona pannelli](assets/panels-icon.png)

* [Visualizzare](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![icona delle visualizzazioni](assets/visualizations-icon.png)

* [Componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)![icona dei componenti](assets/components-icon.png)

* [Dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)![icona dizionario dati](assets/data-dictionary-icon.png)

* [Sommario](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) ![icona sommario](assets/toc-icon.png)

I componenti (dimensioni, metriche, filtri, intervalli di date) nella barra a sinistra si riferiscono alla vista di dati del pannello attivo. Il pannello attivo è identificato dal bordo blu che lo circonda e la visualizzazione dati attiva è elencata nella parte superiore della barra dei componenti.

![I componenti relativi alla visualizzazione dati del pannello attivo per la visualizzazione dati Demo cross-industry.](assets/left-rail.png)



## Menu di scelta rapida

Video sull’utilizzo del menu di scelta rapida in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23981/?quality=12)

## Area di lavoro del progetto {#canvas}

Nell’area di lavoro del progetto puoi raccogliere i pannelli, le tabelle, le visualizzazioni e i componenti con cui intendi generare le analisi. Un progetto può contenere diversi pannelli, e ciascun pannello può contenere più tabelle e visualizzazioni.

I pannelli sono utili per organizzare i progetti in base a specifici periodi di tempo, suite di rapporti o casi di utilizzo di analisi. Il pannello attivo è evindenziato da un bordo blu e determina quali componenti sono disponibili nella barra a sinistra.

A seconda del punto iniziale scelto per i progetti, l’area di lavoro presenta una [tabella a forma libera](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=it) o un [pannello vuoto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=it). Il modo più rapido per iniziare l’analisi consiste nel selezionare uno o più componenti e semplicemente trascinarli nell’area di lavoro del progetto. Viene creata automaticamente una tabella di dati. [Scopri di più](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=it) sulle diverse opzioni per la creazione di una tabella. Per maggiori informazioni su come creare il primo progetto, segui questo [tutorial](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it#training-tutorial).

![](assets/canvas.png)

## Project Manager {#manager}

I progetti Analysis Workspace possono essere gestiti tramite **[!UICONTROL Analytics]> [!UICONTROL Components] >[!UICONTROL Projects]**. Il Project Manager mostra gli elementi creati da un utente specifico.

La proprietà del progetto può essere trasferita a un nuovo utente in [!UICONTROL Admin] > [!UICONTROL Analytics Users & Assets] > [!UICONTROL Transfer Assets].

Nella finestra per la gestione dei progetti è possibile aggiungere, assegnare tag, condividere, duplicare/copiare e altro ancora. Per cercare un progetto puoi utilizzare la barra di ricerca o le opzioni filtro disponibili nella barra a sinistra. Puoi filtrare per tag, proprietari, tipo di progetto e altro ancora.

![](assets/project-manager.png)

Di seguito sono riportate le azioni più comuni per la gestione dei progetti, che possono essere eseguite su uno o più progetti alla volta:

| Azione | Descrizione |
|---|---|
| Add | Creare un nuovo progetto da zero o iniziare da un [rapporto](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md). |
| Tag (Assegna tag) o Approve (Approva) | Scegli &quot;Tag&quot; o &quot;Approve&quot; per organizzare i progetti e semplificarne la ricerca. |
| [Condividi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=it) | Rendi un progetto disponibile ad altri utenti di Analysis Workspace all’interno dell’organizzazione. |
| Elimina | Elimina il progetto. |
| Rinomina | Modifica il nome del progetto. |
| Copia | Crea un duplicato del progetto. Viene creato un nuovo progetto, con un nuovo ID progetto. Eventuali condivisioni o pianificazioni collegate al progetto originale non vengono copiate. |
| Export to CSV (Esporta in CSV) | Scarica il progetto come file CSV, contenente dati in formato solo testo. |
