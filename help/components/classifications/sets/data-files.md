---
description: Comprendere i vari formati di file supportati dai set di classificazione
title: Formati di file del set di classificazione
feature: Classifications
exl-id: f3d429be-99d5-449e-952e-56043b109411
TQID: https://experienceleague.adobe.com/-4pIa7Kqe0sEJkhwiVanaN90xkI8jg0U3-1qEWxRiwM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: e992d880-33bc-4949-a648-aa7d410276cdid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1110
ht-degree: 1%

---

# Formati dei file del set di classificazione

I set di classificazione supportano più formati di file per il caricamento dei dati di classificazione. Ogni formato ha requisiti specifici per caricamenti di dati riusciti.

Una volta che il file è formattato correttamente in base a queste specifiche, puoi caricare i dati tramite l’interfaccia o l’API dei set di classificazione. Per istruzioni di caricamento dettagliate:

* **Caricamento browser**: vedi [Caricamento](manage/schema.md#upload) nell&#39;interfaccia [Schema](manage/schema.md) per un set di classificazione.
* **Caricamento API**: vedi [API classificazioni di Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)

I set di classificazione supportano i seguenti formati di file:

* **JSON**: file di notazione dell&#39;oggetto JavaScript con dati strutturati
* **CSV**: file di valori separati da virgole
* **TSV o TAB**: file di valori separati da tabulazioni

## Requisiti generali dei file

Tutti i formati di file devono rispettare i seguenti requisiti:

* **Codifica file**: utilizzare UTF-8 senza indicatori di ordine dei byte. È supportata anche la codifica Latin1.
* **Limiti dei caratteri**: i singoli valori di classificazione hanno un limite massimo di 255 byte.
* **Requisiti chiave**: i valori chiave non possono essere vuoti o contenere solo spazi vuoti. Se sono presenti chiavi duplicate, viene utilizzata l’ultima occorrenza.

+++ Dettagli formato JSON

Il formato del file JSON segue le convenzioni per le linee JSON (JSONL). Il file deve contenere un oggetto JSON per riga, dove ogni oggetto rappresenta un singolo record di classificazione.

>[!NOTE]
>
>Nonostante le convenzioni per le righe JSON, utilizza l&#39;estensione di file `.json` per tutti i caricamenti. L&#39;utilizzo dell&#39;estensione `.jsonl` può causare errori.

### Struttura JSON

Ogni oggetto JSON deve contenere:

* `key` (obbligatorio): identificatore univoco per il record di classificazione
* `data` (obbligatorio per gli aggiornamenti): oggetto contenente i nomi delle colonne di classificazione e i relativi valori
* `action` (facoltativo): azione da eseguire. I valori supportati includono:
   * `update` (azione predefinita, quando non viene specificata alcuna azione)
   * `delete-field`
   * `delete-key`
* `enc` (facoltativo): specifica di codifica dati. I valori supportati includono:
   * `utf8` o `UTF8` (impostazione predefinita)
   * `latin1` o `LATIN1`

Tutti i nomi di campo JSON (`key`, `data`, `action`, `enc`) fanno distinzione tra maiuscole e minuscole e devono essere minuscole.

### Regole di convalida JSON

* Il campo `key` è obbligatorio e non può essere nullo o vuoto.
* Per le azioni `update`, il campo `data` è obbligatorio e non può essere vuoto.
* Per le azioni `delete-field`, il campo `data` deve contenere i campi da eliminare.
* Per le azioni `delete-key`, il campo `data` non deve essere presente.
* I valori di codifica supportati non fanno distinzione tra maiuscole e minuscole e includono nomi di set di caratteri standard.

### Esempi JSON

Alcuni esempi di record JSON in un file JSON.

#### Record di aggiornamento di base

```json
{"key": "product123", "data": {"Product Name": "Basketball Shoes", "Brand": "Brand A", "Category": "Sports"}}
```

#### Aggiorna con codifica specificata

```json
{"key": "product456", "enc": "utf8", "data": {"Product Name": "Running Shoes", "Brand": "Brand B"}}
```

#### Elimina campi specifici

```json
{"key": "product789", "action": "delete-field", "data": {"Brand": null, "Category": null}}
```

#### Eliminare un&#39;intera chiave

```json
{"key": "product999", "action": "delete-key"}
```


+++

+++ Dettagli formato CSV

I file CSV (Comma-Separated Values, Valori separati da virgole) utilizzano le virgole per separare i campi dei dati di classificazione.

### Struttura CSV

* **Riga intestazione**: la prima riga deve contenere intestazioni di colonna e la prima colonna deve essere la colonna chiave. Le colonne successive devono corrispondere ai nomi nello schema del set di classificazione
* **Righe dati**: ogni riga successiva contiene dati di classificazione
* **Delimitatori**: i campi sono separati da virgole
* **Virgolette**: i campi contenenti virgole, virgolette o nuove righe devono essere racchiusi tra virgolette doppie

### Regole di formattazione CSV

* I campi contenenti virgole devono essere racchiusi tra virgolette.
* I campi contenenti virgolette doppie devono essere preceduti da virgolette (`""`).
* I campi vuoti rappresentano valori nulli per tale classificazione.
* Gli spazi iniziali e finali intorno ai campi vengono tagliati automaticamente.
* I caratteri speciali (tabulazioni, nuove righe) nei campi tra virgolette vengono mantenuti.

### Operazioni di eliminazione CSV

* Utilizza `~deletekey~` in qualsiasi campo per eliminare l&#39;intera chiave e tutti i relativi dati di classificazione
* Utilizza `~empty~` in campi specifici per eliminare solo i valori di classificazione (lasciando invariati gli altri campi)
* Quando si utilizza `~empty~`, è possibile combinare eliminazioni con aggiornamenti nello stesso file

### Esempi di CSV

Alcuni esempi di record CSV in un file CSV.

#### Dati di classificazione di base

```csv
Key,Product Name,Brand,Category,Price
product123,"Basketball Shoes",Brand A,Sports,89.99
product456,"Running Shoes",Brand B,Sports,79.99
product789,"Winter Jacket",Brand C,Clothing,149.99
```

#### Eliminare un&#39;intera chiave

```csv
Key,Product Name,Brand,Category,Price
product999,~deletekey~,,,
```

#### Elimina campi specifici (insieme agli aggiornamenti)

```csv
Key,Product Name,Brand,Category,Price
product123,"Updated Product Name",Brand A,Sports,89.99
product456,,~empty~,~empty~,79.99
```

+++

+++ Dettagli del formato TSV e TAB

I file TSV (Valori separati da tabulazioni) e TAB utilizzano i caratteri di tabulazione per separare i campi dei dati di classificazione.

### Struttura TSV e TAB

* **Riga intestazione**: la prima riga deve contenere intestazioni di colonna e la prima colonna deve essere la colonna chiave. Le colonne successive devono corrispondere ai nomi nello schema del set di classificazione.
* **Righe dati**: ogni riga successiva contiene dati di classificazione.
* **Delimitatori**: i campi sono separati da caratteri di tabulazione (`\t`).
* **Virgolette**: in genere non sono necessarie virgolette, ma alcune implementazioni supportano i campi tra virgolette.

### Regole di formattazione TSV e TAB

* I campi sono separati da caratteri di tabulazione singoli.
* I campi vuoti (schede consecutive) rappresentano valori Null.
* In genere non sono richieste virgolette speciali.
* Gli spazi iniziali e finali vengono mantenuti.
* I caratteri di nuova riga all’interno dei campi devono essere evitati.

### Operazioni di eliminazione TSV e TAB

* Utilizza `~deletekey~` in qualsiasi campo per eliminare l&#39;intera chiave e tutti i relativi dati di classificazione.
* Utilizza `~empty~` in campi specifici per eliminare solo i valori di classificazione (lasciando invariati gli altri campi).
* Quando si utilizza `~empty~`, è possibile combinare eliminazioni con aggiornamenti nello stesso file.

### Esempi di TSV e TAB

Alcuni esempi di record delimitati da TSV o TAB in un file TSV o TAB.

#### Dati di classificazione di base

```tsv
Key    Product Name    Brand    Category    Price
product123    Basketball Shoes    Brand A    Sports    89.99
product456    Running Shoes    Brand B    Sports    79.99
product789    Winter Jacket    Brand C    Clothing    149.99
```

#### Eliminare un&#39;intera chiave

```tsv
Key    Product Name    Brand    Category    Price
product999    ~deletekey~            
```

#### Elimina campi specifici (insieme agli aggiornamenti)

```tsv
Key    Product Name    Brand    Category    Price
product123    Updated Product Name    Brand A    Sports    89.99
product456        ~empty~    ~empty~    79.99
```

+++

## Gestione degli errori

Problemi comuni e soluzioni durante il caricamento dei file:

### Errori generali nel formato del file

* **Formato file non valido**: verificare che l&#39;estensione del file corrisponda al formato del contenuto (`.json`, `.csv`, `.tsv` o `.tab`).
* **Intestazione sconosciuta**: i nomi delle colonne devono corrispondere allo schema del set di classificazione (si applica a tutti i formati).

### Errori specifici JSON

* **La chiave è un campo obbligatorio**: tutti i record JSON devono avere un campo `"key"` non vuoto (minuscolo, con distinzione tra maiuscole e minuscole).
* **I dati sono un campo obbligatorio quando si utilizza action=update**: le azioni di aggiornamento JSON devono includere un campo `"data"`.
* **I dati sono un campo obbligatorio quando si utilizza action=delete-field**: Le azioni di eliminazione JSON devono specificare quali campi eliminare nel campo `"data"`.
* **I dati non devono essere presenti quando si utilizza action=delete-key**: Le azioni chiave di eliminazione JSON non possono includere un campo `"data"`.
* **Codifica non supportata**: utilizzare solo i valori di codifica supportati nel campo `"enc"` (`utf8`, `UTF8`, `latin1`, `LATIN1`).
* **Sintassi JSON non valida**: verifica che il file JSON sia formattato correttamente in base alle convenzioni JSONL. Controlla anche la formattazione JSON generale, le virgolette mancanti, le virgole, le parentesi quadre, ecc.


### Errori specifici per CSV e TSV

* **La prima colonna deve essere la chiave**: verificare che il file CSV o TSV contenga una riga di intestazione corretta con la prima colonna chiave.
* **Sono necessari almeno due elementi di intestazione**: i file CSV o TSV devono avere almeno una colonna `Key` e una colonna di classificazione.
* **La prima colonna di intestazione deve essere denominata &#39;Chiave&#39;**: l&#39;intestazione della prima colonna deve essere esattamente `Key` (maiuscolo `K`, con distinzione tra maiuscole e minuscole).
* **Le intestazioni vuote non sono consentite**: tutte le intestazioni di colonna CSV/TSV devono avere nomi.
* **Il numero di colonne non corrisponde alle intestazioni**: ogni riga di dati CSV o TSV deve avere lo stesso numero di campi della riga di intestazione.
* **&quot;Documento in formato non valido**: controlla le virgolette CSV, la separazione delle tabulazioni nei file TSV e altro ancora.


### Errori di limite di dimensione

* **La chiave supera la dimensione massima**: le singole chiavi non possono superare i 255 byte.
* **Il valore della colonna supera la dimensione massima**: i singoli valori di classificazione non possono superare i 255 byte.

## Best practice

* **Dimensione file**: 50 MB è la dimensione massima del file per i caricamenti del browser e dell&#39;API.
* **Elaborazione batch**: per i set di dati di grandi dimensioni, è consigliabile suddividerli in file più piccoli.
* **Convalida dei dati**: verifica con un piccolo file di esempio prima di caricare set di dati di grandi dimensioni.
* **Backup**: mantieni copie dei file di dati di origine.
* **Aggiornamenti incrementali**: utilizza il formato JSON per un controllo preciso degli aggiornamenti e delle eliminazioni dei singoli record.
