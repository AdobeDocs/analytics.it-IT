---
description: Scopri le diverse opzioni di salvataggio, tra cui salvataggio automatico, con nome o come modello e apertura delle versioni precedenti.
title: Salvare i progetti
feature: Workspace Basics
role: User, Admin
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
source-git-commit: 20093692327f555bfd78d99b2ec03146a5f2b181
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 98%

---

# Salvare i progetti

I progetti in Analysis Workspace vengono salvati automaticamente ogni 2 minuti.

Puoi anche salvare i progetti manualmente. Quando salvi manualmente un progetto sono disponibili opzioni aggiuntive, ad esempio l’aggiunta di tag o note.

## Salvare i progetti manualmente {#Save}

Quando salvi manualmente un progetto in Analysis Workspace sono disponibili varie opzioni.

Per salvare manualmente un progetto:

1. Con il progetto aperto in Analysis Workspace, seleziona **[!UICONTROL Project]** (Progetto), quindi scegli tra le seguenti opzioni:

   | Azione | Descrizione |
   |---|---| 
   | **[!UICONTROL Save]** | Salva le modifiche apportate al progetto. Se il progetto è condiviso, i destinatari del progetto visualizzeranno anche le modifiche. Quando salvi il progetto per la prima volta, ti viene richiesto di assegnare al progetto un nome, una descrizione (facoltativa) e di aggiungere tag (facoltativi). |
   | **[!UICONTROL Save with notes]** | Prima di salvare il progetto, aggiungi note sulle modifiche apportate al progetto. Le note sono memorizzate con la versione del progetto e sono disponibili per tutti gli editor in [!UICONTROL Project] (Progetto) > [!UICONTROL Open previous version] (Apri versione precedente). |
   | **[!UICONTROL Save as]** | Crea un duplicato del progetto. Il progetto originale non subirà modifiche. |
   | **[!UICONTROL Save as template]** | Salva il progetto come [modello](/help/analyze/analysis-workspace/templates/create-templates.md) che diventa disponibile per la tua organizzazione in **[!UICONTROL Project > New]** |

## Salvataggio automatico {#Autosave}

Tutti i progetti in Analysis Workspace vengono salvati automaticamente ogni 2 minuti nel computer locale. Sono inclusi i progetti appena creati che non sono ancora stati salvati manualmente.

* **Nuovi progetti:** anche se i nuovi progetti vengono salvati automaticamente, è necessario salvarli manualmente la prima volta. Analysis Workspace richiede di salvare manualmente nuovi progetti quando si passa a un altro progetto, si chiude la scheda del browser e così via.

  Se per qualsiasi motivo perdi inaspettatamente l’accesso a un nuovo progetto creato prima di salvarlo manualmente, viene salvata una versione di ripristino del progetto nella pagina di destinazione di Analysis Workspace in una cartella denominata `Recovered Projects (Last 7 Days)` (Ultimi 7 giorni). È necessario ripristinare il progetto recuperato e salvarlo manualmente nella posizione desiderata.

  Per ripristinare un progetto recuperato:

   1. Vai alla cartella [!UICONTROL **Recovered Projects**] (Progetti recuperati) nella pagina di destinazione di Analysis Workspace.

      ![](assets/recovered-folder.png)

   1. Apri il progetto e salvalo nella posizione desiderata.

* **Progetti esistenti:** se per qualsiasi motivo esci da un progetto con modifiche non ancora salvate automaticamente, Analysis Workspace richiede di salvare le modifiche o mostra un messaggio di avviso.

  Di seguito sono riportati alcuni scenari comuni:

### Aprire un altro progetto

Se apri un progetto aggiuntivo mentre lavori a un progetto contenente modifiche non ancora salvate automaticamente, Analysis Workspace richiede di salvare il progetto in corso prima di uscire.

Sono disponibili le seguenti opzioni:

* **Save (Salva):** sostituisce la copia locale più recente del progetto salvata automaticamente con le ultime modifiche.
* **Save as (Salva con nome):** salva le modifiche più recenti come nuovo progetto. Il progetto originale viene salvato solo con le ultime modifiche salvate automaticamente.
* **Discard Changes (Elimina modifiche):** elimina le modifiche più recenti. Il progetto conserva le modifiche salvate automaticamente più recenti.

![](assets/existing-save.png)

### Uscire o chiudere una scheda

In caso di uscita o chiusura della scheda del browser durante la visualizzazione di un progetto con modifiche non ancora salvate automaticamente, il browser avverte che le modifiche non salvate andranno perse. È possibile scegliere di uscire o annullare.

![](assets/browser-image.png)

### Arresto anomalo del browser o timeout della sessione

Se il browser si blocca o se la sessione si interrompe, al prossimo accesso ad Analysis Workspace viene richiesto di ripristinare eventuali modifiche al progetto che non sono ancora state salvate automaticamente.

Di seguito è riportata la finestra di dialogo Project Recovery (Recupero progetto) che compare al primo accesso ad Analysis Workspace dopo un arresto anomalo o un timeout.

Seleziona **Yes** (Sì) per ripristinare il progetto dalla copia salvata automaticamente più recente.

Seleziona **No** per eliminare la copia salvata automaticamente e aprire l’ultima versione del progetto salvata dall’utente.

![](assets/project-recovery.png)

Per i **nuovi** progetti che non sono mai stati salvati, non è possibile recuperare le modifiche non salvate.

## Aprire una versione precedente {#previous-version}

Per aprire una versione precedente di un progetto:

1. Vai a **[!UICONTROL Project]** > **[!UICONTROL Open previous version]**

   ![](assets/previous-versions.png)

1. Rivedi l’elenco delle versioni precedenti disponibili.
   Vengono visualizzati [!UICONTROL Timestamp] e [!UICONTROL Editor], oltre a [!UICONTROL Notes] se sono state aggiunte al momento del salvataggio dell’[!UICONTROL Editor]. Le versioni senza note sono conservate per 90 giorni; le versioni con note sono memorizzate per 1 anno.
1. Seleziona una versione precedente e fai clic su **[!UICONTROL Load]** (Carica).
La versione precedente viene quindi caricata con una notifica. La versione precedente diventa la versione salvata corrente del progetto solo dopo aver fatto clic su **[!UICONTROL Save]**. Se ti sposti dalla versione caricata, quando torni viene visualizzata l’ultima versione salvata del progetto.
