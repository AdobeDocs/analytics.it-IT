---
description: Questa sezione descrive i file trovati in una consegna di feed dati.
keywords: Feed dati;processo;contenuto;manifesto;file;ricerca;hit;contenuti consegna
subtopic: data feeds
title: 'Contenuti feed dati: panoramica'
feature: Data Feeds
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 2%

---

# Contenuti feed dati: panoramica

Le sezioni seguenti descrivono come accedere e comprendere i file presenti in una consegna di feed di dati.

## Accedere al contenuto del feed dati

Per accedere al contenuto di un feed dati:

1. Accedi al sito di destinazione del feed di dati.

   Questo è il sito di destinazione configurato durante la creazione del feed di dati, ad esempio un bucket Amazon S3 o Google Cloud Platform.

1. Scarica il file del feed dati compresso sul computer locale.

1. Decomprimi il file compresso utilizzando un programma che supporta le estensioni di file `.tar.gz`.

1. Apri il file `hit_data.tsv` nell&#39;applicazione per fogli di calcolo o database scelta per visualizzare i dati non elaborati per quel giorno. —>

## File manifesto {#feed-manifest}

Il file manifesto contiene i seguenti dettagli su ciascun file che fa parte del set di dati caricato:

* Nome file
* Dimensione file
* Hash MD5
* Numero di record contenuti nel file

Il file manifest ha lo stesso formato di un file manifest Java JAR.

Il file manifesto viene sempre recapitato per ultimo come file `.txt` separato, in modo che la sua esistenza indichi che il set di dati completo per tale periodo di richiesta è già stato recapitato. I file manifesto sono denominati in base a quanto segue:

```text
[rsid]_[YYYY-mm-dd].txt
```

Un file manifesto tipico contiene dati simili ai seguenti:

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: rsid_date-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-rsid_date.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Ogni file manifesto contiene un&#39;intestazione che indica il numero totale di file di ricerca, file di dati e il numero totale di record in tutti i file di dati. Questa intestazione è seguita da più sezioni contenenti informazioni per ciascun file incluso nella consegna del feed di dati.

Alcuni feed sono configurati per ricevere un file `.fin` invece di un manifesto `.txt`. `.fin` indica che il caricamento è completo, ma i metadati in esso contenuti sono in un formato precedente.

## Ricercare file

Alcune colonne di feed dati restituiscono un numero che corrisponde al valore effettivo. I file di ricerca vengono utilizzati per far corrispondere un numero di una colonna di feed dati con un valore effettivo. Ad esempio, il valore &quot;497&quot; nella colonna dei dati dell&#39;hit `browser` indica che l&#39;hit proviene da &quot;Microsoft Internet Explorer 8&quot; se si cerca in `browser.tsv`.

Tieni presente che `column_headers.tsv` e `event_list.tsv` sono specifici per il feed di dati e la suite di rapporti. Altri file, ad esempio `browser.tsv`, sono generici.

I file di ricerca vengono consegnati insieme in un file ZIP compresso denominato in base ai seguenti elementi:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* **`column_headers.tsv`**: una singola riga contenente le intestazioni di colonna per `hit_data.tsv`.
* **`browser.tsv`**: esegue il mapping dell&#39;ID browser (colonna del feed `browser`) al nome descrittivo del browser.
* **`browser_type.tsv`**: esegue il mapping dell&#39;ID del browser (colonna del feed `browser`) al tipo di browser.
* **`color_depth.tsv`**: esegue il mapping dell&#39;ID di profondità del colore (colonna di feed `color`) alla profondità del colore.
* **`connection_type.tsv`**: esegue il mapping dell&#39;ID del tipo di connessione (colonna del feed `connection_type`) al tipo di connessione.
* **`country.tsv`**: esegue il mapping dell&#39;ID paese (colonna del feed `country`) al nome del paese.
* **`javascript_version.tsv`**: esegue il mapping dell&#39;ID versione di JavaScript (colonna del feed `javascript`) alla versione di JavaScript.
* **`languages.tsv`**: mappa l&#39;ID lingua (colonna del feed `language`) sulla lingua.
* **`operating_systems.tsv`**: esegue il mapping dell&#39;ID del sistema operativo (colonna del feed `os`) al nome del sistema operativo.
* **`plugins.tsv`**: esegue il mapping dell&#39;ID del plug-in (la colonna del feed `plugin`) al rispettivo nome del plug-in.
* **`resolution.tsv`**: esegue il mapping dell&#39;ID risoluzione (colonna del feed `resolution`) alla risoluzione del monitoraggio.
* **`referrer_type.tsv`**: esegue il mapping dell&#39;ID del tipo di referente (colonna del feed `ref_type`) al tipo di referente.
* **`search_engines.tsv`**: esegue il mapping dell&#39;ID del motore di ricerca (colonna del feed `search_engine`) al nome del motore di ricerca.
* **`event.tsv`**: esegue il mapping di ogni ID evento (la colonna del feed `event_list`) al rispettivo nome evento.

## File di dati di hit

I dati di hit vengono forniti in un file `hit_data.tsv`. La quantità di dati in questo file è determinata dal formato di consegna (orario o giornaliero e file singoli o multipli). Questo file contiene solo dati di hit. Le intestazioni di colonna vengono consegnate separatamente con i file di ricerca. Ogni riga di questo file contiene una singola chiamata al server.

I file consegnati da Adobe variano in base al tipo di feed di dati configurato. Tutti i file sono codificati con ISO-8859-1.

* `[rsid]` fa riferimento all&#39;ID suite di rapporti da cui proviene il feed di dati.
* `[index]` viene utilizzato solo in più feed di file e fa riferimento all&#39;ordine corretto dei file impaginati.
* `[YYYY-mm-dd]` si riferisce al giorno iniziale per il quale il feed dati è stato creato.
* `[HHMMSS]` viene utilizzato solo nei feed orari e si riferisce all&#39;ora di inizio del feed dati.
* `[compression_suffix]` fa riferimento al tipo di compressione utilizzato. In genere i feed di dati sono compressi in `tar.gz` o `zip` file.
* `[format_suffix]` fa riferimento al tipo di formato di file. In genere il formato del file del feed dati è `.tsv`.

### Ogni giorno, file singolo

Una volta raccolti i dati per un giorno, si riceverà un singolo file di dati compresso e un file manifesto. Il file di dati è denominato:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Una volta estratto, il file di dati contiene un singolo file `hit_data.tsv` con tutti i dati per quel giorno, nonché i file di ricerca per le colonne richieste.

### Giornaliero, più file

Una volta raccolti i dati per un giorno, si riceveranno uno o più file di dati compressi e un file manifesto. Il file di dati è denominato:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Quando estratti, ogni file di dati contiene un singolo `[index]-[rsid]_[YYYY-mm-dd].[format_suffix]` che contiene circa 2 GB di dati non compressi e i file di ricerca per le colonne richieste.

### Ogni ora, file singolo

Una volta raccolti i dati per un&#39;ora, si riceverà un singolo file di dati compresso e un file manifesto. Il file di dati è denominato:

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

Una volta estratto, il file di dati contiene un singolo file `hit_data.tsv` con tutti i dati per quell&#39;ora, nonché i file di ricerca per le colonne richieste.

### Ogni ora, più file

Una volta raccolti i dati per un&#39;ora, si riceveranno uno o più file di dati compressi e un file manifesto. I file di dati sono denominati:

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix].[compression_suffix]`

Una volta estratto, ogni file di dati contiene un singolo file `[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix]` contenente circa 2 GB di dati non compressi e i file di ricerca per le colonne richieste.

## Dimensione file di dati

La dimensione del file di dati hit varia notevolmente a seconda del numero di variabili utilizzate attivamente e della quantità di traffico inviato alla suite di rapporti. Tuttavia, in media, una riga di dati è di circa 500B (compressi) o 2KB (non compressi). Moltiplicando questo dato per il numero di chiamate al server si può ottenere una stima approssimativa delle dimensioni di un file di feed dati. Una volta che le organizzazioni iniziano a ricevere i file di feed dati, è possibile trovare un numero più preciso dividendo il numero di righe in `hit_data.tsv` per la dimensione totale del file.