---
title: Impostazioni del set di classificazioni
description: Crea o modifica un set di classificazione.
source-git-commit: c9465ea0524225494aa5067d00ca5e7aba4bca92
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

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
* **[!UICONTROL Subscriptions]**: Suite di rapporti e variabile a cui si applica il set di classificazione. Attualmente è supportata una sola suite di rapporti per un determinato set di classificazioni; è pianificato il supporto per più suite di rapporti.

## Schema

Visualizza le dimensioni di classificazione attualmente configurate per la sottoscrizione. Sono disponibili i seguenti pulsanti:

* **[!UICONTROL Upload]**: Carica manualmente i dati di classificazione per una o più dimensioni di classificazione. Sono supportati i file JSON, CSV, TSV e TAB. Il caricamento di un file valido mostra un’anteprima della tabella dei dati da classificare.
   * **[!UICONTROL File encoding]**: Seleziona il file encoding corretto utilizzando questo menu a discesa. Le opzioni valide includono [!UICONTROL UTF-8] e [!UICONTROL Latin1].
   * **[!UICONTROL List delimiter]**: Selezionare il delimitatore elenco corretto. Se utilizzi un file scaricato o un file modello, assicurati che [!UICONTROL List delimiter] qui corrisponde al [!UICONTROL List delimiter] quando il file è stato scaricato.
   * **[!UICONTROL Apply]**: Salva i dati di classificazione caricati nel set di classificazione.
