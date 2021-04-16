---
description: Questa sezione descrive i file trovati in una consegna feed di dati.
keywords: Feed di dati;processo;contenuto;manifesto;file;ricerca;dati di hit;contenuto della consegna
subtopic: data feeds
title: 'Contenuti feed dati: panoramica'
feature: Nozioni di base su Reports & Analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# Contenuti feed dati: panoramica

Questa sezione descrive i file trovati in una consegna feed di dati.

## File manifesto

Il file manifesto contiene i seguenti dettagli su ogni file che fa parte del set di dati caricati:

* Nome file
* Dimensione file
* hash MD5
* Numero di record contenuti nel file

Il file manifesto segue lo stesso formato di un file manifesto Java JAR.

Il file manifesto viene sempre consegnato per ultimo come file `.txt` separato, in modo che la sua esistenza indichi che il set di dati completo per quel periodo di richiesta è già stato consegnato. I file manifest sono denominati in base ai seguenti elementi:

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

Ogni file manifest contiene un&#39;intestazione che indica il numero totale di file di ricerca, file di dati e il numero totale di record in tutti i file di dati. A questa intestazione seguono più sezioni contenenti informazioni per ciascun file incluso nella consegna del feed di dati.

Alcuni feed sono configurati per ricevere un file `.fin` invece di un manifesto `.txt`. Il `.fin` indica che il caricamento è completo, ma non contiene metadati sul caricamento.

## File di ricerca

Alcune colonne di feed dati producono un numero che corrisponde al valore effettivo. I file di ricerca vengono utilizzati per associare un numero di una colonna di feed di dati e per farlo corrispondere a un valore effettivo. Ad esempio, un valore di &quot;497&quot; nella colonna dei dati di hit `browser` indica che l’hit proviene da &quot;Microsoft Internet Explorer 8&quot; se si cerca in `browser.tsv`.

Tieni presente che le `column_headers.tsv` e `event_list.tsv` sono specifiche per il feed di dati e la suite di rapporti. Altri file, come `browser.tsv`, sono generici.

I file di ricerca vengono consegnati insieme in un file ZIP compresso denominato in base ai seguenti elementi:

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

## File di dati di hit

I dati degli hit vengono forniti in un file [!DNL hit_data.tsv]. La quantità di dati in questo file è determinata dal formato di consegna (ogni ora o giorno, e da uno o più file). Questo file contiene solo dati di hit. Le intestazioni di colonna vengono distribuite separatamente con i file di ricerca. Ogni riga in questo file contiene una singola chiamata al server.

I file inviati da Adobe variano a seconda del tipo di feed di dati configurato. Tutti i file vengono codificati mediante lo standard ISO-8859-1.

* `[rsid]` fa riferimento all’ID suite di rapporti da cui proviene il feed di dati.
* `[index]` viene utilizzato solo in più feed di file e fa riferimento all’ordine corretto dei file impaginati.
* `[YYYY-mm-dd]` si riferisce al giorno iniziale per il quale viene eseguito il feed di dati.
* `[HHMMSS]` viene utilizzato solo nei feed orari e si riferisce all’ora di inizio per la quale è destinato il feed di dati.
* `[compression_suffix]` si riferisce al tipo di compressione utilizzato. In genere i feed di dati vengono compressi in file `tar.gz` o `zip`.

### File singolo giornaliero

Una volta raccolti i dati per un giorno, riceverai un singolo file di dati compressi e un file manifesto. Il file di dati è denominato:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Una volta estratto, il file di dati contiene un singolo file `hit_data.tsv` con tutti i dati per quel giorno, nonché file di ricerca per eventuali colonne richieste.

### File giornalieri, più file

Dopo la raccolta dei dati per un giorno, si ricevono uno o più file di dati compressi e un file manifesto. Il file di dati è denominato:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Quando viene estratto, ogni file di dati contiene un singolo `hit_data.tsv` che contiene circa 2 GB di dati non compressi, nonché file di ricerca per eventuali colonne richieste.

### File singolo orario

Dopo aver raccolto i dati per un&#39;ora, si riceve un singolo file di dati compressi e un file manifesto. Il file di dati è denominato:

`[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

Quando viene estratto, il file di dati contiene un singolo file `hit_data.tsv` con tutti i dati per quell’ora, nonché file di ricerca per eventuali colonne richieste.

### File multipli orari

Dopo aver raccolto i dati per un&#39;ora, si ricevono uno o più file di dati compressi e un file manifesto. Il file di dati è denominato:

`[index]-[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

Quando viene estratto, ogni file di dati contiene un singolo `hit_data.tsv` che contiene circa 2 GB di dati non compressi, nonché file di ricerca per eventuali colonne richieste.

## Dimensioni del file di dati

La dimensione del file di dati di hit varia notevolmente a seconda del numero di variabili utilizzate attivamente e della quantità di traffico inviato alla suite di rapporti. Tuttavia, in media, una riga di dati è di circa 500B (compressi) o 2 KB (non compressi). La moltiplicazione per il numero di chiamate al server può fornire una stima approssimativa della dimensione di un file di feed di dati. Una volta che le organizzazioni iniziano a ricevere i file di feed di dati, puoi trovare un numero più preciso dividendo il numero di righe in `hit_data.tsv` per la dimensione totale del file.
