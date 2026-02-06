---
title: Gestisci processi feed dati
description: Scopri come gestire singoli lavori nei feed dati. Naviga nell’interfaccia, utilizza i filtri e cerca, quindi trova le definizioni delle colonne.
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
source-git-commit: 728e807764901ad2bd6834339e5e75348dd5a988
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 2%

---

# Gestire i processi per feed dati

I job sono singole attività che generano un file compresso. Sono create e gestite dai feed.

Per gestire i processi di feed dati:

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.

1. Seleziona l&#39;icona a 9 quadrati in alto a destra, quindi seleziona [!UICONTROL **Analytics**].

1. Nella barra di navigazione superiore, passa a [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

   Vengono visualizzati i feed di dati per tutte le suite di rapporti a cui hai accesso. Oppure, se non è stato configurato alcun feed, la pagina mostra un pulsante [!UICONTROL Create New Data Feed].

   ![Gestione feed dati](assets/data-feed-manager.png)

1. (Facoltativo) Seleziona la casella di controllo accanto al feed di dati contenente i processi che desideri visualizzare, quindi seleziona [!UICONTROL **Cronologia processi**].

   Per ulteriori informazioni, vedere [Visualizzare la cronologia dei processi per un feed di dati](#view-job-history-for-a-data-feed).

## Filtrare e cercare

Puoi filtrare e cercare per individuare esattamente il processo che stai cercando.

A sinistra, fai clic sull’icona del filtro per mostrare o nascondere le opzioni di filtro. I filtri sono organizzati per categoria. Fai clic sulla freccia per comprimere o espandere le categorie di filtro. Fai clic sulla casella di controllo per applicare un filtro.

![Filtro](assets/jobs-filter.png)

Utilizzare la ricerca per individuare un processo in base al nome.

![Ricerca](assets/search.png)

## Ordinare e personalizzare le colonne

Ogni job mostra diverse colonne che forniscono informazioni sul job. È possibile ordinare le informazioni in ogni colonna e personalizzare le colonne visualizzate.

### Ordinare le colonne

Seleziona un’intestazione di colonna per ordinarla in ordine crescente. Seleziona di nuovo un’intestazione di colonna per ordinarla in ordine decrescente.

### Personalizza colonne

Per regolare le colonne visibili nella tabella:

1. Seleziona l&#39;icona della colonna ![Icona della colonna](assets/customize-columns-icon.png) in alto a destra.

1. Nella finestra di dialogo Personalizza tabella selezionare ogni colonna che si desidera visualizzare e deselezionare ogni colonna che si desidera nascondere.

   Sono disponibili le seguenti colonne:

* **Nome feed**: colonna obbligatoria. Visualizza il nome del feed. I processi creati dallo stesso feed hanno lo stesso nome di feed.
* **ID feed**: visualizza l&#39;ID feed, un identificatore univoco. I processi creati dallo stesso feed hanno lo stesso ID feed.
* **Suite di rapporti**: la suite di rapporti da cui il processo fa riferimento ai dati.
* **ID suite di rapporti**: identificatore univoco della suite di rapporti.
* **Intervallo**: intervallo del feed.
* **Tipo di destinazione**: il tipo di destinazione del feed.
* **Destinazione**: la destinazione del feed.
* **Proprietario**: proprietario del feed.
* **Stato**: lo stato del feed.
   * In attesa di dati: il processo è operativo e i dati per l’intervallo di reporting sono in fase di raccolta.
   * Elaborazione: il processo sta creando i file di dati e si sta preparando per inviarli.
   * Completato: il processo è stato completato senza alcun problema.
   * Non riuscito: processo non completato. Consulta [Risoluzione dei problemi dei feed di dati](troubleshooting.md) per determinare la causa dell&#39;errore.
   * In attesa di esportazione: i dati per l’intervallo di reporting non sono ancora stati completamente elaborati.
   * Nessun dato: non sono presenti dati nella suite di rapporti per l’intervallo di reporting richiesto.
* **Ultima modifica**: ora dell&#39;ultima modifica del feed.
* **Data inizio**: ora di inizio del processo. La data e l’ora vengono visualizzate nel fuso orario della suite di rapporti con offset GMT. I feed giornalieri in genere iniziano vicino alla mezzanotte nel fuso orario della suite di rapporti.
* **Data di fine**: ora di fine del processo. La data e l’ora vengono visualizzate nel fuso orario della suite di rapporti con offset GMT.

## Visualizzare la cronologia dei processi per un feed di dati

Puoi visualizzare un elenco dei processi di feed dati passati per un dato feed di dati, insieme alle informazioni su ciascun processo.

Per visualizzare la cronologia dei processi per un feed di dati:

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

   ![Gestione feed dati](assets/data-feed-manager.png)

1. Selezionare la casella di controllo accanto al feed di dati di cui si desidera visualizzare la cronologia dei processi, quindi selezionare [!UICONTROL **Cronologia processi**].

   Viene visualizzata la cronologia dei processi di feed dati, con le seguenti informazioni disponibili su ciascun processo (seleziona l’icona della colonna per aggiungere colonne che non sono visibili per impostazione predefinita):

   * **[!UICONTROL Request period begin]**

   * **[!UICONTROL Request period end]**

   * **[!UICONTROL Scheduled]**

   * **[!UICONTROL Started]**

   * **[!UICONTROL Finished]**

   * **[!UICONTROL Run #]**

   * **[!UICONTROL Status]**

   * **[!UICONTROL Error code]**

   * **[!UICONTROL Error message]**

## Invia di nuovo processi feed dati

Puoi inviare nuovamente un processo di feed dati se desideri inviare nuovamente il file di feed dati con gli stessi dati ed elaborazione di quando è stato inviato originariamente. In alternativa, è possibile [rielaborare un processo di feed dati](#reprocess-data-feed-jobs).

Per inviare nuovamente uno o più processi di feed dati:

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Selezionare la casella di controllo accanto al feed di dati contenente i processi che si desidera inviare di nuovo, quindi selezionare [!UICONTROL **Cronologia processi**].

1. Selezionare la casella di controllo accanto a uno o più processi di feed dati, quindi selezionare **[!UICONTROL Resend]**. <!-- What does the status need to be? Error, ... -->

   ![Rielabora processo feed dati](assets/data-feed-job-resend.png)

## Rielabora processi feed dati

Puoi rielaborare i dati di origine di un processo di feed dati e inviarli nuovamente con i dati rielaborati. In alternativa, è possibile [inviare nuovamente un processo di feed dati](#resend-data-feed-jobs).

Per rielaborare uno o più processi di feed dati:

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Selezionare la casella di controllo accanto al feed di dati contenente i processi che si desidera rielaborare, quindi selezionare [!UICONTROL **Cronologia processi**].

1. Selezionare la casella di controllo accanto a uno o più processi di feed dati, quindi selezionare **[!UICONTROL Reprocess]**. <!-- What does the status need to be? Error, ... -->

   ![Rielabora processo feed dati](assets/data-feed-job-reprocess.png)
