---
description: Questa sezione descrive i file trovati in una consegna di feed dati.
keywords: Feed dati;processo;contenuto;manifesto;file;ricerca;hit;contenuti consegna
subtopic: data feeds
title: 'Contenuti feed dati: panoramica'
feature: Data Feeds
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
source-git-commit: 43e483f157f1c2527f671eb43a165db86c77a7ce
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 4%

---

# Contenuti feed dati: panoramica

Le sezioni seguenti descrivono come accedere e comprendere i file presenti in una consegna di feed di dati.

## Accedere al contenuto del feed dati

Per accedere al contenuto di un feed dati:

1. Accedi al sito di destinazione del feed di dati.

   Questo è il sito di destinazione configurato durante la creazione del feed di dati, ad esempio un bucket Amazon S3 o Google Cloud Platform.

1. Scarica il file del feed dati compresso sul computer locale.

1. Decomprimi il file compresso utilizzando un programma che supporta le estensioni di file `.tar.gz`.

1. Apri il file `hit_data.tsv` nell’applicazione per fogli di calcolo o database scelta per visualizzare i dati non elaborati per quel giorno. -->

## File manifesto {#feed-manifest}

Il file manifesto contiene i seguenti dettagli su ciascun file che fa parte del set di dati caricato:

* Nome file
* Dimensione file
* Hash MD5
* Numero di record contenuti nel file

Il file manifest ha lo stesso formato di un file manifest Java JAR.

Il file manifesto viene sempre recapitato per ultimo come file separato `.txt` in modo che la sua esistenza indichi che il set di dati completo per tale periodo di richiesta è già stato consegnato. I file manifesto sono denominati in base a quanto segue:

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

Alcuni feed sono configurati per ricevere un `.fin` anziché un file `.txt` manifesto. Il `.fin` indica che il caricamento è completo, ma non contiene metadati sul caricamento.

## Ricercare file

Alcune colonne di feed dati restituiscono un numero che corrisponde al valore effettivo. I file di ricerca vengono utilizzati per far corrispondere un numero di una colonna di feed dati con un valore effettivo. Ad esempio, un valore di &quot;497&quot; nel campo `browser` la colonna dei dati di hit indica che l’hit proviene da &quot;Microsoft Internet Explorer 8&quot; se si cerca in `browser.tsv`.

Tieni presente che `column_headers.tsv` e `event_list.tsv` sono specifiche per il feed di dati e la suite di rapporti. Altri file, ad esempio `browser.tsv`, sono generici.

I file di ricerca vengono consegnati insieme in un file ZIP compresso denominato in base ai seguenti elementi:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* **`column_headers.tsv`**: una singola riga contenente le intestazioni di colonna per `hit_data.tsv`.
* **`browser.tsv`**: mappa l’ID del browser (il `browser` feed) al nome descrittivo del browser.
* **`browser_type.tsv`**: mappa l’ID del browser (il `browser` feed) al tipo di browser.
* **`color_depth.tsv`**: esegue la mappatura dell’ID di profondità del colore (il `color` colonna feed) alla profondità del colore.
* **`connection_type.tsv`**: esegue il mapping dell’ID del tipo di connessione (il `connection_type` feed) al tipo di connessione.
* **`country.tsv`**: esegue la mappatura dell’ID paese (il `country` feed) al nome del paese.
* **`javascript_version.tsv`**: esegue il mapping dell’ID versione JavaScript (il `javascript` feed) alla versione JavaScript.
* **`languages.tsv`**: esegue la mappatura dell’ID lingua (il `language` colonna feed) alla lingua.
* **`operating_systems.tsv`**: esegue il mapping dell’ID del sistema operativo (il `os` feed) al nome del sistema operativo.
* **`plugins.tsv`**: esegue la mappatura dell’ID del plug-in (il `plugin` colonna feed) a ciascun nome del rispettivo plug-in.
* **`resolution.tsv`**: esegue la mappatura dell’ID risoluzione (il `resolution` feed) alla risoluzione del monitor.
* **`referrer_type.tsv`**: esegue la mappatura dell’ID del tipo di referente (il `ref_type` feed) al tipo di referente.
* **`search_engines.tsv`**: mappa l’ID del motore di ricerca (il `search_engine` feed) al nome del motore di ricerca.
* **`event.tsv`**: esegue la mappatura di ogni ID evento (il `event_list` feed) al rispettivo nome evento.

## File di dati di hit

I dati di hit vengono forniti in una `hit_data.tsv` file. La quantità di dati in questo file è determinata dal formato di consegna (orario o giornaliero e file singoli o multipli). Questo file contiene solo dati di hit. Le intestazioni di colonna vengono consegnate separatamente con i file di ricerca. Ogni riga di questo file contiene una singola chiamata al server.

I file consegnati da Adobe variano in base al tipo di feed di dati configurato. Tutti i file sono codificati con ISO-8859-1.

* `[rsid]` fa riferimento all’ID suite di rapporti da cui proviene il feed di dati.
* `[index]` viene utilizzato solo in più feed di file e fa riferimento all’ordine corretto dei file impaginati.
* `[YYYY-mm-dd]` si riferisce al giorno di inizio previsto per il feed di dati.
* `[HHMMSS]` viene utilizzato solo nei feed orari e si riferisce all’ora di inizio prevista del feed di dati.
* `[compression_suffix]` fa riferimento al tipo di compressione utilizzato. In genere, i feed di dati vengono compressi in `tar.gz` o `zip` file.

### Ogni giorno, file singolo

Una volta raccolti i dati per un giorno, si riceverà un singolo file di dati compresso e un file manifesto. Il file di dati è denominato:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Quando viene estratto, il file di dati contiene un singolo `hit_data.tsv` con tutti i dati per quel giorno, nonché i file di ricerca per le colonne richieste.

### Giornaliero, più file

Una volta raccolti i dati per un giorno, si riceveranno uno o più file di dati compressi e un file manifesto. Il file di dati è denominato:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Quando estratti, ogni file di dati contiene un singolo `hit_data.tsv` che contiene circa 2 GB di dati non compressi e file di ricerca per le colonne richieste.

### Ogni ora, file singolo

Una volta raccolti i dati per un&#39;ora, si riceverà un singolo file di dati compresso e un file manifesto. Il file di dati è denominato:

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

Quando viene estratto, il file di dati contiene un singolo `hit_data.tsv` con tutti i dati per quell’ora, nonché i file di ricerca per le colonne richieste.

### Ogni ora, più file

Una volta raccolti i dati per un&#39;ora, si riceveranno uno o più file di dati compressi e un file manifesto. Il file di dati è denominato:

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

Quando estratti, ogni file di dati contiene un singolo `hit_data.tsv` che contiene circa 2 GB di dati non compressi e file di ricerca per le colonne richieste.

## Dimensione file di dati

La dimensione del file di dati hit varia notevolmente a seconda del numero di variabili utilizzate attivamente e della quantità di traffico inviato alla suite di rapporti. Tuttavia, in media, una riga di dati è di circa 500B (compressi) o 2KB (non compressi). Moltiplicando questo dato per il numero di chiamate al server si può ottenere una stima approssimativa delle dimensioni di un file di feed dati. Una volta che le organizzazioni iniziano a ricevere i file di feed dati, puoi trovare un numero più preciso dividendo il numero di righe in `hit_data.tsv` in base alla dimensione totale del file.