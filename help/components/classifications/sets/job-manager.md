---
title: Gestione processi set di classificazione
description: Visualizza i processi di classificazione correnti e completati generati dai set di classificazione.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 51%

---

# Gestione processi set di classificazione

Gestione processi set di classificazione consente di visualizzare i processi di classificazione correnti e completati generati dai set di classificazione. Puoi inoltre utilizzare questa interfaccia per scaricare i dati o i modelli di classificazione per un particolare processo o per caricare dati aggiuntivi su un processo.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Jobs]**

Impossibile creare processi da questa interfaccia. Crea processi caricando i dati in un set di classificazione (manualmente o tramite una posizione esterna configurata), richiedendo un file di download o un file modello.

## Filtrare i set di classificazione

Il lato sinistro di Gestione processo set di classificazione fornisce le impostazioni del filtro per individuare il processo desiderato. Facendo clic sull’icona del filtro si attiva la visibilità delle impostazioni del filtro. È possibile filtrare i set di classificazione per **[!UICONTROL Classification set]**, **[!UICONTROL Completion time]**, **[!UICONTROL Status]**, **[!UICONTROL Job Type]** o **[!UICONTROL Source]**.

![Filtri processo set di classificazione](../assets/classification-set-job-filters.png)

Ulteriori opzioni di filtro sono disponibili sopra le colonne Gestione processo set di classificazione:

* **[!UICONTROL Search by title]**: cerca i processi per nome file.
* **[!UICONTROL Load more]**: Gestione processo set di classificazione visualizza inizialmente fino a 1000 processi. Se esistono più processi, fare clic su questo pulsante per caricare altri 1000 processi.
* **Mostra/Nascondi colonne**: attiva/disattiva la visibilità delle colonne oltre a [!UICONTROL Filename] e [!UICONTROL Completion time].

## Colonne di Gestione processo set di classificazione

In Gestione processo set di classificazione sono disponibili le colonne seguenti:

* **[!UICONTROL Filename]**: nome del file di caricamento o download.
* **[!UICONTROL Classification set]**: nome del set di classificazione a cui si applica il file. Puoi fare clic sul nome del set di classificazione per raggiungerne le [Impostazioni](manage/settings.md).
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
* **[!UICONTROL Job type]**: tipo di processo.
* **[!UICONTROL Source]**: origine del processo.
* **[!UICONTROL File download]**: si applica solo ai processi di download, come il download di dati di classificazione o modelli. Quando un download è pronto, questa colonna fornisce il collegamento relativo.
* **[!UICONTROL Modified lines]**: numero di righe modificate.
* **[!UICONTROL Completed lines]**: numero di righe completate.
* **[!UICONTROL Completion time]**: data e ora in cui il processo è stato completato (o non è riuscito).
