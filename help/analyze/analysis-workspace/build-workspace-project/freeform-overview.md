---
description: Scopri le nozioni di base per lavorare su un progetto Workspace.
keywords: Analysis Workspace
title: Panoramica sui progetti
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
feature: Concetti di base di Workspace
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: 5027c17f1b0efc2fe22915e39aca901ee2beb34a
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 96%

---

# Panoramica sui progetti

Utilizzando i progetti Workspace, puoi combinare componenti dati, tabelle e visualizzazioni per sviluppare delle analisi da condividere con altri nella tua organizzazione. Prima di iniziare il primo progetto, scopri come accedere, navigare e gestire i progetti.

## Elenco dei progetti {#project-list}

Quando scegli **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** per la prima volta, vengono elencati tutti i progetti di cui sei proprietario o a cui puoi accedere. Questa è anche la pagina di destinazione per Adobe Analytics, a meno che tu non abbia precedentemente impostato una pagina di destinazione personalizzata.

![](assets/sample-project.png)

La pagina dell’elenco dei progetti Workspace contiene le seguenti informazioni:

| Elemento | Descrizione |
|---|---|
| [Crea nuovo progetto](/help/analyze/analysis-workspace/home.md) | Fai clic su questo collegamento per avviare un nuovo progetto partendo da zero o da un [modello](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it#analysis-workspace) che è stato creato per te. |
| Gestione progetti | Fai clic su questo collegamento per passare al modulo di gestione dei componenti per progetti (**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), in cui vengono elencati tutti i tuoi progetti e dove puoi assegnare tag, condividere, eliminare, rinominare, approvare, copiare ed esportare i progetti come file CSV. |
| Imposta come pagina di destinazione | Consente di impostare la pagina attuale come pagina di destinazione di Workspace. |
| [Visualizza esercitazioni](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html?lang=it) | Consente di accedere ai video tutorial su Analysis Workspace. |
| Nome | Nome del progetto Workspace. |
| Proprietario | Autore del progetto (tu o l’utente che ha condiviso con te il progetto). |
| Tipo | Indica se si tratta di un progetto Workspace o di una [scheda di valutazione mobile](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=it). |
| [Ruolo progetto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=it) | Indica il tuo ruolo per il progetto, ossia se sei il proprietario o se sei autorizzato a modificarlo, duplicarlo o visualizzarlo. |
| Tag | Tag che sono stati applicati al progetto. |
| Ultima modifica | Data e ora dell’ultima volta che il progetto è stato modificato. |
| Progetti preferiti | Per contrassegnare un progetto come preferito, aprilo e fai clic sulla stella accanto al nome del progetto. Al successivo avvio di Workspace, verrà elencato tra i progetti preferiti. |
| Progetti visualizzati di frequente | Elenca i progetti che vengono aperti più spesso, per accedervi più facilmente. |

## Barra dei menu {#menu-bar}

In un progetto, il menu fornisce le opzioni necessarie per gestirlo, aggiungervi dei componenti, cercare assistenza e altro ancora. È inoltre possibile accedere a ogni opzione del menu tramite [scelte rapide](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=it) da tastiera.

![](assets/menu.png)

| Opzione di menu | Descrizione |
|---|---|
| Progetto | Include azioni comuni per la gestione dei progetti, come Nuovo, Apri, Salva, Salva con nome e [Salva come modello](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=it). Puoi anche aggiornare l’intero progetto per recuperare i dati e le definizioni più recenti facendo clic su Refresh Project (Aggiorna progetto). Le opzioni [Download CSV and PDF](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=it) (Scarica CSV e PDF) consentono di esportare i dati da Workspace. [Project Info &amp; Settings](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html?lang=it#info-settings) (Informazioni e impostazioni progetto) offre molte opzioni per la gestione del progetto. |
| Modificare | Annulla o ripristina l’ultima azione. Con Clear All (Cancella tutto) puoi ripristinare il progetto e tornare al progetto vuoto iniziale. |
| Inserisci | Con questo menu puoi inserire nuovi pannelli o visualizzazioni. Puoi anche inserire nuovi pannelli e visualizzazioni dalla barra a sinistra. |
| [Componenti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=it) | Crea dal progetto nuovi segmenti, metriche calcolate, intervalli di date o componenti di avviso. Puoi anche creare nuovi componenti dalla barra a sinistra. Se le definizioni dei componenti sono state recentemente modificate, usa Refresh Components (Aggiorna componenti) per recuperare le definizioni più recenti. |
| [Condividi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html?lang=it) | Puoi curare, condividere e pianificare progetti PDF/CSV per i destinatari all’interno della tua organizzazione. |
| Aiuto | Accedi alla documentazione dell’Aiuto, ai video e alla [community di Experience League](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community) per Analytics. Gestisci la visibilità dei suggerimenti di Workspace e il [debugger](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md). Trova dettagli su Workspace e sui fattori che influiscono sulle [prestazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html?lang=it) del progetto. |
| Pulsante Condividi o Proprietario | Se stai utilizzando il progetto in modalità Own (Proprietario) o Edit (Modifica), il pulsante Share (Condividi) in alto a destra consente di accedere con un solo clic ai destinatari del progetto e di gestirli. Se invece utilizzi il progetto con un ruolo Duplicate (Duplica) o View (Visualizza), viene visualizzato il nome del proprietario del progetto. |

### Informazioni e impostazioni progetto {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]** fornisce informazioni a livello di progetto sul progetto attualmente attivo.

![](assets/projectinfo.png)

Le impostazioni includono:

| Impostazione | Descrizione |
|---|---|
| Progetto Nome | Nome assegnato al progetto. Puoi fare doppio clic sul nome per modificarlo. |
| Creato da | Nome del proprietario del progetto. |
| Ultima modifica | Data dell’ultima modifica apportata al progetto. |
| Tag | Elenca eventuali tag applicati a un progetto per facilitarne la categorizzazione. |
| Descrizione | La descrizione è utile per chiarire lo scopo di un progetto. Puoi fare doppio clic sulla descrizione per modificarla. |
| Conteggio istanze ripetute nel progetto | Consente di specificare se conteggiare o meno, per i rapporti, le istanze ripetute. Ad esempio, questa impostazione (se attivata) tratta più visualizzazioni di pagina consecutive sulla stessa pagina di più visualizzazioni di pagina. Con questa opzione, vengono conteggiati come visualizzazione a pagina singola (influisce solo su determinate metriche, come le visite a pagina singola). **Nota**: Questa impostazione non si applica alle visualizzazioni Flusso o Abbandono. |
| [Palette dei colori del progetto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=it) | Per cambiare la palette di colori utilizzata per le categorie in Workspace, puoi scegliere una delle palette predefinite ottimizzate per il daltonismo o specificarne una personalizzata. Questa funzione interessa numerosi elementi in Workspace, compresa la maggior parte delle visualizzazioni. |
| [Densità di visualizzazione](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=it) | Consente di visualizzare più dati nella schermata riducendo la spaziatura verticale della barra a sinistra, tabelle a forma libera e tabelle a coorte. |

## Barra a sinistra {#left-rail}

Nel progetto Workspace, puoi accedere a [pannelli](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it), tabelle, [visualizzazioni](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=it) e [componenti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) dalla barra a sinistra. Si tratta degli elementi di base del progetto.

Puoi anche accedere a visualizzazioni e pannelli dal [pannello vuoto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=it).

I componenti (dimensioni, metriche, segmenti, intervalli di date) nella barra a sinistra si riferiscono alla suite di rapporti del pannello attivo. Il pannello attivo è evidenziato da un bordo blu e la suite di rapporti attiva è elencata nella parte superiore della barra dei componenti.

![](assets/left-rail.png)

## Area di lavoro del progetto {#canvas}

Nell’area di lavoro del progetto puoi raccogliere i pannelli, le tabelle, le visualizzazioni e i componenti con cui intendi generare le analisi. Un progetto può contenere diversi pannelli, e ciascun pannello può contenere più tabelle e visualizzazioni.

I pannelli sono utili per organizzare i progetti in base a specifici periodi di tempo, suite di rapporti o casi di utilizzo di analisi. Il pannello attivo è evindenziato da un bordo blu e determina quali componenti sono disponibili nella barra a sinistra.

A seconda del punto iniziale scelto per i progetti, l’area di lavoro presenta una [tabella a forma libera](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=it) o un [pannello vuoto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html). Il modo più rapido per iniziare l’analisi consiste nel selezionare uno o più componenti e semplicemente trascinarli nell’area di lavoro del progetto. Viene creata automaticamente una tabella di dati. [Scopri di più](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html) sulle diverse opzioni per la creazione di una tabella. Per maggiori informazioni su come creare il primo progetto, segui questo [tutorial](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=it#training-tutorial).

![](assets/canvas.png)

## Project Manager {#manager}

I progetti di Analysis Workspace possono essere gestiti da **Analytics > Components >  Projects** (Componenti > Progetti). Lo strumento per la gestione dei progetti mostra gli elementi creati da uno specifico utente. La proprietà del progetto può essere trasferita a un nuovo utente da Admin > Analytics Users &amp; Assets > Transfer Assets (Amministrazione > Utenti e risorse di Analytics > Trasferisci risorse).

Nella finestra per la gestione dei progetti è possibile aggiungere, assegnare tag, condividere, duplicare/copiare e altro ancora. Per cercare un progetto puoi utilizzare la barra di ricerca o le opzioni filtro disponibili nella barra a sinistra. Puoi filtrare per tag, proprietari, tipo di progetto e altro ancora.

![](assets/project-manager.png)

Di seguito sono riportate le azioni più comuni per la gestione dei progetti, che possono essere eseguite su uno o più progetti alla volta:

| Azione | Descrizione |
|---|---|
| Add | Crea un nuovo progetto da zero o inizia da un [modello](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html). |
| Tag (Assegna tag) o Approve (Approva) | Scegli Tag (Assegna tag) o Approve (Approva) per organizzare i progetti e semplificarne la ricerca. |
| [Condividi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Rendi un progetto disponibile ad altri utenti di Analysis Workspace all’interno dell’organizzazione. |
| Elimina | Elimina il progetto. |
| Rinomina | Modifica il nome del progetto. |
| Copia | Crea un duplicato del progetto. Viene creato un nuovo progetto, con un nuovo ID progetto. Eventuali condivisioni o pianificazioni collegate al progetto originale non vengono copiate. |
| Export to CSV (Esporta in CSV) | Scarica il progetto come file CSV, contenente dati in formato solo testo. |
