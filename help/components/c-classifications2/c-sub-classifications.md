---
description: Adobe Analytics supporta modelli di classificazioni a livello singolo e a livello multiplo. Una gerarchia di classificazione consente di applicare una classificazione a una classificazione.
seo-description: Adobe Analytics supporta modelli di classificazioni a livello singolo e a livello multiplo. Una gerarchia di classificazione consente di applicare una classificazione a una classificazione.
seo-title: Informazioni sulle classificazioni secondarie
solution: Analytics
subtopic: Classificazioni
title: Informazioni sulle classificazioni secondarie
topic: Strumenti di amministrazione
uuid: 48 bd 7 fc 1-54 a 1-40 ef-bc 55-395338522 f 2 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Informazioni sulle classificazioni secondarie

Adobe Analytics supporta modelli di classificazioni a livello singolo e a livello multiplo. Una gerarchia di classificazione consente di applicare una classificazione a una classificazione.

>[!NOTE]
>
>La classificazione secondaria fa riferimento alla capacità di creare classificazioni di classificazioni. However, this is not the same as a [!UICONTROL Classification Hierarchy] used to create [!UICONTROL Hierarchy] reports. For more information about Classification hierarchies, see [Classification Hierarchies](classification-hierarchies.md).

<!-- 

<p>Removed sub-classifications in rule builder. Preserve subclass files in project for future reference. </p>

 -->

<!-- 

c_single-level_classifications.xml

 -->

Ad esempio:

![](assets/single-level-popup-C.png)

Ogni classificazione in questo modello è indipendente e corrisponde a un nuovo sottorapporto per la variabile di reporting selezionata. Inoltre, ogni classificazione rappresenta una colonna dati nel file di dati, con il nome della classificazione come intestazione della colonna. Ad esempio:

| KEY | PROPERTY 1 | PROPERTY 2 |
|---|---|---|
| 123 | ABC | A12B |
| 456 | DEF | C3D4 |

For more information about the data file, see [Classification Data Files](../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_EBA7669C546040BE8162ADACA3548735).

<!-- 

c_multiple-level_classifications.xml

 -->

Le classificazioni a livello multiplo sono costituite da classificazioni principali e secondarie. Ad esempio:

![](assets/Multi-Level-Class-popup.png)

**Classificazioni principali:** Una classificazione principale è una classificazione con classificazione figlia associata. Una classificazione può essere una classificazione principale e secondaria. The top-level parent classifications correspond to single-level classifications (See [Single-Level Classifications](../../components/c-classifications2/c-sub-classifications.md#concept_6B909B54221F4A9BAEA8E30594F06C49)).

**Classificazioni secondarie:** Una classificazione secondaria è una classificazione con un'altra classificazione come elemento padre anziché variabile. Le classificazioni secondarie forniscono informazioni aggiuntive sulla classificazione padre. For example, a [!UICONTROL Campaigns] classification might have a Campaign Owner child classification. [!UICONTROL Numeric] Le classificazioni funzionano anche come metriche nei report di classificazione.

Ogni classificazione, principale o figlio, costituisce una colonna di dati nel file di dati. L'intestazione della colonna di una classificazione secondaria utilizzando il seguente formato di denominazione:

`<parent_name>^<child_name>`

For more information about the data file format, see [Classification Data Files](../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_EBA7669C546040BE8162ADACA3548735).

Ad esempio:

| KEY | PROPERTY 1 | Proprietà 1 &amp; amp; Cappello; Proprietà 1-1 | Proprietà 1 &amp; amp; Cappello; Proprietà 1-2 | Proprietà 2 |
|---|---|---|---|---|
| 123 | ABC | Verde | Piccolo | A12B |
| 456 | DEF | Rosso | Grande | C3D4 |

Anche se il modello di file per una classificazione multievel è più complesso, l'efficacia delle classificazioni a più livelli è che i livelli separati possono essere caricati come file separati. Questo approccio può essere utilizzato per ridurre al minimo la quantità di dati che devono essere caricati periodicamente (giornalieri, settimanali e così via) raggruppando dati in livelli di classificazione che cambiano nel tempo e che non vengono modificati.

>[!NOTE]
>
>If the [!UICONTROL Key] column in a data file is blank, Adobe automatically generates unique keys for each data row. To avoid possible file corruption when uploading a data file with second-level or higher-level classification data, populate each row of the [!UICONTROL Key] column with an asterisk (*).

See [Common Classification Upload Issues](https://marketing.adobe.com/resources/help/en_US/home/index.html#kb-common-saint-upload-issues) for troubleshooting help.

<!-- 

c_classifications_example.xml

 -->

![](assets/sample-product-classifications.png)

>[!NOTE]
I dati di classificazione del prodotto sono limitati agli attributi dei dati direttamente correlati al prodotto. I dati non sono limitati alla modalità di categorizzazione o vendita dei prodotti sul sito Web. Elementi dati come categorie di vendite, nodi Sfoglia sito o elementi comprati non sono dati di classificazione del prodotto. Tali elementi vengono invece catturati nelle variabili di conversione del rapporto.

Durante il caricamento di file di dati per questa classificazione di prodotto, potete caricare i dati di classificazione come singoli file o come file multipli (vedi di seguito). Separando il codice del colore nel file 1 e il nome del colore nel file 2, i dati del nome del colore (che possono essere solo poche righe) devono essere aggiornati solo quando vengono creati nuovi codici colore. Questo elimina il nome del colore (CODE &amp; amp; Cappello; COLOR) dal file aggiornato più frequentemente 1 e riduce le dimensioni e la complessità del file durante la generazione del file di dati.

## Product Classification - Single File {#section_E8C5E031869C449F9B636F5EB3BFEC17}

| KEY | NOME PRODOTTO | DETTAGLI PRODOTTO | GENERE | SIZE | CODE | CODE &amp; amp; Cappello; COLOR |
|---|---|---|---|---|---|---|
| 410390013 | Polo-SS | Camicia di uomo, custodia breve (M, 01) | M | M | 01 | Pietra |
| 410390014 | Polo-SS | Camicia di uomo, custodia breve (L, 03) | M | L | 03 | Heather |
| 410390015 | Polo-LS | Camicia di donna, manicotto lungo (S, 23) | F | S | 23 | Acquamarina |

## Product Classification - Multiple Files (File 1) {#section_A99F7D0F145540069BA4EEC0597FF13F}

| KEY | NOME PRODOTTO | DETTAGLI PRODOTTO | GENERE | SIZE | CODE |
|---|---|---|---|---|---|
| 410390013 | Polo-SS | Camicia di uomo, custodia breve (M, 01) | M | M | 01 |
| 410390014 | Polo-SS | Camicia di uomo, custodia breve (L, 03) | M | L | 03 |
| 410390015 | Polo-LS | Camicia di donna, manicotto lungo (S, 23) | F | S | 23 |

## Product Classification - Multiple Files (File 2) {#section_19ED95C33B174A9687E81714568D56A3}

| KEY | CODE | CODE &amp; amp; Cappello; COLOR |
|---|---|---|
| * | 01 | Pietra |
| * | 03 | Heather |
| * | 23 | Acquamarina |
