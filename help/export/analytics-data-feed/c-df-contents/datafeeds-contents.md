---
description: In questa sezione vengono descritti i file trovati in una consegna di feed di dati.
keywords: Feed dati; processo; contenuti; manifest; file; ricerca; dati hit; contenuto della consegna
seo-description: In questa sezione vengono descritti i file trovati in una consegna di feed di dati.
seo-title: Contenuto feed dati - Panoramica
solution: Analytics
subtopic: feed dati
title: Contenuto feed dati - Panoramica
topic: Reports & Analytics
uuid: 82 a 86314-4841-4133-a 0 dc -4 e 7 c 6 cd 14 fc 1
translation-type: tm+mt
source-git-commit: 7fe23291d8ee9675181065025692108aee3ea9a5

---


# Contenuto feed dati - Panoramica

In questa sezione vengono descritti i file trovati in una consegna di feed di dati.

## Manifest File {#section_044BBDE2906D49518F8264CD4832D429}

Il file manifesto contiene i seguenti dettagli su ciascun file contenuto nel set di dati caricato:

* nome file
* dimensione file
* Hash MD 5
* numero di record contenuti nel file

Il file manifesto segue lo stesso formato di un file manifest Java JAR.

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. I file manifest vengono denominati secondo quanto segue:

```
<report_suite_id>_YYYY_MM_DD.txt
```

Un file manifesto tipico contiene dati simili ai seguenti:

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: bugzilla_2012-09-09-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-bugzilla_2012-09-09.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Ogni file manifesto contiene un'intestazione, che indica il numero totale di file di ricerca, i file di dati e il numero totale di record in tutti i file di dati. Questa intestazione è seguita da più sezioni contenenti informazioni per ogni file incluso nella distribuzione dei feed di dati.

Some feeds are configured to receive a `rsid_YYYY-MM-DD.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## Lookup Files {#section_B5863537A48D47D78D0F7274838923C1}

I file di ricerca non contengono dati di hit, si tratta di file supplementari che forniscono le intestazioni di colonna dei dati hit e dei file di ricerca per tradurre gli ID trovati nel feed di dati in valori effettivi. Ad esempio, il valore "497" nella colonna del browser indica che l'hit proviene da "Microsoft Internet Explorer 8".

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. Other files, such as `browser.tsv`, are generic.

I file di ricerca vengono distribuiti insieme in un file ZIP compresso in base ai seguenti criteri:

```
<report_suite_id>_<YYYY-mm-dd>-<HHMMSS>-lookup_data.<compression_suffix>
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

## Hit Data Files {#section_B0745236104E41F2BA625D24AB442636}

Hit data is provided in a [!DNL hit_data.tsv] file. La quantità di dati in questo file è determinata dal formato di consegna (su base oraria o giornaliera e su più file o più file). Questo file contiene solo dati di hit. Le intestazioni delle colonne vengono distribuite separatamente con i file di ricerca. Ogni riga in questo file contiene una singola chiamata al server.

## Delivery Contents {#section_994B43D1E71A4EFDB2E4183C0929A397}

>[!NOTE]
>
>I file vengono codificati con lo standard ISO -8859-1.

I file effettivi forniti da Adobe variano in base al tipo di feed di dati configurato. Per una descrizione dei file consegnati, individuate la configurazione che corrisponde al feed di dati nella seguente tabella.

L'ora (HHMMSS) indicata in un nome di file indica sempre l'inizio dell'intervallo di date per i dati nel file, indipendentemente da quando è stato prodotto o caricato.

<table id="table_DBF34F39D29D4DA2B2689029CDA24B92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato consegna </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Singolo file giornaliero </td> 
   <td colname="col2"> <p>Dopo la raccolta dei dati per un giorno, riceverai una consegna contenente quanto segue: </p> 
    <ul id="ul_D630D73D0DBA440FA704CF31856243C7"> 
     <li id="li_717873DBBF264422A39217E1A8829742">un singolo file di dati compresso. </li> 
     <li id="li_9F75D42FD56E4CC89C4683D32E59337B">Un file manifesto. </li> 
    </ul> <p>Il file di dati viene distribuito con il seguente nome: </p> 
    <code>&lt; report_ suite &gt;_ &lt; YYYY-mm-dd &gt;.&lt;compression_suffix&gt;
    </code> <p> Where <code> &lt;compression_suffix&gt;</code> is either <code> tar.gz</code> or <code> zip</code>. </p> <p>When extracted, the data file contains a single <span class="filepath"> hit_data.tsv</span> file with all data for that day, as well as the compressed lookup files described above. </p> <p>Le dimensioni del file di dati hit variano notevolmente a seconda del numero di variabili attive attivamente e della quantità di traffico nella suite di rapporti. Tuttavia, in media, una riga di dati è circa 500 B (compressa) o 2 KB (non compressa). Se si moltiplica questo numero in base al numero di chiamate server, è possibile ottenere una stima approssimativa sulla grandezza di un file di feed di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numero giornaliero, più file </td> 
   <td colname="col2"> <p>Dopo la raccolta dei dati per un giorno, riceverai una consegna contenente quanto segue: </p> 
    <ul id="ul_4B873D3F6F18467890C36AE8E86F49DA"> 
     <li id="li_227315384B954A5784FA370D9B30E2AF">Uno o più file di dati compressi, suddivisi in blocchi di 2 GB. </li> 
     <li id="li_4169D889CEA3446CB5FAA08FD60AA0D0">Un file manifesto. </li> 
    </ul> <p>Ogni file di dati viene distribuito con il seguente nome: </p> 
    <code>&lt; index &gt;-&lt; report_ suite &gt;_ &lt; YYYY-mm-dd &gt;.&lt;compression_suffix&gt;
    </code> <p> Where <code> &lt;index&gt;</code> is an incrementing file index from <i>1</i> to <i>n</i>, given <i>n</i> files, and <code> &lt;compression_suffix&gt;</code> is either <code> tar.gz</code> or <code> zip</code>. </p> <p>When extracted, each data file contains a single <span class="filepath"> hit_data.tsv</span> that contains approximately 2 GB of uncompressed data, as well as the compressed lookup files described above. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Un singolo file orario </td> 
   <td colname="col2"> <p>Dopo la raccolta dei dati per un'ora, riceverai una consegna contenente quanto segue: </p> 
    <ul id="ul_29B06981A4F74D2AA1171D733C5FB1F4"> 
     <li id="li_072BBC4BA9B84C61B4E8EFA35F54707B">un singolo file di dati. </li> 
     <li id="li_E2D05E9DAE814309B6BC91798BB29FBB">Un file manifesto. </li> 
    </ul> <p>Il file di dati viene distribuito con il seguente nome: </p> 
    <code>&lt; report_ suite &gt;_ &lt; YYYY-mm-dd &gt;-&lt; HHMMSS &gt;.&lt;compression_suffix&gt;
    </code> <p> Where <code> &lt;compression_suffix&gt;</code> is either <code> tar.gz</code> or <code> zip</code>. </p> <p>When extracted, the data file contains a single <span class="filepath"> hit_data.tsv</span> file with all data for that hour. I file di ricerca compressi descritti sopra vengono distribuiti solo con i dati per la prima ora di ogni giorno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Orario, più file </td> 
   <td colname="col2"> <p>Dopo la raccolta dei dati per un'ora, riceverai una consegna contenente quanto segue: </p> 
    <ul id="ul_A739BA12B66547A28BA45E0B9B747B16"> 
     <li id="li_C0DF059D1E6843C8A38E24CA1B59D99C">Uno o più file di dati compressi, suddivisi in blocchi di 2 GB. </li> 
     <li id="li_604266DA9B8A4000905C44C95DA65D14">Un file manifesto. </li> 
    </ul> <p>Ogni file di dati viene distribuito con il seguente nome: </p> 
    <code>&lt; index &gt;-&lt; report_ suite &gt;_ &lt; AAAA-mm-dd &gt;-&lt; HHMMSS &gt;. tsv.&lt;compression_suffix&gt;
    </code> <p>Where <code> &lt;index&gt;</code> is an incrementing file index from <i>1</i> to <i>n</i>, given <i>n</i> files, and <code> &lt;compression_suffix&gt;</code> is either <code> gz</code> or <code> zip</code> </p> <p>When extracted, each data file contains a single <span class="filepath"> hit_data.tsv</span> that contains approximately 2 GB of uncompressed data. I file di ricerca compressi descritti sopra vengono distribuiti solo con i dati per la prima ora di ogni giorno. </p> </td> 
  </tr> 
 </tbody> 
</table>

