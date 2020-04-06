---
description: Data that is collected from web sites, mobile apps, or is uploaded using web service APIs or data sources, is processed and stored in Adobe's Data Warehouse. Questi dati clickstream non elaborati formano il set di dati utilizzato da Adobe Analytics.
keywords: clickstream;data feed;datafeed;Data Feed
title: Panoramica sui feed dati di Analytics
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Panoramica sui feed dati di Analytics

I feed di dati sono un modo potente per estrarre dati grezzi da Adobe Analytics. Questi dati non elaborati possono essere utilizzati in altre piattaforme esterne ad Adobe per l&#39;utilizzo a discrezione dell&#39;azienda. I dati vengono consegnati in batch orari al termine di ogni ora, o in batch giornalieri al termine di ogni giorno.

## Prerequisiti

Prima di utilizzare i feed di dati, accertatevi di soddisfare tutti i seguenti requisiti.

* Siti e credenziali FTP a portata di mano. I feed di dati possono essere inviati solo a una destinazione server. In genere, l&#39;organizzazione fornisce le credenziali FTP. Adobe può fornire una posizione FTP con una quantità modesta di spazio di archiviazione su richiesta. Contatta l&#39;Assistenza clienti per richiedere una destinazione FTP per i feed di dati.
* Un&#39;implementazione di lavoro che invia dati ai server di raccolta dati Adobe. Consulta [Convalida e pubblicazione di un’implementazione in Launch](/help/implement/launch/validate-publish-prod.md) nella guida per l’utente Implementa.
* Il tuo account è un amministratore di prodotto Analytics oppure il tuo account appartiene a un profilo di prodotto con accesso ai feed di dati.

## Steps to get started

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
2. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
3. In the top navigation bar, navigate to Admin > Data feeds.
4. Fai clic su [!UICONTROL Add]. A new page appears with three main categories: [!UICONTROL Feed information], [!UICONTROL Destination], and [!UICONTROL Data Column Definitions].
5. Fill out [!UICONTROL Feed Information] fields.
   * Name: Any desired name, such as &quot;Test data feed&quot;.
   * Report suite: Select the desired report suite.
   * E-mail al termine: Inserite il messaggio e-mail.
   * Intervallo feed: Selezionate l’intervallo desiderato (orario o giornaliero).
   * Elaborazione ritardata: Può essere lasciato come [!UICONTROL No Delay].
   * Date di inizio e fine: Selezionate una data di inizio da diversi giorni fa e quella odierna come data di fine.
6. Compila [!UICONTROL Destination] i campi.
   * Tipo: FTP
   * Host: Inserite l&#39;URL di destinazione FTP desiderato. Ad esempio, `ftp://ftp.omniture.com`.
   * Percorso: Può essere lasciato vuoto
   * Nome utente: Immettete il nome utente per accedere al sito FTP.
   * Password e conferma password: Immettete la password per accedere al sito FTP.
7. Compilate [!UICONTROL Data Column Definitions].
   * Selezionate il modello &quot;Tutte le colonne Adobe&quot; più recente nel menu a discesa.
   * Formato di compressione: Gzip
   * Tipo di pacchetto: Più file
   * Manifesto: Nessun file
8. Fate clic [!UICONTROL Save] in alto a destra.
9. Una volta salvato, viene avviata l&#39;elaborazione dei dati storici. Al termine dell&#39;elaborazione dei dati per un giorno, il file viene inserito sul sito FTP.
10. Effettuate l&#39;accesso al sito FTP utilizzando Esplora risorse o un client FTP dedicato.
11. Download the compressed data feed file to your local machine.
12. Unzip the compressed file using a program that supports `.tar.gz` file extensions.
13. Aprite il `hit_data.tsv` file nel foglio di calcolo o nell’applicazione di database desiderata per visualizzare i dati non elaborati per quel giorno.

## Passaggi successivi

Una volta compreso il flusso di lavoro di base per l’ottenimento dei feed di dati, potete collaborare con i team all’interno dell’organizzazione per memorizzare o trasferire dati non elaborati in un database.

* [Creare un feed](create-feed.md)di dati: Dettagli tecnici per la creazione di un feed di dati, con informazioni più dettagliate sui singoli campi
* [Gestire i feed](df-manage-feeds.md)di dati: Scopri di più sulla navigazione nell&#39;interfaccia del feed di dati
* [Contenuto](c-df-contents/datafeeds-contents.md)feed dati: Comprendere cosa contiene il file compresso
* [Definizioni](c-df-contents/datafeeds-reference.md)delle colonne di dati: Un elenco completo di tutte le colonne disponibili

## Risorse aggiuntive

Video sulla navigazione dell’interfaccia del feed di dati:

>[!VIDEO](https://www.youtube.com/watch?v=m_fb--gNtR4)
