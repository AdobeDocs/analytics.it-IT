---
description: Formati di file supportati dai set di classificazione
title: Formati dei file del set di classificazione
feature: Classifications
exl-id: f3d429be-99d5-449e-952e-56043b109411
source-git-commit: c642664ecca24d9fc555944fb2b449f30eac879d
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 1%

---

# Formati dei file del set di classificazione

I set di classificazione supportano più formati di file per il caricamento in blocco dei dati di classificazione. Ogni formato ha requisiti specifici per caricamenti di dati riusciti.

Una volta che il file è formattato correttamente in base a queste specifiche, puoi caricarlo tramite l’interfaccia o l’API dei set di classificazione. Per istruzioni di caricamento dettagliate:

* **Caricamento browser**: Vedere [Schema](manage/schema.md)
* **Caricamento API**: vedi [API classificazioni di Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)

I set di classificazione supportano i seguenti formati di file:

* **JSON**: file di notazione dell&#39;oggetto JavaScript con dati strutturati
* **CSV**: file di valori separati da virgole
* **TSV/TAB**: file di valori separati da tabulazioni

## Requisiti generali dei file

Tutti i formati di file devono rispettare i seguenti requisiti:

* **Codifica file**: utilizzare UTF-8 senza indicatori di ordine dei byte. È supportata anche la codifica Latin1.
* **Limiti dei caratteri**: i singoli valori di classificazione hanno un limite massimo di 255 byte.
* **Requisiti chiave**: i valori chiave non possono essere vuoti o contenere solo spazi vuoti. Se sono presenti chiavi duplicate, viene utilizzata l’ultima occorrenza.

+++**Dettagli formato JSON**

Il formato del file JSON segue le convenzioni per le linee JSON (JSONL). Il file deve contenere un oggetto JSON per riga, dove ogni oggetto rappresenta un singolo record di classificazione.

>[!NOTE]
>
>Nonostante le seguenti convenzioni per le righe JSON, utilizza l&#39;estensione di file `.json` per tutti i caricamenti. L&#39;utilizzo dell&#39;estensione `.jsonl` può causare errori.

### Struttura JSON

Ogni oggetto JSON deve contenere:

* `key` (obbligatorio): identificatore univoco per il record di classificazione
* `data` (obbligatorio per gli aggiornamenti): oggetto contenente i nomi delle colonne di classificazione e i relativi valori
* `action` (facoltativo): azione da eseguire. I valori supportati includono:
   * `update` (predefinito)
   * `delete-field`
   * `delete-key`
* `enc` (facoltativo): specifica di codifica dati. I valori supportati includono:
   * `utf8` o `UTF8` (impostazione predefinita)
   * `latin1` o `LATIN1`

Tutti i nomi di campo JSON (`key`, `data`, `action`, `enc`) fanno distinzione tra maiuscole e minuscole e devono essere minuscole.

### Esempi JSON

**Record aggiornamento di base:**

```json
{"key": "product123", "data": {"Product Name": "Basketball Shoes", "Brand": "Brand A", "Category": "Sports"}}
```

**Aggiornamento con codifica specificata:**

```json
{"key": "product456", "enc": "utf8", "data": {"Product Name": "Running Shoes", "Brand": "Brand B"}}
```

**Elimina campi specifici:**

```json
{"key": "product789", "action": "delete-field", "data": {"Brand": null, "Category": null}}
```

**Elimina chiave intera:**

```json
{"key": "product999", "action": "delete-key"}
```

### Regole di convalida JSON

* Il campo `key` è obbligatorio e non può essere nullo o vuoto.
* Per le azioni `update`, il campo `data` è obbligatorio e non può essere vuoto.
* Per le azioni `delete-field`, il campo `data` deve contenere i campi da eliminare.
* Per le azioni `delete-key`, il campo `data` non deve essere presente.
* I valori di codifica supportati non fanno distinzione tra maiuscole e minuscole e includono nomi di set di caratteri standard.

+++

+++**Dettagli formato CSV**

I file CSV (Comma-Separated Values, Valori separati da virgole) utilizzano le virgole per separare i campi dei dati di classificazione.

### Struttura CSV

* **Riga intestazione**: la prima riga deve contenere intestazioni di colonna e la prima colonna deve essere la colonna chiave. Le colonne successive devono corrispondere ai nomi nello schema del set di classificazione
* **Righe dati**: ogni riga successiva contiene dati di classificazione
* **Delimitatori**: i campi sono separati da virgole
* **Virgolette**: i campi contenenti virgole, virgolette o nuove righe devono essere racchiusi tra virgolette doppie

### Esempi di CSV

**Dati di classificazione di base:**

```csv
Key,Product Name,Brand,Category,Price
product123,"Basketball Shoes",Brand A,Sports,89.99
product456,"Running Shoes",Brand B,Sports,79.99
product789,"Winter Jacket",Brand C,Clothing,149.99
```

**Elimina chiave intera:**

```csv
Key,Product Name,Brand,Category,Price
product999,~deletekey~,,,
```

**Elimina campi specifici (insieme agli aggiornamenti):**

```csv
Key,Product Name,Brand,Category,Price
product123,"Updated Product Name",Brand A,Sports,89.99
product456,,~empty~,~empty~,79.99
```

### Regole di formattazione CSV

* I campi contenenti virgole devono essere racchiusi tra virgolette doppie
* I campi contenenti virgolette doppie devono essere preceduti da virgolette di escape doppie (`""`)
* I campi vuoti rappresentano valori nulli per tale classificazione
* Gli spazi iniziali e finali intorno ai campi vengono tagliati automaticamente
* I caratteri speciali (tabulazioni, nuove righe) nei campi tra virgolette vengono mantenuti

**Operazioni di eliminazione:**
* Utilizza `~deletekey~` in qualsiasi campo per eliminare l&#39;intera chiave e tutti i relativi dati di classificazione
* Utilizza `~empty~` in campi specifici per eliminare solo i valori di classificazione (lasciando invariati gli altri campi)
* Quando si utilizza `~empty~`, è possibile combinare eliminazioni con aggiornamenti nello stesso file

+++

+++**Dettagli formato TSV/TAB**

I file TSV (Valori separati da tabulazioni) e TAB utilizzano i caratteri di tabulazione per separare i campi dei dati di classificazione.

### Struttura TSV/TAB

* **Riga intestazione**: la prima riga deve contenere intestazioni di colonna e la prima colonna deve essere la colonna chiave. Le colonne successive devono corrispondere ai nomi nello schema del set di classificazione
* **Righe dati**: ogni riga successiva contiene dati di classificazione
* **Delimitatori**: i campi sono separati da caratteri di tabulazione (`\t`)
* **Virgolette**: in genere non sono necessarie virgolette, ma alcune implementazioni supportano campi tra virgolette

### Esempi di TSV/TAB

**Dati di classificazione di base:**

```tsv
Key    Product Name    Brand    Category    Price
product123    Basketball Shoes    Brand A    Sports    89.99
product456    Running Shoes    Brand B    Sports    79.99
product789    Winter Jacket    Brand C    Clothing    149.99
```

**Elimina chiave intera:**

```tsv
Key    Product Name    Brand    Category    Price
product999    ~deletekey~            
```

**Elimina campi specifici (insieme agli aggiornamenti):**

```tsv
Key    Product Name    Brand    Category    Price
product123    Updated Product Name    Brand A    Sports    89.99
product456        ~empty~    ~empty~    79.99
```

### Regole di formattazione TSV/TAB

* I campi sono separati da caratteri di tabulazione singoli
* I campi vuoti (schede consecutive) rappresentano valori Null
* In genere non sono richieste virgolette speciali
* Gli spazi iniziali e finali vengono mantenuti
* Evitare l’utilizzo di caratteri di nuova riga all’interno dei campi

**Operazioni di eliminazione:**
* Utilizza `~deletekey~` in qualsiasi campo per eliminare l&#39;intera chiave e tutti i relativi dati di classificazione
* Utilizza `~empty~` in campi specifici per eliminare solo i valori di classificazione (lasciando invariati gli altri campi)
* Quando si utilizza `~empty~`, è possibile combinare eliminazioni con aggiornamenti nello stesso file

+++

## Gestione degli errori

Problemi di caricamento comuni e soluzioni:

### Errori generali nel formato del file

* **Formato file non valido**: verificare che l&#39;estensione del file corrisponda al formato del contenuto (.json, .csv, .tsv o .tab).
* **&quot;Intestazione sconosciuta&quot;**: i nomi delle colonne devono corrispondere allo schema del set di classificazione (si applica a tutti i formati).

### Errori specifici CSV/TSV

* **&quot;La prima colonna deve essere la chiave&quot;**: verificare che il file CSV/TSV contenga una riga di intestazione corretta con la colonna chiave.
* **&quot;Sono necessari almeno due elementi di intestazione&quot;**: i file CSV/TSV devono avere almeno una colonna &quot;Chiave&quot; e una colonna di classificazione.
* **&quot;La prima colonna di intestazione deve essere denominata &#39;Key&#39;&quot;**: l&#39;intestazione della prima colonna deve essere esattamente &quot;Key&quot; (maiuscolo K, con distinzione tra maiuscole e minuscole).
* **&quot;Le intestazioni vuote non sono consentite&quot;**: tutte le intestazioni di colonna CSV/TSV devono avere nomi.
* **&quot;Il numero di colonne non corrisponde alle intestazioni&quot;**: ogni riga di dati CSV/TSV deve avere lo stesso numero di campi della riga di intestazione.
* **&quot;Documento in formato non valido&quot;**: controllare le virgolette CSV, la separazione delle tabulazioni nei file TSV e così via.

### Errori specifici JSON

* **&quot;La chiave è un campo obbligatorio&quot;**: tutti i record JSON devono avere un campo `"key"` non vuoto (minuscolo, distinzione maiuscole/minuscole).
* **&quot;I dati sono un campo obbligatorio quando si utilizza action=update&quot;**: le azioni di aggiornamento JSON devono includere un campo `"data"`.
* **&quot;I dati sono un campo obbligatorio quando si utilizza action=delete-field&quot;**: Le azioni di eliminazione JSON devono specificare quali campi eliminare nel campo `"data"`.
* **&quot;I dati non devono essere presenti quando si utilizza action=delete-key&quot;**: Le azioni chiave di eliminazione JSON non possono includere un campo `"data"`.
* **&quot;Codifica non supportata&quot;**: utilizzare solo i valori di codifica supportati nel campo `"enc"` (utf8, UTF8, latin1, LATIN1).
* **Sintassi JSON non valida**: verifica che il file JSON sia formattato correttamente in base alle convenzioni JSONL. Controlla anche la formattazione JSON generale, le virgolette mancanti, le virgole, le parentesi quadre, ecc.

### Errori di limite di dimensione

* **&quot;La chiave supera la dimensione massima&quot;**: le singole chiavi non possono superare i 255 byte.
* **&quot;Il valore della colonna supera la dimensione massima&quot;**: i singoli valori di classificazione non possono superare i 255 byte.

## Best practice

* **Dimensione file**: 50 MB è la dimensione massima del file per i caricamenti del browser e dell&#39;API.
* **Elaborazione batch**: per i set di dati di grandi dimensioni, è consigliabile suddividerli in file più piccoli.
* **Convalida dei dati**: verifica con un piccolo file di esempio prima di caricare set di dati di grandi dimensioni.
* **Backup**: mantieni copie dei file di dati di origine.
* **Aggiornamenti incrementali**: utilizza il formato JSON per un controllo preciso degli aggiornamenti e delle eliminazioni dei singoli record.
