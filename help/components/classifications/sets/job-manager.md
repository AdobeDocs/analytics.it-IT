---
title: Gestione processo set di classificazione
description: Visualizza i lavori di classificazione correnti e completati generati dai set di classificazione.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 100%

---

# Gestione processi set di classificazione

Gestione processi set di classificazione consente di visualizzare i processi di classificazione correnti e completati generati dai set di classificazione. Puoi inoltre utilizzare questa interfaccia per scaricare i dati o i modelli di classificazione per un particolare processo o per caricare dati aggiuntivi su un processo.

>[!NOTE]
>
>Questa funzione sarà disponibile per tutti i clienti che hanno eseguito la migrazione delle suite di rapporti alla nuova architettura Classificazioni. Per ulteriori informazioni, contatta l’Assistenza clienti Adobe o il tuo Account Manager.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Jobs]**

Non è possibile creare processi da questa interfaccia. Puoi invece creare processi caricando i dati in un set di classificazione, richiedendo un file di download o un file modello.

## Filtrare i set di classificazione

Il lato sinistro di Gestione processo set di classificazione fornisce le impostazioni del filtro per individuare il processo desiderato. Facendo clic sull’icona del filtro si attiva la visibilità delle impostazioni del filtro. Puoi filtrare i set di classificazione per **[!UICONTROL Classification Set]**, **[!UICONTROL Completion time]** oppure **[!UICONTROL Status]**.

![Filtri di processo per set di classificazione](../assets/classification-set-job-filters.png)

Ulteriori opzioni di filtro sono disponibili sopra le colonne di Gestione processo set di classificazione:

* **[!UICONTROL Search by title]**: cerca i processi per nome file.
* **[!UICONTROL Load more]**: Gestione processo set di classificazione visualizza inizialmente fino a 1000 processi. Fai clic su questo pulsante per caricare altri 1000 processi.
* **Mostra/Nascondi colonne**: attiva/disattiva la visibilità delle colonne oltre a [!UICONTROL Filename] e [!UICONTROL Completion time].

## Colonne di Gestione processo set di classificazione

In Gestione processo set di classificazione sono disponibili le colonne seguenti:

* **[!UICONTROL Filename]**: nome del file di caricamento o download.
* **[!UICONTROL Classification Set]**: nome del set di classificazione a cui si applica il file. Puoi fare clic sul nome del set di classificazione per raggiungerne le [Impostazioni](settings.md).
* **[!UICONTROL Size]**: dimensione del file.
* **[!UICONTROL Status]**: stato del processo di elaborazione del file.
   * **[!UICONTROL Created]**: lavoro inviato.
   * **[!UICONTROL Queued]**: file pronto per l’elaborazione e in attesa di venire elaborato da un server di classificazione.
   * **[!UICONTROL Validated]**: file valido e in attesa di elaborazione.
   * **[!UICONTROL Failed validation]**: file formattato in modo errato o comunque non valido. Il file non viene sottoposto a elaborazione.
   * **[!UICONTROL Processing]**: file elaborato attivamente tramite Adobe.
   * **[!UICONTROL Failed processing]**: elaborazione del file non riuscita.
   * **[!UICONTROL Complete]**: elaborazione completata. I dati di classificazione sono visibili nel reporting.
   * **[!UICONTROL Failed]**: errore generico non correlato alla convalida o all’elaborazione.
* **[!UICONTROL Type]**: tipo di processo.
* **[!UICONTROL File download]**: si applica solo ai processi di download, come il download di dati di classificazione o modelli. Quando un download è pronto, questa colonna fornisce il collegamento relativo.
* **[!UICONTROL Completion time]**: data e ora in cui il processo è stato completato (o non è riuscito).
