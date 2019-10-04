---
description: In questa sezione vengono descritti i file trovati in una distribuzione di feed di dati.
keywords: Feed dati;job;contents;manifest;file;search;hit data;delivery contents;contents;contents;contents;contents;contents;manifest;file;search;hit data;delivery contents;delivery contents
seo-description: In questa sezione vengono descritti i file trovati in una distribuzione di feed di dati.
seo-title: 'Contenuti feed dati: panoramica'
solution: Analytics
subtopic: feed di dati
title: 'Contenuti feed dati: panoramica'
topic: Reports and Analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
translation-type: tm+mt
source-git-commit: 4ce92a400c6590ce7c891155f404b64f0808bcb8

---


# Contenuti feed dati: panoramica

In questa sezione vengono descritti i file trovati in una distribuzione di feed di dati.

## File manifesto

Il file manifesto contiene i seguenti dettagli su ciascun file che fa parte del set di dati caricato:

* Nome file
* Dimensione file
* hash MD5
* Numero di record contenuti nel file

Il file manifesto segue lo stesso formato di un file manifesto Java JAR.

Il file manifesto viene sempre consegnato per ultimo come `.txt` file separato, in modo che la sua esistenza indichi che il set di dati completo per quel periodo di richiesta è già stato consegnato. I file manifesto vengono denominati in base alle seguenti impostazioni:

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

Ogni file manifesto contiene un'intestazione che indica il numero totale di file di ricerca, file di dati e il numero totale di record in tutti i file di dati. Questa intestazione è seguita da più sezioni contenenti informazioni per ciascun file incluso nella distribuzione dei feed di dati.

Alcuni feed sono configurati per ricevere un `.fin` file invece di un `.txt` manifesto. Indica `.fin` che il caricamento è completo, ma non contiene metadati relativi al caricamento.

## Ricerca di file

Alcune colonne di feed di dati restituiscono un numero corrispondente al valore effettivo. I file di ricerca vengono utilizzati per far corrispondere un numero da una colonna feed di dati e per adattarlo a un valore effettivo. Ad esempio, un valore pari a "497" nella colonna dei dati di `browser` hit indica che l’hit proviene da "Microsoft Internet Explorer 8" se si cerca in `browser.tsv`.

Tieni presente che `column_headers.tsv` e `event_list.tsv` sono specifici per il feed di dati e la suite di rapporti. Altri file, come `browser.tsv`, sono generici.

I file di ricerca vengono inviati insieme in un file ZIP compresso con il seguente nome:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* [!DNL column_headers.tsv] (personalizzato per questo feed di dati)
* [!DNL browser.tsv]
* [!DNL browser_type.tsv]
* [!DNL color_depth.tsv]
* [!DNL connection_type.tsv]
* [!DNL country.tsv]
* [!DNL javascript_version.tsv]
* [!DNL languages.tsv]
* [!DNL operating_systems.tsv]
* [!DNL plugins.tsv]
* [!DNL resolution.tsv]
* [!DNL referrer_type.tsv]
* [!DNL search_engines.tsv]
* [!DNL event_lookup.tsv] (personalizzato per questo feed di dati)

## Hit data files

I dati degli hit vengono forniti in un [!DNL hit_data.tsv] file. La quantità di dati in questo file è determinata dal formato di consegna (ogni ora o giorno, e da uno o più file). Questo file contiene solo i dati hit. Le intestazioni delle colonne vengono distribuite separatamente con i file di ricerca. Ogni riga in questo file contiene una singola chiamata server.

I file inviati da Adobe variano in base al tipo di feed di dati configurato. Tutti i file vengono codificati tramite lo standard ISO-8859-1.

* `[rsid]` si riferisce all'ID suite di rapporti da cui proviene il feed di dati.
* `[index]` viene utilizzato solo in più feed di file e fa riferimento all'ordine corretto dei file impaginati.
* `[YYYY-mm-dd]` si riferisce al giorno iniziale per il quale è destinato il feed di dati.
* `[HHMMSS]` viene utilizzato solo nei feed orari e fa riferimento all'ora di inizio per la quale è destinato il feed di dati.
* `[compression_suffix]` si riferisce al tipo di compressione utilizzato. In genere i feed di dati vengono compressi in `tar.gz` o `zip` file.

### Giorno, file singolo

Una volta raccolti i dati per un giorno, riceverete un singolo file di dati compresso e un file manifesto. Il file di dati è denominato:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Quando estratto, il file di dati contiene un singolo `hit_data.tsv` file con tutti i dati per quel giorno, così come i file di ricerca per qualsiasi colonna richiesta.

### Giornaliero, più file

Una volta raccolti i dati per un giorno, riceverete uno o più file di dati compressi e un file manifesto. Il file di dati è denominato:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Quando estratto, ogni file di dati contiene un singolo `hit_data.tsv` che contiene circa 2 GB di dati non compressi, nonché file di ricerca per qualsiasi colonna richiesta.

### File singolo ogni ora

Una volta raccolti i dati per un'ora, riceverete un singolo file di dati compresso e un file manifesto. Il file di dati è denominato:

`[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

Se estratto, il file di dati contiene un singolo `hit_data.tsv` file con tutti i dati per quell'ora, nonché file di ricerca per le colonne richieste.

### Ogni ora, più file

Una volta raccolti i dati per un'ora, riceverete uno o più file di dati compressi e un file manifesto. Il file di dati è denominato:

`[index]-[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

Quando estratto, ogni file di dati contiene un singolo `hit_data.tsv` che contiene circa 2 GB di dati non compressi, nonché file di ricerca per qualsiasi colonna richiesta.

## Dimensioni del file di dati

La dimensione del file di dati di hit varia notevolmente a seconda del numero di variabili utilizzate attivamente e della quantità di traffico inviata alla suite di rapporti. Tuttavia, in media, una riga di dati è di circa 500 B (compressi) o 2 KB (non compressi). Moltiplicando questo dato per il numero di chiamate al server è possibile ottenere una stima approssimativa delle dimensioni di un file di feed di dati. Dopo che le organizzazioni hanno iniziato a ricevere i file di feed di dati, è possibile ottenere un numero più preciso dividendo il numero di righe in `hit_data.tsv` base alla dimensione totale del file.
