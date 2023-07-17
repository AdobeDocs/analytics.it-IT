---
description: I dati raccolti da siti web, app mobili o caricati utilizzando API di servizi web o origini dati, vengono elaborati e memorizzati nel Data Warehouse di Adobe. Questi dati di click-stream non elaborati formano il set di dati utilizzato da Adobe Analytics.
keywords: clickstream;feed dati;datafeed;feed dati
title: Panoramica sui feed dati di Analytics
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: f66cc6252ecd54c143c08be1e0e7e5bf90cc42e9
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 86%

---

# Panoramica sui feed dati di Analytics

I feed di dati offrono un modo potente per estrarre dati grezzi da Adobe Analytics. Puoi utilizzare i dati non elaborati in altre piattaforme al di fuori di Adobe, in base alle esigenze della tua organizzazione. I dati vengono consegnati in batch orari alla conclusione di ogni ora oppure in batch giornalieri alla conclusione di ogni giorno.

## Prerequisiti

Prima di utilizzare i feed di dati, è necessario soddisfare tutti i seguenti requisiti.

* Un’implementazione funzionante che invia dati ai server di raccolta dati di Adobe. Consulta [Convalidare e pubblicare un’implementazione](/help/implement/launch/validate-publish-prod.md) nella Guida all’implementazione.
* Il tuo account deve essere quello di un amministratore di prodotto Analytics oppure deve appartenere a un profilo di prodotto con accesso ai feed di dati.
* Un bucket configurato su Amazon S3, Google Cloud Platform, Azure RBAC o Azure SAS.
* (Legacy: Obbligatorio solo per i tipi di destinazione FTP e SFTP legacy) Utilizza un sito FTP e le relative credenziali (credenziali FTP fornite dalla tua organizzazione).

## Risorse di feed dati consigliate

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
2. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
3. Nella barra di navigazione superiore, seleziona Admin > Data feeds (Amministrazione > Feed dati).
4. Fai clic su [!UICONTROL Add]. Viene visualizzata una nuova pagina con tre categorie principali: [!UICONTROL Feed information], [!UICONTROL Destination] e [!UICONTROL Data Column Definitions].
5. Compila i campi [!UICONTROL Feed Information].
   * Name (Nome): il nome desiderato, ad esempio “Test feed dati”.
   * Report suite (Suite di rapporti): seleziona la suite di rapporti desiderata.
   * Email when complete (Invia e-mail al termine): immetti il tuo indirizzo e-mail.
   * Feed interval (Intervallo di feed): seleziona l’intervallo desiderato (orario o giornaliero).
   * Delay processing (Ritardo elaborazione): può essere lasciato impostato su [!UICONTROL No Delay].
   * Date di inizio e fine: seleziona una data di inizio da diversi giorni fa; seleziona “today” (oggi) come data di fine.
6. Compila i campi [!UICONTROL Destination].
   * Type (Tipo): FTP
   * Host: immetti l’URL di destinazione FTP desiderato. Esempio: `ftp://ftp.omniture.com`.
   * Path (Percorso): può essere lasciato vuoto.
   * Username (Nome utente): immetti il nome utente per accedere al sito FTP.
   * Password/Confirm password (Password/Conferma password): immetti la password per accedere al sito FTP.
7. Compila [!UICONTROL Data Column Definitions].
   * Seleziona il modello &quot;All Adobe Columns&quot; (Tutti gli) più recente nell’elenco a discesa.
   * Compression format (Formato di compressione): Gzip
   * Packaging type (Tipo di pacchetto): file multipli
   * Manifest (Manifesto): nessun file
8. Fai clic su [!UICONTROL Save] in alto a destra.
9. Una volta salvata la configurazione, inizia l’elaborazione dei dati storici. Al termine dell’elaborazione dei dati per un giorno, il file viene inserito sul sito FTP.
10. Accedi al sito FTP utilizzando Esplora risorse o un client FTP dedicato.
11. Scarica il file del feed dati compresso sul computer locale.
12. Decomprimi il file compresso utilizzando un programma che supporta le estensioni di file `.tar.gz`.
13. Apri il file `hit_data.tsv` nell’applicazione per fogli di calcolo o database scelta per visualizzare i dati non elaborati per quel giorno.

## Passaggi successivi

Una volta compreso il flusso di lavoro di base per l’ottenimento dei feed di dati, puoi lavorare con i team della tua organizzazione per archiviare o acquisire dati non elaborati in un database.

* [Best practice per il feed dati](/help/export/analytics-data-feed/data-feeds-best-practices.md): best practice per la creazione e la gestione dei feed di dati.
* [Creare un feed di dati](create-feed.md): dettagli tecnici per la creazione di un feed di dati, con informazioni più dettagliate sui singoli campi
* [Gestire i feed dati](df-manage-feeds.md): ulteriori informazioni sulla navigazione nell’interfaccia del feed dati
* [Contenuti dei feed dati](c-df-contents/datafeeds-contents.md): comprendere cosa c&#39;è all&#39;interno del file compresso <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [Definizioni delle colonne dati](c-df-contents/datafeeds-reference.md): un elenco completo di tutte le colonne disponibili.
* Video sulla navigazione nell’interfaccia del feed dati:

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* Video su come trovare l’ID del proprio feed dati:

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)