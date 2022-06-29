---
title: Gestione processi set di classificazioni
description: Visualizza i lavori di classificazione correnti e completati generati dai set di classificazioni.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 0%

---

# Gestione processi set di classificazioni

Gestione processi set di classificazione consente di visualizzare i processi di classificazione correnti e completati generati dai set di classificazioni. Puoi inoltre utilizzare questa interfaccia per scaricare i dati o i modelli di classificazione per un particolare lavoro o per caricare dati aggiuntivi su un processo.

>[!NOTE]
>
>Questa funzione è attualmente in versione limitata. Se desideri accedere a questa funzione, contatta l’Assistenza clienti Adobe o il tuo Account Manager, che può inoltrare la tua richiesta al team Classificazioni per il provisioning.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Jobs]**

Non è possibile creare processi da questa interfaccia. Puoi invece creare lavori caricando i dati in un set di classificazione, richiedendo un file di download o richiedendo un file modello.

## Filtra set di classificazioni

Il lato sinistro di Gestione processi set di classificazione fornisce le impostazioni del filtro per individuare il processo desiderato. Facendo clic sull’icona del filtro viene attivata la visibilità delle impostazioni del filtro. Puoi filtrare i set di classificazioni per **[!UICONTROL Classification Set]**, **[!UICONTROL Completion time]** oppure **[!UICONTROL Status]**.

![Filtri di lavoro per set di classificazioni](../assets/classification-set-job-filters.png)

Ulteriori opzioni di filtro sono disponibili sopra le colonne di Gestione processi set di classificazione:

* **[!UICONTROL Search by title]**: Cerca i lavori per nome file.
* **[!UICONTROL Load more]**: In Gestione processi set di classificazione vengono inizialmente visualizzati fino a 1000 processi. Fai clic su questo pulsante per caricare altri 1000 processi.
* **Mostra/Nascondi colonne**: Attiva/disattiva la visibilità di qualsiasi colonna oltre a [!UICONTROL Filename] e [!UICONTROL Completion time].

## Colonne di Gestione processi set di classificazioni

Le colonne seguenti sono disponibili in Gestione processi set di classificazione:

* **[!UICONTROL Filename]**: Nome del file di caricamento o download.
* **[!UICONTROL Classification Set]**: Nome del set di classificazioni a cui si applica il file. Puoi fare clic sul nome del set di classificazioni per raggiungere il [Impostazioni](settings.md).
* **[!UICONTROL Size]**: Dimensione del file.
* **[!UICONTROL Status]**: Lo stato del processo di elaborazione del file.
   * **[!UICONTROL Created]**: Il lavoro è stato sottomesso.
   * **[!UICONTROL Queued]**: Il file è pronto per l’elaborazione ed è in attesa che il file venga elaborato da un server di classificazione.
   * **[!UICONTROL Validated]**: Il file è valido e in attesa di elaborazione.
   * **[!UICONTROL Failed validation]**: Il file viene formattato in modo errato o non è comunque valido. Il file non viene sottoposto a elaborazione.
   * **[!UICONTROL Processing]**: Il file viene elaborato attivamente tramite Adobe.
   * **[!UICONTROL Failed processing]**: Elaborazione del file non riuscita.
   * **[!UICONTROL Complete]**: Elaborazione completata. I dati di classificazione sono visibili nel reporting.
   * **[!UICONTROL Failed]**: Errore generico non correlato alla convalida o all&#39;elaborazione.
* **[!UICONTROL Type]**: Tipo di processo.
* **[!UICONTROL File download]**: Si applica solo ai processi di download, ad esempio per scaricare i dati di classificazione o i modelli. Quando un download è pronto, questa colonna fornisce un collegamento per il download.
* **[!UICONTROL Completion time]**: Data e ora di completamento del processo (o non riuscito).
