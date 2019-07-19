---
description: L'importazione consente di caricare in massa i dati classificazioni in un file di analisi. L'importazione richiede un formato di file specifico per il corretto caricamento dei dati.
seo-description: L'importazione consente di caricare in massa i dati classificazioni in un file di analisi. L'importazione richiede un formato di file specifico per il corretto caricamento dei dati.
seo-title: File di dati classificazione
solution: Analytics
subtopic: Classificazioni
title: File di dati classificazione
topic: Strumenti di amministrazione
uuid: f 27 bb 812-56 e 0-472 a -9993-d 869 f 0 fea 700
translation-type: tm+mt
source-git-commit: c0c4a3f42a7236c6f9e5001f5ca0ef9173dbaa66

---


# File di dati classificazione

L'importazione consente di caricare in massa i dati classificazioni in un file di analisi. L'importazione richiede un formato di file specifico per il corretto caricamento dei dati.

Per creare file di dati validi, puoi scaricare un file modello che fornisce una struttura file in cui puoi incollare i dati di classificazione. For more information, see [Download Classifications Template](../../../components/c-classifications2/c-classifications-importer/c-download-saint-data.md#concept_0F06847AD8D042F5BA818AE3C37E2417).

See [General File Structure](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9EFF968DF5D244A887DE94075431C1BE) for more information about character limits in classifications.

See [Numeric 2 Classifications](../../../components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md#concept_71024B7B91DF4E909076062AB1380D8B) for information about uploading data using numeric 2 classifications.

## Struttura file generale

L'illustrazione seguente è un file di dati di esempio:

![](assets/completed-saint-file.png)

Un file di dati deve aderire alle seguenti regole struttura:

* Le classificazioni non possono avere un valore pari a 0 (zero).
* Adobe consiglia di limitare il numero di colonne di importazione ed esportazione a 30.
* I file caricati devono utilizzare UTF -8 senza codifica dei caratteri BOM.
* Special characters, such as a tabs, newlines, and quotes can be embedded within a cell provided the v2.1 file format is specified and the cell is properly [escaped](../../../components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md#task_EB47E80063F14F9CB2D186C0CAA9CBAD). I caratteri speciali includono:

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   La virgola non è un carattere speciale.

* Le classificazioni non possono contenere un accento circonflesso (^) poiché questo carattere è utilizzato per indicare una classificazione secondaria.
* Utilizzate l'assistenza quando utilizzate un trattino. For example, if you use a hyphen (-) in a Social term, Social recognizes the hyphen as a [!DNL Not] operator (the minus sign). For example, if you specify *`fragrance-free`* as a term using the import, Social recognizes the term as fragrance *`minus`* free and collects posts that mention *`fragrance`*, but not *`free`*.
* I limiti dei caratteri vengono applicati per classificare i dati del rapporto. For example, if you upload a classifications text file for products ( *`s.products`*) with product names longer than 100 characters (bytes), the products will not display in reporting. I codici di tracciamento e tutte le variabili di conversione personalizzate (evar) consentono 255 byte.
* File di dati delimitato da tabulazioni (create il file del modello utilizzando un'applicazione di fogli di calcolo o un editor di testo).
* Either a [!DNL .tab] or [!DNL .txt] file extension.
* Un cancelletto (#) identifica la riga come commento utente. Adobe ignora qualsiasi linea che inizi con #.
* Un segno doppio cancelletto seguito da SC (# # SC) identifica la riga come commento dell'intestazione pre-elaborazione utilizzata dai rapporti. Non eliminare queste righe.
* Le esportazioni di classificazione possono avere chiavi duplicate a causa di caratteri newline nella chiave. In un'esportazione FTP o browser, questa soluzione può essere risolta attivando la citazione per l'account FTP. In questo modo si inseriscono preventivi intorno a ogni chiave con caratteri newline.
* La Cella C 1 nella prima riga del file di importazione contiene un identificatore versione che determina il modo in cui le classificazioni possono essere utilizzate per tutto il resto del file.

   * v 2.0 ignora le virgolette e presuppone che facciano parte delle chiavi e dei valori specificati. Ad esempio, considerate questo valore: " Questo è "some value". v 2.0 la interpreterebbe letteralmente come: " Questo è "some value".
   * La release v 2.1 indica che le virgolette fanno parte della formattazione dei file utilizzata nei file Excel. Quindi, la versione v 2.1 formatta l'esempio precedente per: Questo è "some value".
   * Possono verificarsi problemi quando la release v 2.1 è specificata nel file, ma ciò che effettivamente è desiderato è v 2.0, vale a dire quando le virgolette vengono utilizzate in modalità non consentite nella formattazione Excel. Ad esempio, se hai un valore: " VP NO REPS "S/l Dress w/Overlay. Con la release v 2.1, questa formattazione non è corretta (il valore deve essere racchiuso da virgolette di apertura e di chiusura, e le virgolette che fanno parte del valore effettivo devono essere precedute da virgolette) e le classificazioni non funzioneranno più.
   * Accertatevi di effettuare una delle seguenti operazioni: modificate il formato di file in v 2.0 modificando l'intestazione (cella C 1) nei file caricati, oppure implementate correttamente Excel in tutti i file.

* La prima riga (non commento) del file di dati contiene le intestazioni di colonna utilizzate per identificare i dati di classificazione nella colonna. L'importazione richiede un formato specifico per le intestazioni delle colonne. For more information, see [Column Heading Format](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_ADC08C783477451B959782CEA23AF5EF).
* Immediatamente dopo la riga di intestazione in un file di dati sono presenti le righe dati. Ogni riga di dati deve contenere un campo dati per ogni intestazione di colonna.
* Il file di dati supporta i seguenti codici di controllo, utilizzati da Adobe per fornire struttura al file e importare correttamente i dati di classificazione:

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CODICE DI CONTROLLO </th> 
   <th colname="col2" class="entry"> DESCRIPTION </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;Nuovo grafico a linee&gt; </p> </td> 
   <td colname="col2"> <p>Un nuovo carattere di riga è l'unico delimitatore supportato tra le righe dati/record nel file di dati. In genere, durante la scrittura di un programma è necessario inserire solo questi caratteri per generare automaticamente i file di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~ autogen ~ </p> </td> 
   <td colname="col2"> <p>Richiede che Adobe generi automaticamente un ID univoco per questo elemento. </p> <p>Nel contesto della campagna, questo valore di controllo indica ad Adobe di assegnare un identificatore a ciascun elemento creativo. See <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_0B77B3079B5C414F9956058688990443" format="dita" scope="local"> Key </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~ period ~ </p> </td> 
   <td colname="col2"> <p>Indica che la colonna dati rappresenta l'intervallo di date associato all'elemento. See <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9ECCD5ED97764CDC90C0B7B0F9461825" format="dita" scope="local"> Date </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campo vuoto </p> </td> 
   <td colname="col2"> <p>Rappresenta un valore NULL per il campo corrente. Utilizzate questa opzione se non si applica una particolare colonna di dati al record corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PER modificatori </p> </td> 
   <td colname="col2"> <p>Designates that the data column represents a <span class="wintitle"> PER Modifier </span> field. See <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_7E199A26E3274B31B07CCAF8DFE3B274" format="dita" scope="local"> PER Modifier Headings </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Problemi comuni di caricamento](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)


## Formato intestazione colonna

>[!NOTE]
>
>Adobe consiglia di limitare il numero di colonne di importazione ed esportazione a 30.

I file di classificazione supportano le seguenti intestazioni di colonna:

### Chiave

Ogni valore deve essere univoco nell'intero sistema. The value in this field corresponds to a value assigned to the [!DNL Analytics] variable in your Web site’s [!DNL JavaScript] beacon. Data in this column might include ~autogen~ or any other unique tracking code.

### Intestazione della colonna classificazione

For example, reports and analytics automatically include two classifications for [!UICONTROL Campaign] variables: [!UICONTROL Campaigns] and [!UICONTROL Creative Elements]. To add data to the [!UICONTROL Campaigns] classification, the column heading in the classification data file would be [!UICONTROL Campaigns].

>[!NOTE]
>
>The values in the [!UICONTROL Classifications] column heading must exactly match the classification’s naming convention, or the import fails. For example, if the administrator changes [!UICONTROL Campaigns] to [!UICONTROL Internal Campaign Names] in the [!UICONTROL Campaign Set-up Manager], the file column heading must change to match.

Inoltre, il file di dati supporta le seguenti convenzioni di intestazione aggiuntive per identificare le sottoclassi e altre colonne di dati specializzate:

### Intestazione di classificazione secondaria

For example, [!UICONTROL Campaigns^Owner] is a column heading for the column containing [!UICONTROL Campaign Owner] values. Similarly, [!UICONTROL Creative Elements^Size] is a column heading for the column containing the [!UICONTROL Size] sub-classification of the [!UICONTROL Creative Elements] classification.

### Titoli delle metriche di classificazione

For example, [!UICONTROL Campaigns^~Cost] refers to the [!UICONTROL Cost] metric in the [!UICONTROL Campaigns] classification.

### Intestazione per modificatore

*`Per Modifier`* sono denotate aggiungendo *`~per`* all'intestazione della metrica classificazione. For example, if the *`Metric`* heading is *`Campaigns^~Cost`*, the PER modifier heading is *`Campaigns^~Cost~per`*. Adobe supports the following *`PER Modifier`* keywords:

Questi caratteri hanno un significato speciale in un file di dati. Se possibile, evitate di usare queste parole nei nomi e nei dati degli attributi.

**PROBLEMA corretto:** Valore fisso. Non eseguire alcun ridimensionamento.

**GIORNO:** Moltiplica il valore per il numero di giorni nel report.

**ORDER:** Moltiplica il valore per il numero di ordini per l'elemento della riga nel report.

**CHECKOUT:** Moltiplica il valore per il numero di checkout per l'elemento della riga nel report.

**UNIT:** Moltiplica il valore per il numero di unità per l'elemento della riga nel rapporto.

**ENTRATE:** Moltiplica il valore per l'importo delle entrate per l'elemento della riga nel report.

**Scadenza:** Moltiplica il valore per il numero di volte in cui l' [!UICONTROL Shopping Cart Add] evento è stato chiamato per elemento riga nel report.

**SCREMOVE:** Moltiplica il valore per il numero di volte in cui l' [!UICONTROL Shopping Cart Remove] evento è stato chiamato per elemento riga nel report.

**INSTANCE:** Moltiplica il valore per il numero di istanze per l'elemento della riga nel report.

**CLICK:** Moltiplica il valore per il numero di clic per l'elemento linea nel report.

**EVENT:** Moltiplica il valore per il numero di volte in cui l'evento personalizzato specificato si è verificato per elemento riga del report.

**Esempio:** Se Campaign A costa $ 10,000, la [!UICONTROL Campaigns^~Cost] colonna contiene un valore pari a 10000 e la [!UICONTROL Campaigns^~colonna Costper~] contiene [!UICONTROL FIXED]. Quando si visualizza il costo per Campaign A nei report, visualizzerete $ 10,000 come costo fisso per Campaign A per l'intervallo date.

**Esempio:** Se la campagna B costa circa $ 2 per click, la [!UICONTROL Campaigns^~Cost] colonna contiene 2 e la colonna **[!UICONTROL Campaigns^~Costper~]** contiene [!UICONTROL CLICK]. When displaying the Cost for Campaign B in the reports, Adobe calculates (2 * [number of clicks]) on the fly for the date range of the report. Questo fornisce un calcolo costi totale in base al numero di clic eseguiti con Campaign B.

### Data

Le date delle campagne sono in genere intervalli (date di inizio e di fine) associate a singole campagne. Le date devono essere visualizzate nel formato AAAA/MM/DD. Ad esempio, 2013/06/15-2013/06/30.

For more information, see [Conversion Classifications](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications).

>[!NOTE]
>
>In the May 10, 2018, [!DNL Analytics] Maintenance release, Adobe started to limit the functionality of date-enabled and numeric classifications. Questi tipi di classificazione sono stati rimossi dalle interfacce Admin (Amministratore) e Classification Importer (Importazione classificazione). Non è possibile aggiungere nuove classificazioni numeriche e abilitate per le date. Sarà comunque possibile gestire le classificazioni esistenti, aggiornandole o eliminandole tramite il flusso di lavoro di classificazione standard, e continuare a utilizzarle nei rapporti.

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL Classifications] può essere utilizzato per assegnare intervalli di date alle campagne o ad altre conversione [!UICONTROL classifications], per una misurazione più accurata delle campagne. Dopo aver specificato l'intervallo di date di un valore, qualsiasi valore corrispondente che si verifica al di fuori dell'intervallo di date non verrà classificato. Questo è utile per la misurazione delle campagne che desiderano utilizzare le date esatte in cui una campagna è Live, e non tutti gli hit corrispondenti alla campagna stessa. Per classificare correttamente un valore con un intervallo di date, è necessario soddisfare quanto segue:

* The [!UICONTROL classification] must be based on a conversion variable.
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* L'intervallo di date coinvolto deve contenere una data di inizio e, facoltativamente, una data di fine.

Per classificare le campagne in base all'intervallo di date:

1. Log in to [!DNL Analytics] and go to Admin &gt; Classifications.
1. Click the **[!UICONTROL Browser Export]** tab, ensure the settings to your date-enabled classification are correct, then click Export File.
1. Aprire questo file in Microsoft Excel o in un altro editor di fogli di calcolo.
1. Una delle colonne terminerà con

   ^~period~
which is the column to enter the date range in.
1. Sotto questa colonna, immetti l'intervallo di date di ciascun valore nel seguente formato:

   `YYYY/MM/DD - YYYY/MM/DD`. Verificate quanto segue:

   * Lasciare spazi su entrambi i lati del trattino.
   * Usate un trattino (-) per separare gli intervalli, non un trattino o un trattino.
   * Se il mese o il giorno è una cifra singola, è presente uno zero iniziale.
   * È presente un intervallo di date iniziale; l'intervallo di date finale è facoltativo.

1. Save the file, and upload it to [!DNL Analytics] by going to Admin | Classifications | Import File.

>[!NOTE]
>
>Un valore chiave specifico non può avere più di un intervallo di date.

## Classificazione delle classificazioni

* [Problemi comuni di caricamento](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html): Articolo della Knowledge Base che descrive i problemi derivanti da formati di file e contenuti del file errati.

