---
title: Impostazioni del set di classificazioni
description: Crea o modifica un set di classificazione.
exl-id: abf00508-5dde-4669-bf94-5eb4754888cc
source-git-commit: c849f216f8dda83070fc3f8d8b1c25fba4d2786a
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 1%

---

# Impostazioni del set di classificazioni

Configura un set di classificazione, carica dati o scarica dati.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Fai clic sul nome del set di classificazioni desiderato

Quando si modifica un set di classificazioni, sono disponibili due schede; **[!UICONTROL Schema]** e **[!UICONTROL Settings]**.

## Impostazioni

I seguenti campi sono disponibili nella [!UICONTROL Settings] e può essere modificato:

* **[!UICONTROL Name]**: Nome del set di classificazioni.
* **[!UICONTROL Description]**: Descrizione del set di classificazioni.
* **[!UICONTROL Owner name]**: Nome del proprietario.
* **[!UICONTROL Owner email]**: Indirizzo e-mail del proprietario.
* **[!UICONTROL Notify of issues]**: Elenco di indirizzi e-mail delimitati da virgole a cui vengono notificati i problemi relativi a questo set di classificazioni.
* **[!UICONTROL Tags]**: Aggiungi uno o più tag ai set di classificazioni selezionati, per organizzare o raggruppare i set di classificazioni in modo da facilitarne l’individuazione in futuro.

Altri campi sono disponibili a scopo informativo e non possono essere modificati:

* **[!UICONTROL Type]**: Tipo di classificazione tra [!UICONTROL Primary] e [!UICONTROL Lookup]. Le classificazioni principali vengono generalmente utilizzate.
* **[!UICONTROL Subscriptions]**: Suite di rapporti e variabile a cui si applica il set di classificazione. Al momento è supportata una sola suite di rapporti per un determinato set di classificazioni; è pianificato il supporto per più suite di rapporti.

## Schema

Visualizza le dimensioni di classificazione attualmente configurate per la sottoscrizione. Sono disponibili i seguenti pulsanti:

* **[!UICONTROL Upload]**: Carica manualmente i dati di classificazione per una o più dimensioni di classificazione. Sono supportati i file JSON, CSV, TSV e TAB. Il caricamento di un file valido mostra un’anteprima della tabella dei dati da classificare.
   * **[!UICONTROL File encoding]**: Seleziona il file encoding corretto utilizzando questo menu a discesa. Le opzioni valide includono [!UICONTROL UTF-8] e [!UICONTROL Latin1].
   * **[!UICONTROL List delimiter]**: Selezionare il delimitatore elenco corretto. Se utilizzi un file scaricato o un file modello, assicurati che il [!UICONTROL List delimiter] qui corrisponde al [!UICONTROL List delimiter] quando il file è stato scaricato.
   * **[!UICONTROL Apply]**: Salva i dati di classificazione caricati nel set di classificazione.

   ![Caricamento set di classificazioni](../assets/classification-set-upload.png)

* **[!UICONTROL Download]**: Scarica i valori chiave e le relative colonne di classificazione.
   * **[!UICONTROL Rows]**: Il numero massimo di righe da includere nel file di download.
   * **[!UICONTROL Download rows received between]**: Selettore data calendario che consente di filtrare i valori chiave in base a quando vengono visualizzati nel rapporto. Se un valore chiave non è stato raccolto in questo intervallo di date, non viene visualizzato nel file scaricato.
   * **[!UICONTROL Data returned]**: Elenco a discesa che consente di filtrare i valori chiave inclusi nel file scaricato in base ai dati di classificazione associati.
      * **[!UICONTROL All classified values]**: Include righe in cui i dati di classificazione sono inclusi in almeno una colonna.
      * **[!UICONTROL All unclassified values]**: Include righe in cui mancano i dati di classificazione in almeno una colonna.
   * **[!UICONTROL File format]**: Elenco a discesa che determina il formato del file in cui si trova il file di download. Le opzioni includono [!UICONTROL JSON], [!UICONTROL Comma separated values]e [!UICONTROL Excel tab separated values].
   * **[!UICONTROL File encoding]**: Elenco a discesa che determina la codifica del file. Le opzioni includono [!UICONTROL UTF-8] e [!UICONTROL Latin1]. Si consiglia l&#39;UTF-8.
   * **[!UICONTROL List delimiters]**: Elenco a discesa che determina il delimitatore di elenco che separa le colonne di classificazione su ogni riga.

   ![Download set di classificazioni](../assets/classification-set-download.png)

* **[!UICONTROL Template]**: Scarica un file modello. Questo file è simile al [!UICONTROL Download] , ma non contiene dati di classificazione o valori chiave.
   * **[!UICONTROL File format]**: Elenco a discesa che determina il formato di file in cui si trova il file modello. Le opzioni includono [!UICONTROL Comma separated values]e [!UICONTROL Excel tab separated values].
   * **[!UICONTROL File encoding]**: Elenco a discesa che determina la codifica del file. Le opzioni includono [!UICONTROL UTF-8] e [!UICONTROL Latin1]. Si consiglia l&#39;UTF-8.
   * **[!UICONTROL List delimiters]**: Elenco a discesa che determina il delimitatore di elenco che separa le colonne di classificazione su ogni riga.
* **[!UICONTROL Job history]**: Collegamento che ti porta al [Responsabile del lavoro](job-manager.md), mostra i processi solo per questo set di classificazione.

   ![Modello del set di classificazioni](../assets/classification-set-template.png)
