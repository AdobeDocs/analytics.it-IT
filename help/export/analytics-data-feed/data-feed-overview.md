---
description: I dati raccolti da siti Web, app mobili o caricati tramite API di servizi Web o origini dati, vengono elaborati e memorizzati  Adobe  Data Warehouse. Questi dati clickstream non elaborati formano il set di dati utilizzato da  Adobe Analytics.
keywords: clickstream;data feed;datafeed;Data Feed
title: Panoramica sui feed dati di Analytics
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
translation-type: tm+mt
source-git-commit: f6f638bcd6a9630d857996a44312dbb739a0c2a8
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 7%

---


# Panoramica sui feed dati di Analytics

I feed di dati sono un modo efficace per estrarre dati grezzi da  Adobe Analytics. Questi dati non elaborati possono essere utilizzati in altre piattaforme esterne  Adobe per utilizzarli a discrezione dell&#39;azienda. I dati vengono consegnati in batch orari al termine di ogni ora, o in batch giornalieri al termine di ogni giorno.

## Prerequisiti

Prima di utilizzare i feed di dati, accertatevi di soddisfare tutti i seguenti requisiti.

* Siti e credenziali FTP a portata di mano. I feed di dati possono essere inviati solo a una destinazione server. In genere, l&#39;organizzazione fornisce le credenziali FTP.  Adobe può fornire una posizione FTP con una quantità modesta di spazio di archiviazione su richiesta. Contatta l&#39;Assistenza clienti per richiedere una destinazione FTP per i feed di dati.
* Un&#39;implementazione di lavoro che invia i dati a  server di raccolta dati di Adobe. Consulta [Convalida e pubblicazione di un’implementazione in Launch](/help/implement/launch/validate-publish-prod.md) nella guida per l’utente Implementa.
* Il tuo account è un amministratore di prodotto Analytics oppure il tuo account appartiene a un profilo di prodotto con accesso ai feed di dati.

## Passaggi per iniziare

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
2. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
3. Nella barra di navigazione superiore, andate a Admin (Amministratore) > Data Feed (Feed dati).
4. Fai clic su [!UICONTROL Add]. Viene visualizzata una nuova pagina con tre categorie principali: [!UICONTROL Feed information], [!UICONTROL Destination]e [!UICONTROL Data Column Definitions].
5. Compila [!UICONTROL Feed Information] i campi.
   * Nome: Qualsiasi nome desiderato, ad esempio &quot;Feed dati di prova&quot;.
   * Suite di rapporti: Seleziona la suite di rapporti desiderata.
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
   * Selezionate l&#39;ultimo modello &quot;Tutti  Adobe Columns&quot; nel menu a discesa.
   * Formato di compressione: Gzip
   * Tipo di pacchetto: Più file
   * Manifesto: Nessun file
8. Click [!UICONTROL Save] in the top right.
9. Una volta salvato, viene avviata l&#39;elaborazione dei dati storici. Al termine dell&#39;elaborazione dei dati per un giorno, il file viene inserito sul sito FTP.
10. Effettuate l&#39;accesso al sito FTP utilizzando Esplora risorse o un client FTP dedicato.
11. Scaricate il file di feed di dati compressi nel computer locale.
12. Decomprimete il file compresso utilizzando un programma che supporta le estensioni di `.tar.gz` file.
13. Aprite il `hit_data.tsv` file nel foglio di calcolo o nell’applicazione di database desiderata per visualizzare i dati non elaborati per quel giorno.

## Passaggi successivi

Una volta compreso il flusso di lavoro di base per l’ottenimento dei feed di dati, potete collaborare con i team all’interno dell’organizzazione per memorizzare o trasferire dati non elaborati in un database.

* [Creare un feed](create-feed.md)di dati: Dettagli tecnici per la creazione di un feed di dati, con informazioni più dettagliate sui singoli campi
* [Gestire i feed](df-manage-feeds.md)di dati: Scopri di più sulla navigazione nell&#39;interfaccia del feed di dati
* [Contenuto](c-df-contents/datafeeds-contents.md)feed dati: Comprendere cosa contiene il file compresso
* [Definizioni](c-df-contents/datafeeds-reference.md)delle colonne di dati: Un elenco completo di tutte le colonne disponibili

## Risorse aggiuntive

Video sulla navigazione dell’interfaccia del feed di dati:

>[!VIDEO](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/exporting/data-feeds/data-feeds-management-ui.html)
