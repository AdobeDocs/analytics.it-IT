---
description: I dati raccolti da siti web, app mobili o caricati utilizzando API di servizi web o origini dati, vengono elaborati e memorizzati nella Data Warehouse di Adobe. Questi dati click-stream non elaborati formano il set di dati utilizzato da Adobe Analytics.
keywords: clickstream;feed dati;datafed;feed dati
title: Panoramica sui feed dati di Analytics
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 7%

---

# Panoramica sui feed dati di Analytics

I feed di dati sono un modo potente per estrarre dati grezzi da Adobe Analytics. Questi dati non elaborati possono essere utilizzati in altre piattaforme al di fuori di Adobe per utilizzarli a discrezione della tua organizzazione. I dati vengono consegnati in batch orari alla conclusione di ogni ora o in batch giornalieri alla conclusione di ogni giorno.

## Prerequisiti

Prima di utilizzare i feed di dati, verifica di soddisfare tutti i seguenti requisiti.

* Avere a portata di mano un sito FTP e le relative credenziali. I feed di dati possono essere inviati solo a una destinazione server. In genere, l’organizzazione fornisce le credenziali FTP. Adobe può fornire una posizione FTP con una quantità modesta di archiviazione su tua richiesta. Contatta l’Assistenza clienti per richiedere una destinazione FTP per i feed di dati.
* Implementazione funzionante che invia dati ai server di raccolta dati di Adobe. Consulta [Convalidare e pubblicare un&#39;implementazione in Launch](/help/implement/launch/validate-publish-prod.md) nella guida utente Implementa.
* Il tuo account è un amministratore di prodotto Analytics oppure appartiene a un profilo di prodotto con accesso ai feed di dati.

## Passaggi da intraprendere

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
2. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
3. Nella barra di navigazione superiore, seleziona Amministratore > Feed dati.
4. Fai clic su [!UICONTROL Add]. Viene visualizzata una nuova pagina con tre categorie principali: [!UICONTROL Feed information], [!UICONTROL Destination] e [!UICONTROL Data Column Definitions].
5. Compila i campi [!UICONTROL Feed Information].
   * Nome: Qualsiasi nome desiderato, ad esempio &quot;Feed dati di test&quot;.
   * Suite di rapporti: Seleziona la suite di rapporti desiderata.
   * Invia e-mail al termine: Immetti l’e-mail.
   * Intervallo di feed: Seleziona l’intervallo desiderato (orario o giornaliero).
   * Elaborazione ritardata: Può essere lasciato come [!UICONTROL No Delay].
   * Date di inizio e fine: Seleziona una data di inizio da diversi giorni fa e oggi come data di fine.
6. Compila i campi [!UICONTROL Destination].
   * Tipo: FTP
   * Host: Immetti l&#39;URL di destinazione FTP desiderato. Ad esempio, `ftp://ftp.omniture.com`.
   * Percorso: Può essere lasciato vuoto
   * Nome utente: Immetti il nome utente per accedere al sito FTP.
   * Password e conferma password: Immetti la password per accedere al sito FTP.
7. Compila [!UICONTROL Data Column Definitions].
   * Seleziona il modello &quot;All Adobe Columns&quot; più recente nel menu a discesa.
   * Formato di compressione: Gzip
   * Tipo di imballaggio: File multipli
   * Manifesto: Nessun file
8. Fai clic su [!UICONTROL Save] in alto a destra.
9. Una volta salvato, inizia l&#39;elaborazione dei dati storici. Al termine dell&#39;elaborazione dei dati per un giorno, il file viene inserito sul sito FTP.
10. Accedi al sito FTP utilizzando Esplora risorse o un client FTP dedicato.
11. Scarica il file di feed dati compressi sul computer locale.
12. Decomprimi il file compresso utilizzando un programma che supporta le estensioni di file `.tar.gz`.
13. Apri il file `hit_data.tsv` nel foglio di calcolo o nell’applicazione di database scelta per visualizzare i dati non elaborati per quel giorno.

## Passaggi successivi

Una volta compreso il flusso di lavoro di base per l’ottenimento dei feed di dati, puoi lavorare con i team all’interno della tua organizzazione per archiviare o acquisire dati non elaborati in un database.

* [Creare un feed](create-feed.md) di dati: Dettagli tecnici per la creazione di un feed di dati, con informazioni più dettagliate sui singoli campi
* [Gestire i feed](df-manage-feeds.md) dati: Ulteriori informazioni sulla navigazione nell’interfaccia feed dati
* [Contenuto](c-df-contents/datafeeds-contents.md) del feed dati: Comprendere cosa c&#39;è all&#39;interno del file compresso
* [Definizioni](c-df-contents/datafeeds-reference.md) delle colonne dati: Un elenco completo di tutte le colonne disponibili

## Risorse aggiuntive

Video sulla navigazione nell’interfaccia feed dati:

>[!VIDEO](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/data-feeds/data-feeds-management-ui.html)
